```注释
                    _ooOoo_
                   o8888888o
                   88" . "88
                   (| -_- |)
                    O\ = /O
                ____/`---'\____
              .   ' \\| |// `.
               / \\||| : |||// \
             / _||||| -:- |||||- \
               | | \\\ - /// | |
             | \_| ''\---/'' | |
              \ .-\__ `-` ___/-. /
           ___`. .' /--.--\ `. . __
        ."" '.___\__/___.' >'""
       | | : `- \`.;`\ _ /`;.`/ - ` : | |
         \ \ `-. \_ __\ /__ _/ .-` / /
======`-.____`-.___\_____/___.-`____.-'======
                    `=---='

.............................................
         佛祖保佑             永无BUG
```

# matlab期末复习
/*
作者：李志浩[^1]   
日期：2025/11/11    
内容：长期以来不玩植物大战僵尸，坚持学习matlab,长期努力的结果     
*/





1. matlab各个界面的名称和作用

- Command Window（命令窗口）：用于输入和执行命令。
- Workspace（工作区）：显示当前变量及其值。
- Command History（命令历史）：记录之前执行过的命令。
- Current Folder（当前文件夹）：显示当前工作目录中的文件和文件夹。
- Editor（编辑器）：用于编写和编辑脚本和函数文件。
- Figure Window（图形窗口）：用于显示绘图和图形。

2. 变量的命名的规则

- 变量名必须以字母开头，可以包含字母、数字和下划线（_）。
- 变量名区分大小写，例如，变量A和a是不同的变量。
- 变量名不能是MATLAB的关键字或保留字，例如if、for、while等。
- 变量名不能包含空格或特殊字符。

3. sqrt函数

```matlab
y = sqrt(x);
```

计算x的平方根，并将结果存储在变量y中。

4. 冒号法生成向量

```matlab
v = start:step:end;
```
注意：默认步长为1。

5. linspace函数

```matlab
v = linspace(start, end, numPoints);
```
linspace = lin(ear) + space → 产生“线性等间距的空间（向量）”。
生成一个包含numPoints个点的行向量v，范围从start到end。

6. find函数

```matlab
index = find(condition);
```

根据给定的条件查找满足条件的元素的索引，并将结果存储在变量index中。

7. mod函数

```matlab
remainder = mod(a, b);
```

计算a除以b的余数，并将结果存储在变量remainder中。

8. length函数

```matlab
len = length(v);
```

计算向量v的长度，并将结果存储在变量len中。

9. disp函数

```matlab
disp(message);
```

10. sprintf

```matlab
formattedString = sprintf('The value of x is %.2f', x);
```

11. fprintf

```matlab
fprintf('The value of x is %.2f\n', x);
```

12. meshgrid函数

```matlab
[X, Y] = meshgrid(x, y);
```

生成二维网格坐标矩阵X和Y，分别对应向量x和y的所有组合。

13. eps函数

```matlab
e = eps;
```

eps为MATLAB中的机器精度，表示浮点数运算中的最小可区分差值。可以用来替换0进行数值比较，以避免浮点数运算中的误差。

14. figure函数

```matlab
figure;
```

创建一个新的图形窗口。

15. grid on

```matlab
grid on;
```

在当前图形窗口中打开网格线。

16. plot函数

```matlab
plot(x, y, 'r-');
```

绘制向量x和y的二维线性图。第三个参数表示线条的颜色和样式。颜色名称 短名称 RGB 三元组 外观
"red" "r" [1 0 0]
Sample of the color red

"green" "g" [0 1 0]
Sample of the color green

"blue" "b" [0 0 1]
Sample of the color blue

"cyan" "c" [0 1 1]
Sample of the color cyan

"magenta" "m" [1 0 1]
Sample of the color magenta

"yellow" "y" [1 1 0]
Sample of the color yellow

"black" "k" [0 0 0]
Sample of the color black

"white" "w" [1 1 1]
Sample of the color white

"-" 实线
Sample of solid line

"--" 虚线
Sample of dashed line

":" 点线
Sample of dotted line

"-." 点划线
Sample of dash-dotted line, with alternating dashes and dots

17. rand函数

  ```matlab
  r = rand(m, n);
  ```
生成一个m行n列的矩阵r，矩阵中的元素为均匀分布在(0, 1)区间的随机数。
- randn函数
  ```matlab
  r = rand(m, n);
  ```
生成一个m行n列的矩阵r，矩阵中的元素为正态分布在(0, 1)区间的随机数，方差为1，均值为0。




18.  diag函数

```matlab
d = diag(v);
```

