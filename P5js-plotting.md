# Plotting in P5js

## Exporting SVGs
I'm working with ZenoZeng's (P5.svg-js library](https://github.com/zenozeng/p5.js-svg). Unfortunately at the time of writing (September 2024) it is broken and unsupported with the latest version of P5js. You'll need to change your index.html to reference the last working verion of p5.js-svg, which was 1.6.0.

In index.html of your p5js sketch, replace the existing p5js library with:
`<script src="https://cdnjs.cloudflare.com/ajax/libs/p5.js/1.6.0/p5.js"></script>`
then add the following line to include the SVG library:
`<script src="https://unpkg.com/p5.js-svg@1.5.1"></script>`

Back in your main sketch.js file, include the `SVG` argument in your `createCanvas` at setup:
`createCanvas(200, 200,SVG);`
then you'll want a way to trigger exporting your SVG when ready. for example:
```function keyPressed(){
    if(key === 's'){
        save("mySVG.svg");
    }
}```

Fingers crossed we get native SVG exporting in p5js 2.0...