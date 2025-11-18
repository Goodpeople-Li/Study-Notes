# MATLAB Basics
1. linspace函数
   ```matlab
   y = linspace(a, b, n)
   ```
   生成一个行向量y，包含从a到b的n个等间距点。

2. figure函数
   ```matlab
   figure('Name', 'My Figure', 'NumberTitle', 'off');
   ```
   创建一个新的图形窗口，并设置窗口名称为"My Figure"，关闭默认的编号标题。
   也可以直接单独使用
   ```matlab
   figure;
   ```
   这将创建一个新的图形窗口，使用默认设置。

3. plot函数
   ```matlab
    plot(x, y, 'r--', 'LineWidth', 2);
    ```这个颜色和线型参数表示绘制红色虚线，线宽为2个单位。
    颜色和线型总共有一下几种表示方法：
   - 颜色：'r'（红色）、'g'（绿色）、'b'（蓝色）、'c'（青色）、'm'（品红色）、'y'（黄色）、'k'（黑色）、'w'（白色）
   - 线型：'-'（实线）、'--'（虚线）、':'（点线）、'-.'（点划线）

3. legend函数
   ```matlab
   legend('Data 1', 'Data 2', 'Location', 'northeast');
   ```
   为图形添加图例，'Data 1'和'Data 2'是图例标签，'Location'参数指定图例位置为右上角。

4. subplot函数
   ```matlab
   subplot(2, 1, 1);
   plot(x1, y1);
   title('Subplot 1');

   subplot(2, 1, 2);
   plot(x2, y2);
   title('Subplot 2');
   ```
   创建一个2行1列的子图布局，并在第一个子图中绘制x1和y1的数据，在第二个子图中绘制x2和y2的数据。

5. sgtitle函数
   ```matlab
   sgtitle('Overall Title');
   ```
   为整个图形窗口添加一个总标题。

6. bar函数
   ```matlab
   bar(x, y, 'b');
   ```
   创建一个条形图，'b'参数设置条形的填充颜色为蓝色。

7. stairs函数
   ```matlab
   stairs(x, y, 'g');
   ```
   创建一个阶梯图，'g'参数设置阶梯线的颜色为绿色。

8. stem函数
   ```matlab
   stem(x, y, 'r', 'filled');
   ```
   创建一个离散数据的茎叶图，'r'参数设置茎叶的颜色为红色，'filled'参数表示茎叶标记为实心。

9. abs函数
   ```matlab
   y_abs = abs(y);
   ```
   计算向量y中每个元素的绝对值，并将结果存储在y_abs中。

10. integral函数
    ```matlab
    area = integral(@(x) x.^2, a, b);
    ```
    计算函数x^2在区间[a, b]上的定积分，并将结果存储在area中。

11. fprintf函数
    ```matlab
    fprintf('The result is: %.2f\n', result);
    ```
    将格式化的字符串输出到命令窗口，'%.2f'表示以浮点数形式显示result，保留两位小数。

12. polyfit函数
    ```matlab
    p = polyfit(x, y, n);
    ```
    进行多项式拟合，返回拟合的多项式系数p。

13. polyval函数
    ```matlab
    y_fit = polyval(p, x);
    ```
    计算多项式p在点x处的值，返回拟合结果y_fit。

14. polyder函数
    ```matlab
    dp = polyder(p);
    ```
    计算多项式p的导数，返回导数多项式的系数dp。