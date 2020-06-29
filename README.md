# 用强化学习MADDPG算法模拟多智能体的竞争与合作

## 仿真环境：openai的‘multiagent-particle-envs’环境
 



### "simple_tag" 场景

* simple_tag场景，有3红1绿总共4个智能体，红绿智能体相互对抗
* 绿色的agent在保证不离开视野的情况下，尽可能避免与3个红色智能体碰撞。
* 红色的agent通过协同行为与绿色agent发生碰撞。

### "simple_world_comm" 场景

* simple_world_comm场景，有4红2小绿总共6个智能体，黑色圆代表不能通过的障碍物，2个蓝色圆为food，2个大绿圆为森林。
* 绿色的agent通过靠近食物来获取奖励，速度较快，数量较少。
* 红色的agent需要有一定协同能力，通过阻碍good_agent获取奖励，速度较慢，但数量较多。


 
## 安装

`pip install paddlepaddle==1.6.3          #如果使用gpu可选安装paddlepaddle-gpu==1.6.3.post97`\
`pip install parl==1.3.1`\
`pip install gym==0.10.5`\
 [multiagent-particle-envs](https://github.com/openai/multiagent-particle-envs)

## 如何开始

 修改train.py文件，然后 python train.py --env [ENV_NAME]   开始测试或者训练你自己的模型。
 训练完成后使用 python train.py --env [ENV_NAME] --show --restore 展示动画效果。
 
 

## tips：

* 在MADDPG中，每个Agent的Critic输入除自身的state-action信息外，还可以有额外的信息，比如其他Agent的动作

* 不同的Agent之间的关系大体可以分为三种，合作型，对抗性，半合作半对抗型，可以根据不同的合作关系来设计他们的奖励函数