将向量v转换为对角矩阵d。

19. kron函数

```matlab
K = kron(A, B);
```

计算矩阵A和B的Kronecker积，并将结果存储在矩阵K中。

20. inv函数

```matlab
invA = inv(A);
```

计算矩阵A的逆矩阵，并将结果存储在矩阵invA中。

二阶矩阵显式求逆公式：若

$$A = \begin{bmatrix} a & b \\ c & d \end{bmatrix}, \; \det(A)=ad-bc\neq 0,$$

则

$$A^{-1} = \frac{1}{ad-bc}\begin{bmatrix} d & -b \\ -c & a \end{bmatrix}.$$

说明：
- 判定是否可逆只需看行列式 ad - bc 是否为 0。
- 手算时先算行列式，再交换主对角元素 (a,d)，改变副对角元素符号 (b,c)。
- 在 MATLAB 中更推荐用 `A\eye(size(A))` 或 `A\b` 求解线性方程，而不是直接 `inv(A)`（数值稳定性更好）。

示例：
```matlab
A = [2 3; 5 7];
detA = det(A);          % 2*7 - 3*5 = 14 - 15 = -1
A_inv_formula = (1/detA)*[7 -3; -5 2];
A_inv_builtin = inv(A);
norm(A_inv_formula - A_inv_builtin)  % 验证 ≈ 0
```

若 `detA == 0`，矩阵不可逆，`inv(A)` 会报错或返回数值不稳定结果（奇异矩阵警告）。

21. expand函数

```matlab
syms x y
f1 = (x + 1)^3;
g1 = expand(f1);          % 展开幂：x^3 + 3*x^2 + 3*x + 1

f2 = (3*x^3 + x)*(x^3 + 1/2);
g2 = expand(f2);          % 展开乘积，得到单一多项式

f3 = (x + y)*(x - y);
g3 = expand(f3);          % -> x^2 - y^2

% 与 factor 相反的操作
h  = factor(g1);          % 把展开结果再因式分解为 (x + 1)^3
```

说明：expand 用于符号表达式的代数“展开”，把乘积、幂、括号等展开成各项之和。只作用于 syms 或 symbolic 类型；与 factor 相互配合（factor=因式分解，expand=展开）。复杂表达式展开后项数可能急剧增长，注意可读性与性能.

22. quorem函数

```matlab
syms x
N = (3*x^3 + x)*(x^3 + 1/2);      % 被除多项式（先可 expand）
D = (x^2 + 2*x - 2)*(5*x^3 + 2*x^2 + 1);  % 除式
N = expand(N);
D = expand(D);

[Q,R] = quorem(N, D, x);          % Q: 商多项式  R: 余多项式
```

作用：对两个符号多项式做“整除”式的多项式除法，返回商 Q 与余数 R；语法 [Q,R] = quorem(A,B,x) 视 A,B 为关于变量 x 的多项式。

余数 R 的次数 < 除式 B 的次数。与 deconv 的区别：quorem 面向符号表达式（直接用 x），deconv 面向系数向量。若只需商或余，可分别用 Q = quorem(A,B,x) 或 [~,R] = quorem(A,B,x)

【实战示例】本题：求有理分式

$$
R(x) = \frac{(3x^3 + x)(x^3 + 1/2)}{(x^2 + 2x - 2)(5x^3 + 2x^2 + 1)}
$$

的商多项式与余多项式。

符号法（推荐）

```matlab
syms x
N = (3*x^3 + x)*(x^3 + 1/2);                % 被除式
D = (x^2 + 2*x - 2)*(5*x^3 + 2*x^2 + 1);    % 除式
N = expand(N); D = expand(D);

[Q,R] = quorem(N, D, x);     % Q: 商  R: 余
Q = simplify(Q); R = simplify(R);

% 校验：应为 0
simplify(N - (Q*D + R))
```

计算结果：

- 商多项式：$Q(x) = \tfrac{3}{5}x - \tfrac{36}{25}$
- 余多项式：$R(x) = \tfrac{547}{25}x^4 - \tfrac{267}{50}x^3 - \tfrac{138}{25}x^2 + \tfrac{229}{50}x - \tfrac{72}{25}$

并且 $\deg R < \deg D$。

系数向量法（deconv，数值）

```matlab
% 按降幂写系数
n1 = [3 0 1 0];           % 3x^3 + x
n2 = [1 0 0 0.5];         % x^3 + 0.5
d1 = [1 2 -2];            % x^2 + 2x - 2
d2 = [5 2 0 1];           % 5x^3 + 2x^2 + 1

N = conv(n1, n2);
D = conv(d1, d2);
[q, r] = deconv(N, D);    % q: 商系数, r: 余系数（去掉前导零）
```

