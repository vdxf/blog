## 正方形

```html
<section>
    <div id="square"></div>
</section>
<style type="text/css">
    #square{
        width: 100px;
        height: 100px;
        background: #4C98F7;
    }
</style>
```

## 长方形

```html
<section>
    <div id="rectangle"></div>
</section>
<style type="text/css">
    #rectangle{
        width: 200px;
        height: 100px;
        background: #4C98F7;
    }
</style>
```

## 圆形

```html
<section>
    <div id="circle"></div>
</section>
<style type="text/css">
    #circle{
        width: 100px;
        height: 100px;
        background: #4C98F7;
        border-radius: 50%;
    }
</style>
```

## 半圆

```html
<section>
    <div id="semicircle"></div>
</section>
<style type="text/css">
    #semicircle{
        width: 100px;
        height: 50px;
        background: #4C98F7;
        border-radius: 100px 100px 0 0;
    }
</style>
```

## 椭圆

```html
<section>
    <div id="oval"></div>
</section>
<style type="text/css">
    #oval{
        width: 100px;
        height: 50px;
        background: #4C98F7;
        border-radius: 100px / 50px;
    }
</style>
```

## 三角形

```html
<section>
    <div id="regular-triangle"></div>
</section>
<style type="text/css">
    #regular-triangle{
        width: 0;
        height: 0;
        border-left: 50px solid transparent;
        border-right: 50px solid transparent;
        border-bottom: 100px solid #4C98F7;
    }
</style>

<section>
    <div id="corner-triangle"></div>
</section>
<style type="text/css">
    #corner-triangle{
        width: 0;
        height: 0;
        border-top: 100px solid #4C98F7;
        border-right: 100px solid transparent;
    }
</style>
```

## 平行四边形

```html
<section>
    <div id="parallelogram"></div>
</section>
<style type="text/css">
    #parallelogram{
        margin: 0 15px;
        width: 200px; 
        height: 100px; 
        transform: skew(-20deg); 
        background: #4C98F7;
    }
</style>
```

## 菱形

```html
<section>
    <div id="diamond"></div>
</section>
<style type="text/css">
    #diamond {
        width: 0;
        height: 0;
        border: 100px solid transparent;
        border-bottom-color: #4C98F7;
        position: relative;
        top: -100px;
    }
    #diamond:after {
        content: "";
        position: absolute;
        left: -100px;
        top: 100px;
        width: 0;
        height: 0;
        border: 100px solid transparent;
        border-top-color: #4C98F7;
    }
</style>
```

## 六角星

```html
<section>
    <div id="hexagons"></div>
</section>
<style type="text/css">
    #hexagons {
        width: 0;
        height: 0;
        border: 100px solid transparent;
        border-bottom-color: #4C98F7;
        position: relative;
        top: -100px;
    }
    #diamond:after {
        content: "";
        position: absolute;
        left: -100px;
        top: 100px;
        width: 0;
        height: 0;
        border: 100px solid transparent;
        border-top-color: #4C98F7;
    }
</style>
```

## 五角星

```html
<section>
    <div id="five-pointed-star"></div>
</section>
<style type="text/css">
    #five-pointed-star { 
        margin: 100px 0 50px 0; 
        position: relative;
        width: 0px; 
        height: 0px; 
        border-right: 100px solid transparent; 
        border-bottom: 70px solid #4C98F7; 
        border-left: 100px solid transparent; 
        transform: rotate(35deg); 
    }
     #five-pointed-star:before { 
        content: ""; 
        position: absolute; 
        height: 0; 
        width: 0; 
        top: -45px; 
        left: -65px; 
        border-bottom: 80px solid #4C98F7; 
        border-left: 30px solid transparent; 
        border-right: 30px solid transparent; 
        transform: rotate(-35deg); 
    } 
    #five-pointed-star:after { 
        content: ""; 
        position: absolute; 
        top: 3px; 
        left: -105px; 
        width: 0px; 
        height: 0px; 
        border-right: 100px solid transparent; 
        border-bottom: 70px solid #4C98F7; 
        border-left: 100px solid transparent; 
        transform: rotate(-70deg); 
    }
</style>
```

## 心形

```html
<section>
    <div id="five-pointed-star"></div>
</section>
<style type="text/css">
    #five-pointed-star { 
        margin: 100px 0 50px 0; 
        position: relative;
        width: 0px; 
        height: 0px; 
        border-right: 100px solid transparent; 
        border-bottom: 70px solid #4C98F7; 
        border-left: 100px solid transparent; 
        transform: rotate(35deg); 
    }
     #five-pointed-star:before { 
        content: ""; 
        position: absolute; 
        height: 0; 
        width: 0; 
        top: -45px; 
        left: -65px; 
        border-bottom: 80px solid #4C98F7; 
        border-left: 30px solid transparent; 
        border-right: 30px solid transparent; 
        transform: rotate(-35deg); 
    } 
    #five-pointed-star:after { 
        content: ""; 
        position: absolute; 
        top: 3px; 
        left: -105px; 
        width: 0px; 
        height: 0px; 
        border-right: 100px solid transparent; 
        border-bottom: 70px solid #4C98F7; 
        border-left: 100px solid transparent; 
        transform: rotate(-70deg); 
    }
</style>
```