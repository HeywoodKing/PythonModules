## python random模块

```
random.random()     (0, 1)----float   大于0且小于1之间的小数
random.randint(1, 10)       [1, 10]    大于等于1且小于等于10之间的整数
random.randrange(1, 10)     [1, 10]    大于等于1且小于10之间的整数
random.choice([1, '23', [4, 5]])      1或者23或者[4,5]
random.sample([1, '23', [4, 5]], 2))    列表元素任意2个组合
random.uniform(1, 3)                 大于1小于3的小数，如1.927109612082716
random.shuffle([1,3,5,7,9])    打乱[1,3,5,7,9]的顺序,相当于"洗牌"
```