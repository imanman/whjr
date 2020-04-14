# whjr 排课规则

## 背景：
  固定分班模式，以班级为颗粒度，报名的学员按照班级的课表上课。

## 公共排课规则-冲突，所有机构都一样：
* 一个老师在同一时间，只在一个班级上课。
* 一个教室在同一时间，只有一个班级使用。
* 一个班级在同一时间，只有一个老师，只用一个教室。
* 教室的容量>=班级人数。

## 巨人排课规则

### 老师
* 强性限制条件：老师都有各自的级别，每个级别带班量的有个上限值。（S，A级别的老师带班会多一些，新人老师带班会少一些，避免影响教学效果）
* 强性限制条件：老师当天不跨校区，只在一个校区上课。
* 跨校区逻辑（强制性条件）：一个老师对应1个或者多个行政区（相邻的行政区可以设置成多个），1个行政区下面有多个校区，老师只能上这些校区的课。如：张老师A，只能在行政区武侯区的3个校区上课。


### 教室
* 强制限定条件：教室的统一不可用时间，如果某个教室还有一些单独的不可用时间，可以单独设置 比如：A校区教室A1，从12:30 - 13:30不可用
* 强制限定条件：如果一个班级是续报过来的，那么他之前所在的教室需要沿用过来。


### 班级
* 强制限定条件：每个班级可以上课的时间：周一到周五，还是周末班，还是一三五还是二四六等，或者隔一天上等。
* 弱性限定条件：班级A上课时间期望时间：上午的10:00~11:45 或者 晚上的18:00~20:00。
* 强制限定条件：班级对应的课程：总课时，一共几次课，每次课时间，开课时间。
* 强制限定条件：一个班级如果是续班属性，那么他的上课时间需要跟以前保持一致。
* 强制限定条件：每堂课中间休息15分钟

### 搭配班级
* 弱性限定条件：某个校区，某个班要跟某个班搭课，尽量排在一起。


### 老师跟班级的匹配关系
* 4升5的续报班级，如果老师能上新班型的课，直接平移过来，不能上新班型的课，换其他老师能够匹配的该班型。
* 老师是有level属性，level越高，级别越高。多个老师可以上同一班型的课时，级别高的优先排课。

### 老师跟班型的关系
* 老师跟班型有对应关系，一共老师可以匹配多个班型，每个班型对应着多个班级
* 1个老师对应的班型数<=2个，防止备课太大


### 合班逻辑
* 在预排阶段，同年级、同层次、同科目的班级 人数低于? 人的，需要进行合并处理，进行排课。




