数组操作主要设计排序, 归类, 查找这三大类

排序主要是快排等等具体见排序算法文件夹

连续区域的归类, 其核心是扩充已分类集合, 一般需要维护2个下标(左右指针left right)
	
	若将所有数分为两类
		可以从左向右扩充集合,左边的扩充好了右边也自然好了.
			一般来说是左边主动扩充(主动推进,发现不合适的就与右指针交换), 
			也有被动扩充: 右指针向左指针写符合要求的值.
		也可以左右同时扩充集合, 最终停止时, 先推进的会与另外一方重合, 具体可见快排的partition部分.
	
	若只想圈住数组中的连续某一类那就关心这一类即可但要注意边界.
	
	这里的实现细节的核心在于先找到集合扩充的倾向也就是迭代条件.
	一旦迭代, 已经扩充的集合就不用操心, 只用关心当前的左右指针的动作.这时再思考递进的边界:
	不要超过数组范围以及不与他人重合.

查找:
对于排序数组常常二分查找, 查找任意一个指定值很简单, 但是查找左右边界就很难, 这就要已左闭右开的观点看问题.具体见二分查找文件夹.