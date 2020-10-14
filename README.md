# Visualization_Study

学习主流的可视化底层原理 ``canvas``, ``WebGL``

- [Visualization_Study](#visualization_study)
  - [参考](#参考)
  - [``canvas``](#canvas)
  - [`` WebGL``](#-webgl)
    - [介绍](#介绍)

## 参考
> - [W3Cschool](https://www.w3cschool.cn/webgl/i4gf1oh1.html)

## ``canvas``

## `` WebGL``
### 介绍
> - 基于光栅化的API，而不是3D的API
> - 只关注 投影矩阵的坐标和颜色。由**着色器**提供 
> - 顶点着色器可以提供投影矩阵的坐标，片段着色器可以提供投影矩阵的颜色
> - 无论要实现的图形尺寸有多大，其投影矩阵的坐标的范围始终是从 -1 到 1
> - 需要做的第一件事就是获取``canvas``
```html
        <body onload="main()">
            <canvas id="glcanvas" width="640" height="480">
                你的浏览器似乎不支持或者禁用了HTML5 <code>&lt;canvas&gt;</code> 元素.
            </canvas>
        </body>
        <script>
            // 从这里开始
            function main() {
                const canvas = document.querySelector("#glcanvas");
                // 初始化WebGL上下文
                const gl = canvas.getContext("webgl");

                // 确认WebGL支持性
                if (!gl) {
                    alert("无法初始化WebGL，你的浏览器、操作系统或硬件等可能不支持WebGL。");
                    return;
                }

                // 使用完全不透明的黑色清除所有图像
                gl.clearColor(0.0, 0.0, 0.0, 1.0);
                // 用上面指定的颜色清除缓冲区
                gl.clear(gl.COLOR_BUFFER_BIT);
            }
        </script>
```