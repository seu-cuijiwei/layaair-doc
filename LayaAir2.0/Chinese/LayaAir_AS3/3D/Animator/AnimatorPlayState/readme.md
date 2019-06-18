# 动画播放状态获取

###### *version :2.1.0beta   Update:2019-6-13*

获取动画播放状态，只需要使用Animator的**getCurrentAnimatorPlayState**方法。

![](img/1.png)<br>(图1)

获得后的`AnimatorPlayState` ：

![](img/2.png)<br>(图2)

##### 当动画为非循环播放时

如注释所写的相同当动画为**非循环**（非循环模式）播放的时候这个 normalizedTime会返回一个0.0~1的数1就是代表当前动画已经播放到百分之百也就是已经播放完成了，这个数就是可以理解为当前动画播放的百分比，0.1就是当前播放到百分之10了。

##### 当动画为循环播放时

这个值会在每遍播放完成后+1也就是说整数位为当前播放动画播放完成了多少次，而小数位为当前正在播放的动画的百分比。比如循环动画循环播放了3次了那这个数就应该是3.0当第四次播放到一半时这个数就应该为3.5。