得到的 q、r 与上面 $Q(x),R(x)$ 一致（数值形式）。

函数的命名：quorem = quotient and remainder，商与余数。
conv = convolution，卷积（多项式乘法）。deconv = deconvolution，反卷积（多项式除法）。

23. fzero函数

```matlab
% 语法
x = fzero(fun, x0);          % 给定初值，寻找附近的实根
x = fzero(fun, [a,b]);       % 在[a,b]内寻根（要求 fun(a)*fun(b)<0）
[x,fval,exitflag,output] = fzero(fun, x0, options);

% 基本示例：解 cos(x) - x = 0
fun = @(x) cos(x) - x;
root1 = fzero(fun, 0.5);     % 0.739085...
root2 = fzero(fun, [0,1]);   % 提供变号区间，更稳健

% 带参数的函数：解 x^3 - a = 0（实根）
a = 2;
root = fzero(@(x) x.^3 - a, [0, a]);  % 2 的立方根

% 设置精度与输出
options = optimset('TolX',1e-12,'Display','off');
[x,fval,exitflag,output] = fzero(fun, 0.5, options);
```

要点：

- 作用：求一元实函数 fun(x) 的实零点（最近/区间内的一个根）。
- 初值与区间：
  - 传标量 x0：fzero 会先试图在 x0 附近自动寻找变号区间再收敛。
  - 传区间 [a,b]：要求 fun(a) 与 fun(b) 异号，通常更可靠。
- 只支持标量自变量；多元或方程组请用 fsolve。
- 可能算法：二分法、割线法、反二次插值的组合；返回 fval≈0 表示成功。
- 常用选项：TolX（根的容差）、Display（迭代信息）。

常见问题：

- 区间不变号会报错或难以收敛；先画图或扫点确定变号区间更稳。
- 只找实根；若需复根用 roots 或符号方法。

24. try-catch函数

```matlab
try
    % 可能出错的代码
catch
    % 错误处理代码
end

```

25. sqrt函数

```matlab
y = sqrt(x);
```

计算x的平方根，并将结果存储在变量y中。

26. axis函数

```matlab
plot(x,y);
axis([xmin xmax ymin ymax]);          % 设置二维坐标范围
axis([xmin xmax ymin ymax zmin zmax]);% 三维范围
axis tight;    % 范围收缩到刚好包含全部数据
axis auto;     % 恢复自动调整
axis manual;   % 固定当前范围，不随后续绘制改变
axis equal;    % x、y 轴单位长度比例一致
axis square;   % 绘图区域设为正方形
axis image;    % 等比例 + 紧贴数据（常用于显示图像/矩阵）
axis off;      % 隐藏坐标轴（仅显示内容）
axis on;       % 显示坐标轴
axis ij;       % y 轴向下为正（图像坐标习惯）
axis xy;       % 恢复默认（y 向上为正）
```

27. subplot 函数  
作用：在同一 Figure 中把绘图区划分为 m×n 的网格，在第 p 个格子里创建/激活坐标轴，便于多图对比。

基本语法

```matlab
subplot(m, n, p)            % p 从 1 开始，按“从左到右、从上到下”编号
subplot(m, n, [p1 p2 ...])  % 让一个子图跨越多个格子
ax = subplot(...);          % 返回坐标轴句柄，便于定制
```


28. mesh 与 surf 的区别与用法（对比）
- 本质：
  - mesh：线框网格（wireframe），只画网格线，不填充面。
  - surf：实体曲面（surface），有面片，可着色、光照、透明。
- 输入（尺寸需一致）：
  - mesh(Z) 或 mesh(X,Y,Z) 或 mesh(X,Y,Z,C)
  - surf(Z) 或 surf(X,Y,Z) 或 surf(X,Y,Z,C)
  - 只有 Z 时，X=1:n，Y=1:m 默认生成规则网格。
- 视觉与性能：
  - mesh 更轻量，适合快速检查数据形状；边界清晰但不连贯填充。
  - surf 更直观，可配合 shading/lighting/camlight 做平滑、光照与透明，适合展示。
- 常用参数：
  - surf(...,'EdgeColor','none') 去网格线，仅显示平滑面。
  - surf(...,'FaceAlpha',0.6) 透明度；lighting gouraud; camlight headlight。
  - mesh(...,'MeshStyle','row'/'column'/'both') 控制绘制行/列网格线。
- 适用场景：
  - 探索调试：mesh
  - 汇报展示/需要光照与平滑色彩：surf
