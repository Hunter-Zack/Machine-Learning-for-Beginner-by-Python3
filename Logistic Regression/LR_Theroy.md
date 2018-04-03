# LR_Theroy

+ **逻辑回归问题说明**

有<img src="http://latex.codecogs.com/gif.latex?N" title="N" />个样本，<img src="http://latex.codecogs.com/gif.latex?(X_{i},&space;Y_{i}),&space;i\in&space;(1,2\cdots&space;N)" title="(X_{i}, Y_{i}), i\in (1,2\cdots N)" />，<img src="http://latex.codecogs.com/gif.latex?X_{i}&space;=&space;[X_{i}^{1},&space;X_{i}^{2},&space;\cdots&space;X_{i}^{m-1}]" title="X_{i} = [X_{i}^{1}, X_{i}^{2}, \cdots X_{i}^{m-1}]" />， 表示每个样本有<img src="http://latex.codecogs.com/gif.latex?m-1" title="m-1" />个特征；<a href="http://www.codecogs.com/eqnedit.php?latex=Y_{i}&space;=0\begin{matrix}&space;&&space;or&space;&&space;1&space;\end{matrix}" target="_blank"><img src="http://latex.codecogs.com/gif.latex?Y_{i}&space;=0\begin{matrix}&space;&&space;or&space;&&space;1&space;\end{matrix}" title="Y_{i} =0\begin{matrix} & or & 1 \end{matrix}" /></a>。
 
现在为每个样本添加一个特征值为1的特征，也就是令<a href="http://www.codecogs.com/eqnedit.php?latex=X_{i}&space;=&space;[X_{i}^{1},X_{i}^{2},\cdots&space;X_{i}^{m-1},X_{i}^{m}]" target="_blank"><img src="http://latex.codecogs.com/gif.latex?X_{i}&space;=&space;[X_{i}^{1},X_{i}^{2},\cdots&space;X_{i}^{m-1},X_{i}^{m}]" title="X_{i} = [X_{i}^{1},X_{i}^{2},\cdots X_{i}^{m-1},X_{i}^{m}]" /></a>，其中<a href="http://www.codecogs.com/eqnedit.php?latex=X_{i}^{m}&space;=&space;1" target="_blank"><img src="http://latex.codecogs.com/gif.latex?X_{i}^{m}&space;=&space;1" title="X_{i}^{m} = 1" /></a>。这样操作本质就是将<a href="http://www.codecogs.com/eqnedit.php?latex=w*X&space;&plus;&space;b" target="_blank"><img src="http://latex.codecogs.com/gif.latex?w*X&space;&plus;&space;b" title="w*X + b" /></a>中的<a href="http://www.codecogs.com/eqnedit.php?latex=w" target="_blank"><img src="http://latex.codecogs.com/gif.latex?w" title="w" /></a>和<a href="http://www.codecogs.com/eqnedit.php?latex=w" target="_blank"><img src="http://latex.codecogs.com/gif.latex?b" title="b" /></a>合为一个<a href="http://www.codecogs.com/eqnedit.php?latex=W" target="_blank"><img src="http://latex.codecogs.com/gif.latex?W" title="W" /></a>，便于计算。

<a href="http://www.codecogs.com/eqnedit.php?latex=Sigmoid" target="_blank"><img src="http://latex.codecogs.com/gif.latex?Sigmoid" title="Sigmoid" /></a>函数形式为：

<a href="http://www.codecogs.com/eqnedit.php?latex=\Phi(x)=\frac{1}{1&plus;e^{-x}}" target="_blank"><img src="http://latex.codecogs.com/gif.latex?\Phi(x)=\frac{1}{1&plus;e^{-x}}" title="\Phi(x)=\frac{1}{1+e^{-x}}" /></a>

要使得到的<a href="http://www.codecogs.com/eqnedit.php?latex=W" target="_blank"><img src="http://latex.codecogs.com/gif.latex?W" title="W" /></a>满足：

<a href="http://www.codecogs.com/eqnedit.php?latex=\Phi(X_{i}\cdot&space;W)&space;=&space;\begin{cases}&space;\geq&space;0.5&space;&&space;\text{&space;if&space;}&space;Y_{i}=1&space;\\&space;<&space;0.5&space;&&space;\text{&space;if&space;}&space;Y_{i}=0&space;\end{cases}" target="_blank"><img src="http://latex.codecogs.com/gif.latex?\Phi(X_{i}\cdot&space;W)&space;=&space;\begin{cases}&space;\geq&space;0.5&space;&&space;\text{&space;if&space;}&space;Y_{i}=1&space;\\&space;<&space;0.5&space;&&space;\text{&space;if&space;}&space;Y_{i}=0&space;\end{cases}" title="\Phi(X_{i}\cdot W) = \begin{cases} \geq 0.5 & \text{ if } Y_{i}=1 \\ < 0.5 & \text{ if } Y_{i}=0 \end{cases}" /></a>

我们令

