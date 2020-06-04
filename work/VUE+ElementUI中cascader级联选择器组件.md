# 级联选择器组件置空
## 1、
    let obj = {}
    obj.stopPropagation = () => {}
    try{
        this.$refs.cascader.clearValue(obj)
    }catch(err){
        this.$refs.cascader.handleClear(obj)
    }
## 2、让cascader绑定的值改变的时候，改变options的key值，使cascader组件重新渲染
    参考：https://blog.csdn.net/qq_34451048/article/details/106198550?utm_medium=distribute.pc_relevant.none-task-blog-BlogCommendFromMachineLearnPai2-1.nonecase&depth_1-utm_source=distribute.pc_relevant.none-task-blog-BlogCommendFromMachineLearnPai2-1.nonecase
    给 el-cascader 绑定一个key值 :key="isResouceShow"
    然后在data中初始化一下这个isResouceShow值，比如让他等于0
    接下来只需要在清空的时候，让++ this.isResouceShow自增就ok了