- 易错点：
  - 计算 Z 时用逐元素运算（.^、.*、./）。
  - X、Y、Z 尺寸一致；若用向量 x,y，则 Z 的大小应为 [length(y) × length(x)]（可用 meshgrid 或隐式扩展得到）。

示例：同一数据的 mesh 与 surf 对比
```matlab
x = linspace(0,2*pi,50);
y = linspace(0,2*pi,50);
[X,Y] = meshgrid(x,y);
Z = sin(X).*cos(Y);

figure;
subplot(1,2,1);
mesh(X,Y,Z);
title('mesh 线框网格'); xlabel x; ylabel y; zlabel z; axis tight; grid on;

subplot(1,2,2);
surf(X,Y,Z);
shading interp;                 % 面片颜色插值更平滑
lighting gouraud; camlight headlight;
title('surf 实体曲面'); xlabel x; ylabel y; zlabel z; axis tight; grid on; colorbar;
```

29. size函数
```matlab
[m,n] = size(A);   % 获取矩阵 A 的行数 m 和列数 n
d = size(A, dim);  % 获取矩阵 A 在指定维度 dim 上的大小
eg: n = size(A, 1);  % 获取矩阵 A 的行数
```

30. str2func函数
```matlab
fhandle = str2func(funcName);
```
将字符串funcName转换为函数句柄fhandle，以便动态调用函数。

31. fminsearch函数
```matlab
% 语法
x = fminsearch(fun, x0);    % 从初始点 x0 寻找函数 fun 的局部最小值点
[]
```

32. lasterr函数
```matlab
msg = lasterr;
```
命名：lasterr = last error，表示“最后的错误”。
显示出错的原因

33. max函数

```matlab
X = max(A);                 % 若 A 为矩阵，得到每列最大值（沿第1维）
[m,idx] = max(A);           % 同时返回最大值的行索引（每列一个）
m = max(A,[],dim);          % 沿 dim 维（dim=1 列；dim=2 行；更高维同理）
m = max(A,[], 'all');       % 所有元素的最大值 (R2018b+)
```

34. mean函数
```matlab
m = mean(X);                   % 向量整体均值；矩阵按列均值（沿第1维）
m = mean(X, dim);              % 沿指定维度 dim 求均值（1=列，2=行，…）
m = mean(X, 'all');            % 所有元素的均值（R2018b+）
m = mean(X, dim, 'omitnan');   % 忽略 NaN（默认 includenan 会得到 NaN）
```

要点：

- 向量：返回该向量的均值；矩阵：返回每列均值的行向量；N 维数组：沿第一个非单一维。
- NaN 处理：用 'omitnan' 忽略缺失值。
- 逻辑数组：mean 返回为 true 的比例。
- 与 sum/size 关系：mean(X,dim) ≈ sum(X,dim) ./ size(X,dim)（忽略 NaN 时需用有效计数）。

示例：

```matlab
X = [1 2 3; 4 5 NaN; 7 8 9];

mean(X)                   % -> [4 5 NaN]  按列
mean(X,2)                 % -> [2; NaN; 8] 按行
```

34. std函数
```matlab
s = std(X);                   % 向量整体标准差；矩阵按列标准差（沿第1维）
s = std(X, dim);              % 沿指定维度 dim 求标准差（1=列，2=行，…）
s = std(X, 0, dim);           % 使用 N-1 作为分母（默认）；0 表示样本标准差 
```

35. corrcoef函数
- 命名：correlation coefficient 的缩写，表示“相关系数”。
- 作用：计算输入数据矩阵各列之间的 Pearson 相关系数矩阵及其显著性水平（p 值）。
```matlab
[R, P] = corrcoef(A);   %输出 R：相关系数矩阵（对角线为 1）。
输出 P：与 R 同型的 p 值矩阵（对角线为 0）。
R = corrcoef(A); % 仅输出相关系数矩阵。
```

36. 插值函数
- interp1：一维插值
  - 'nearest'：最近邻插值
  - 'linear'：线性插值
  - 'spline'：三次样条插值
  - 'cubic'：三次插值
- interp2：二维插值
  - 'nearest'：最近邻插值
  - 'linear'：双线性插值
  - 'cubic'：三次插值
