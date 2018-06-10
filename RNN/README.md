# RNN

## 一、从一个例子讲起

假设我们现在要做一个智能的订票系统，它的功能是：用户说一句话，比如系统自动识别地点和时间等信息，然后通过这些信息进行自动订票。

这个功能可以怎么做？很简单，我们可以设置一些固定的槽（slot），比如时间槽，地点槽等。然后统去识别用户输入的语句中关于这些槽的具体的内容是什么，然后填满就好了。填满了之后，根据这些信息系统就可以自动订票了。这种方法叫做slot filling。

现在我们关注怎么去识别一个句子当中拥有哪些槽内容呢？

神经网络

我们把句子中的每个单词都用一个向量来表示，然后把它输入到一个全连接网络中，判断它是属于哪个槽。比如输入台北这个词，那么网络判断为地点槽。但这样有一个问题，就是，如果我 们的句子分别是，，，那判断结果是一样的，但实际上由于arrive和leavezheng好相反。所以网络需要记忆，不仅仅由一个单词就做决定。



## 二、RNN

如果我们在之前的全连接网络中加上记忆，也就是说把隐藏层的输出给储存起来，然后在下一个单词输出的时候，再将其输出到它的隐藏层加起来，那这样就把前一个单词的信息带到了后一个单词中。

举个例子：



如果将RNN网络展开的话，就是这个样子的：




