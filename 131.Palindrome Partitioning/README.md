对于字符串str,遍历从下标0开始的每一个子串：

* 如果子串[0,i]是回文，则将子串添加到路径，递归处理剩余子串[i+1,n]
* 如果子串[0,i]不是回文，处理下一个子串[0,i+1]
* 如果字符串str为空，表示已经递归处理(dfs)到结尾，那么将这条路径添加到结果中
* 每处理完一条路径，递归返回时，需要将之前添加到路径结尾的回文串[0,i]弹出