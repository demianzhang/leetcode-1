> 和上一题不同，这一题中，候选数组中可能包含相同的元素

对于一个数字，同样是使用或不使用两种选择，考虑候选数组[10,1,2,7,6,1,5]，排序后，数组为[1,1,2,5,6,7,10]，如果只通过递归来处理每个数使用或不使用这两种情况，那么当：

* 第一个1使用，第二个1不使用
* 第一个1不使用，第二个1使用

这两种情况就会产生冗余

因此，这里不能单纯的只使用递归来实现，需要结合迭代：

* **迭代**：从头到尾遍历候选数组的中的每个元素，对于位置i的元素，有2个种可能：
    1. 位置i的元素和位置i-1的元素相等。此时直接跳过位置i的元素，否则会与前一次处理产生冗余
    2. 位置i的元素和位置i-1的元素不相等，此时需要处理位置i的元素
* **递归**：对于迭代过程中需要处理的元素，假设使用这个元素，然后递归，对后续子候选数组进行相同的处理

在迭代中，当遍历至位置i时，表示位置i之前的元素都不使用。因为在遍历i之前的元素时，已经处理了所有包含这些元素的子数组了，因此不需要再重复考虑相同的情况