<a href="http://www.codecogs.com/eqnedit.php?latex=P(Y_{i}=1|X_{i},&space;W)=\Phi&space;(X_{i}\cdot&space;W)\\&space;P(Y_{i}=0|X_{i},&space;W)=1&space;-&space;\Phi&space;(X_{i}\cdot&space;W)\\" target="_blank"><img src="http://latex.codecogs.com/gif.latex?P(Y_{i}=1|X_{i},&space;W)=\Phi&space;(X_{i}\cdot&space;W)\\&space;P(Y_{i}=0|X_{i},&space;W)=1&space;-&space;\Phi&space;(X_{i}\cdot&space;W)\\" title="P(Y_{i}=1|X_{i}, W)=\Phi (X_{i}\cdot W)\\ P(Y_{i}=0|X_{i}, W)=1 - \Phi (X_{i}\cdot W)\\" /></a>

其中<a href="http://www.codecogs.com/eqnedit.php?latex=P(Y_{i}=1|X_{i},&space;W)" target="_blank"><img src="http://latex.codecogs.com/gif.latex?P(Y_{i}=1|X_{i},&space;W)" title="P(Y_{i}=1|X_{i}, W)" /></a>表示对于给定的<a href="http://www.codecogs.com/eqnedit.php?latex=W" target="_blank"><img src="http://latex.codecogs.com/gif.latex?W" title="W" /></a>和<a href="http://www.codecogs.com/eqnedit.php?latex=X_{i}" target="_blank"><img src="http://latex.codecogs.com/gif.latex?X_{i}" title="X_{i}" /></a>， 得出的<a href="http://www.codecogs.com/eqnedit.php?latex=Y_{i}&space;=&space;1" target="_blank"><img src="http://latex.codecogs.com/gif.latex?Y_{i}&space;=&space;1" title="Y_{i} = 1" /></a>的概率。将上面两个式子合在一起：

<a href="http://www.codecogs.com/eqnedit.php?latex=P(Y&space;=&space;Y_{i}|(X_{i},W))&space;=&space;\Phi&space;(X_{i}\cdot&space;W)^{Y_{i}}\times&space;(1-\Phi&space;(X_{i}\cdot&space;W)^{1-Y_{i}}" target="_blank"><img src="http://latex.codecogs.com/gif.latex?P(Y&space;=&space;Y_{i}|(X_{i},W))&space;=&space;\Phi&space;(X_{i}\cdot&space;W)^{Y_{i}}\times&space;(1-\Phi&space;(X_{i}\cdot&space;W)^{1-Y_{i}}" title="P(Y = Y_{i}|(X_{i},W)) = \Phi (X_{i}\cdot W)^{Y_{i}}\times (1-\Phi (X_{i}\cdot W)^{1-Y_{i}}" /></a>

定义如下的成本函数：



+ **梯度下降推导**

计算代价函数<a href="http://www.codecogs.com/eqnedit.php?latex=\mathit{cost}" target="_blank"><img src="http://latex.codecogs.com/gif.latex?\mathit{cost}" title="\mathit{cost}" /></a>对<a href="http://www.codecogs.com/eqnedit.php?latex=W" target="_blank"><img src="http://latex.codecogs.com/gif.latex?W" title="W" /></a>的梯度：

<a href="http://www.codecogs.com/eqnedit.php?latex=\bigtriangledown&space;\mathit{cost}&space;=&space;\frac{1}{2N}&space;\bigtriangledown&space;\mathit{C}\\&space;...............=\frac{1}{N}(X^{T}\cdot&space;X\cdot&space;W-X^{T}\cdot&space;Y)\\&space;...............=\frac{1}{N}(X^{T}\cdot&space;(X\cdot&space;W&space;-Y))" target="_blank"><img src="http://latex.codecogs.com/gif.latex?\bigtriangledown&space;\mathit{cost}&space;=&space;\frac{1}{2N}&space;\bigtriangledown&space;\mathit{C}\\&space;...............=\frac{1}{N}(X^{T}\cdot&space;X\cdot&space;W-X^{T}\cdot&space;Y)\\&space;...............=\frac{1}{N}(X^{T}\cdot&space;(X\cdot&space;W&space;-Y))" title="\bigtriangledown \mathit{cost} = \frac{1}{2N} \bigtriangledown \mathit{C}\\ ...............=\frac{1}{N}(X^{T}\cdot X\cdot W-X^{T}\cdot Y)\\ ...............=\frac{1}{N}(X^{T}\cdot (X\cdot W -Y))" /></a>

更新<a href="http://www.codecogs.com/eqnedit.php?latex=W" target="_blank"><img src="http://latex.codecogs.com/gif.latex?W" title="W" /></a>：

<a href="http://www.codecogs.com/eqnedit.php?latex=\mathbf{W&space;=&space;W&space;-&space;\boldsymbol{\eta}&space;\times&space;\boldsymbol{\bigtriangledown&space;\mathit{cost}}&space;}" target="_blank"><img src="http://latex.codecogs.com/gif.latex?\mathbf{W&space;=&space;W&space;-&space;\boldsymbol{\eta}&space;\times&space;\boldsymbol{\bigtriangledown&space;\mathit{cost}}&space;}" title="\mathbf{W = W - \boldsymbol{\eta} \times \boldsymbol{\bigtriangledown \mathit{cost}} }" /></a>

其中<a href="http://www.codecogs.com/eqnedit.php?latex=\eta" target="_blank"><img src="http://latex.codecogs.com/gif.latex?\eta" title="\eta" /></a>表示学习率。