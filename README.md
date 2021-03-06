1. 代码重构，使用Pinyin4J 的拼音数据库。
2. 如果输入的字符不是汉字，则会抛出异常。

## 用法
```
// 设置拼音输出格式
PinyinOutputFormat format = new PinyinOutputFormat(ToneFormat.WITHOUT_TONE, CaseFormat.LOWERCASE, VCharFormat.WITH_U_UNICODE);
char hanzi = '李';
// 判断是否是汉字
if(PinyinUtil.IsHanzi(hanzi)){
    return;
}
// 取出指定汉字的所有拼音
string[] py = Pinyin4Net.GetPinyin(hanzi);
// 取出指定汉字的所有拼音（经过格式化的）
string[] py = Pinyin4Net.GetPinyin(hanzi, format);
// 取指定汉字的唯一或者第一个拼音
Pinyin4Net.GetUniqueOrFirstPinyin(hanzi);
// 取指定汉字的唯一或者第一个拼音（经过格式化的）
Pinyin4Net.GetUniqueOrFirstPinyinWithFormat(hanzi, format);
// 根据拼音查汉字
string[] hanzi = Pinyin4Net.GetHanzi('li', true);
```

## 更新日志

#2016-04-27
- 添加.net2.0分支，主分支使用.net4.0
- 清理未使用的using，优化代码结构

#2015-12-26 2.0.1
- 清理冗余代码
- 将拼音数据库放进资源文件，编译到dll中，这样在使用此库时直接引用dll就可以了，不再需要管数据库。


#2015-11-12 2.0.0

- 代码重构，仅使用Pinyin4J 的拼音数据库，提供更简单的使用接口。
- 如果输入的字符不是汉字，则会抛出异常。
- 添加拼音首字母大写选项。
- 添加只取拼音首字母功能。
- 添加根据拼音找汉字功能。

#2015-11-09 1.0.2
- 添加WEB演示项目
- 修复了一些BUG