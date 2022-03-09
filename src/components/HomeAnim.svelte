<script lang="ts">
    import { onMount } from "svelte";

    interface Circle {
        x: number;
        y: number;
        armX: number;
        armY: number;
        speed: number;
        radius: number;
        rotate: number;
    };

	class Circle {
		constructor(x: number, y: number, speed: number, radius: number){
            [this.x, this.y, this.speed, this.radius, this.rotate] = [x, y, speed, radius, 0];
            [this.armX, this.armY] = [this.radius * Math.cos(this.rotate), this.radius * Math.sin(this.rotate)];
		}

		render(ctx: CanvasRenderingContext2D){
            ctx.strokeStyle = "#aaa"
            ctx.beginPath();
			ctx.ellipse(this.x, this.y, this.radius, this.radius, 0, 0, 2 * Math.PI);
            ctx.stroke();

            ctx.strokeStyle = "#333";
            ctx.beginPath();
            ctx.moveTo(this.x, this.y);
			ctx.lineTo(this.x + this.armX, this.y + this.armY);
            ctx.stroke();
		}

		update(){
            this.rotate += this.speed;
            [this.armX, this.armY] = [this.radius * Math.cos(this.rotate), this.radius * Math.sin(this.rotate)];
		}
	};

	let points = [];
	let circles: Circle[] = [];

    const leftOffset = 200;
    const circleCount = 10;

    function random(start: number, end: number){
        return (start + (start - end) * Math.random());
    }
    
    let setup = ({width, height}) => {
        circles.push(new Circle(leftOffset, height/2, random(0, Math.PI/100), 50));
        for (let i = 0; i < circleCount; ++i){
            const prevCircle = circles[circles.length - 1];
            circles.push(new Circle(prevCircle.x + prevCircle.armX, prevCircle.y + prevCircle.armY, (i % 2 ? 1:-1) * random(0, Math.PI/100) , prevCircle.radius/random(1.5, 2)));
        }
    }

    let render = ({ ctx, width, height, t }) => {
        ctx.clearRect(0, 0, width, height);
        ctx.fillStyle = "#eee";
        ctx.fillRect(0, 0, width, height);

		for (let i = 0; i < circles.length; ++i){
            let circle = circles[i];
			if (i < circles.length - 1){
				circles[i + 1].x = circle.x + circle.armX;
				circles[i + 1].y = circle.y + circle.armY;
			}

			circle.render(ctx);
            circle.update();
		}

        const lastCircle = circles[circles.length - 1];
		points.push(lastCircle.y + lastCircle.armY);

        ctx.strokeStyle = "#0160e2";
        ctx.beginPath();
        ctx.moveTo(lastCircle.x + lastCircle.armX, lastCircle.y + lastCircle.armY);
        ctx.lineTo(width - points.length, lastCircle.y + lastCircle.armY);
        ctx.stroke();
        
        ctx.strokeStyle = "#333";
        ctx.fillStyle = "#ccc"
		ctx.beginPath();
            ctx.moveTo(width, height/2);
            for (let i = 0; i < points.length; ++i){
                ctx.lineTo(width - i, points[i]);
                if (points.length > width - leftOffset * 2){
                    points.splice(0, 1);
                    --i;
                }
            }
            ctx.lineTo(width - points.length + 1, height/2);
        ctx.closePath();
        ctx.stroke();
        ctx.fill();
    };

    let canvas;
    let t = 0;

    onMount(() => {
        const ctx = canvas.getContext('2d');
        let frame = requestAnimationFrame(loop);

        function loop() {
            frame = requestAnimationFrame(loop);

            if (t == 0){
                setup({width: canvas.width, height: canvas.height});
                for (let i = 0; i < width - leftOffset * 2; ++i){
                    render({t: t, ctx: ctx, width: canvas.width, height: canvas.height});
                }
            }

            render({t: t, ctx: ctx, width: canvas.width, height: canvas.height});
            ++t;
        }

        return () => {
            cancelAnimationFrame(frame);
        };
    });

    export let width: number, height: number;
</script>

<canvas
bind:this={canvas}
width={width}
height={height}
></canvas>