```matlab
% 一维插值示例
f_linear  = interp1(x, f, x_interp, 'linear');  % 线性
f_nearest = interp1(x, f, x_interp, 'nearest'); % 阶梯，不连续
f_spline  = interp1(x, f, x_interp, 'spline');  % 三次样条，最平滑但可能过冲
f_cubic   = interp1(x, f, x_interp, 'cubic');   % 三次插值，平滑但可能过冲

% 二维插值示例
F_linear  = interp2(X, Y, F, Xq, Yq, 'linear');  % 双线性
F_nearest = interp2(X, Y, F, Xq, Yq, 'nearest'); % 最近邻
F_cubic   = interp2(X, Y, F, Xq, Yq, 'cubic');   % 三次插值
``` 
![interp](image.png)


37. 拟合函数
- polyfit：多项式拟合
  ```matlab
  p = polyfit(x, y, n); % 拟合 n 次多项式，返回系数向量 p
  ```
- polyval：多项式评估
  ```matlab
  y_fit = polyval(p, x_fit); % 计算多项式 p 在 x_fit 处的值
  ```

- polyder：多项式求导
  ```matlab
  p_der = polyder(p); % 计算多项式 p 的导数，返回导数的系数向量 p_der
  ```

命名：polyfit = polynomial fit，多项式拟合；polyval = polynomial evaluate，多项式评估，polyder = polynomial derivative，多项式求导。

38. 匿名函数
```matlab
f = @(x) x.^2 + 2*x + 1;  % 定义匿名函数 f(x) = x^2 + 2x + 1
y = f(3);                  % 调用函数，计算 f(3)
```

39. 大小写转换
  -upper函数
  ```matlab
  str = 'hello world';
  str_upper = upper(str);  % 转换为大写字母
  ```
命名：upper = upper case，大写。
  -lower函数
  ```matlab
  str = 'HELLO WORLD';
  str_lower = lower(str);  % 转换为小写字母
  ```
命名：lower = lower case，小写。
  -isstrprop函数
  ```
  lower_count = sum(isstrprop(str, 'lower'));% 计算小写字母个数
  ```
  命名：isstrprop = is string property，判断字符串属性。

40. sum函数：
```matlab
sum(A);                   % 计算数组 A 的所有元素之和
sum(A, dim);              % 沿指定维度 dim 求和（1=列，2=行，…）·
```

41. simulink常用模块
- 常用模块：
  - 信号生成模块：Sine Wave（正弦波）、Step（阶跃）、Constant（常数）、Pulse Generator（脉冲发生器）
  - 数学运算模块：Gain（增益）、Sum（求和）、Product（乘法）、Math Function（数学函数）、sqrt（平方根）
  - 逻辑模块：Logical Operator（逻辑运算）、Relational Operator（关系运算）
  - 显示与记录模块：Scope（示波器）
  - 控制系统模块：Transfer Fcn（传递函数）
  - continuous模块：Integrator（积分器）、Derivative（微分器）

42. ode45函数
```matlab
% 语法
[t, y] = ode45(odefun, tspan, y0);
```
- odefun：定义微分方程的函数句柄，形式为 dydt = odefun(t, y)。
- tspan：时间区间 [t0, tf]。
- y0：初始条件。

43. integral函数
```matlab
result = integral(fun, a, b);
```
- fun：被积函数的函数句柄，形式为 y = fun(x)。
- a, b：积分区间的下限和上限。
- 命名：integral = 积分。

43. eig函数
```matlab
[V, D] = eig(A);
```
- V：特征向量矩阵，每列为一个特征向量。
- D：特征值矩阵，对角线为特征值。

44. imag函数
```matlab
y = imag(z);
```
- 作用：返回复数 z 的虚部。

45. any函数
```matlab
b = any(A);
```
- 作用：检查数组 A 中是否存在非零元素，返回逻辑值 true 或 false。

46. num2str函数
```matlab
str = num2str(num);
```
- 作用：将数值 num 转换为字符串 str。

47. str2func函数
```matlab
fhandle = str2func(funcName);
eg:% 定义目标函数（字符串形式）
fun_str = '-exp(-x)*abs(sin(sin(x)))';
% 转换为可被fminsearch调用的函数句柄
fun = str2func(['@(x) ' fun_str]);
```
- 将字符串funcName转换为函数句柄fhandle，以便动态调用函数。

48. input函数
```matlab
user_input = input(prompt);
```
- 作用：显示提示信息 prompt，等待用户输入，并将输入存储在变量 user_input 中。

49. poly2sym函数
```matlab
syms x;   % 定义符号变量 x
p = [1 0 -4]; % 多项式系数
f = poly2sym(p, x);
```
- 作用：将多项式系数向量 p 转换为符号表达式 f。

## 选修：
![alt text](image-1.png)
![alt text](image-2.png)
![alt text](image-3.png)
   
[^1]: 此人很帅