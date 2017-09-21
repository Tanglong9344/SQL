# Orcal 常用函数 <h3 id="abstract"></h3>
### 目录
+ [to_char()函数](#toChar)
+ [to_date()函数](#toDate)

### 测试表 <h3 id="testTable"></h3>
+ [测试表1](#testTable1)

+ ### <h3 id="toChar">to_char()函数</h3> [返回目录](#abstract)
```
select t.name as 姓名,
       t.study_date as 入学日期,
       to_char(t.study_date, 'yyyy-MM-dd') as 入学年月,
       to_char(t.study_date, 'HH24:MI:SS') as 入学时间
  from ORCAL_TEST t;
```
### 执行结果
![toChar](https://github.com/Tanglong9344/SQL/blob/master/Orcal/picture/toChar.png)

+ ### <h3 id="toDate">to_date()函数</h3> [返回目录](#abstract)
```
select t.name as 姓名,
       t.birth_date as 出生日期,
       to_date(t.birth_date, 'yyyy-MM-dd') as 出生年月
  from ORCAL_TEST t;
```
### 执行结果
![toDate](https://github.com/Tanglong9344/SQL/blob/master/Orcal/picture/toDate.png)

+ ### <h3 id="testTable1">测试表1</h3> [返回目录](#testTable)
```
-- Create table
create table ORCAL_TEST
(
  name       VARCHAR2(10) not null,
  birth_date VARCHAR2(30) not null,
  study_date DATE
)
tablespace DATASERVER
  pctfree 10
  initrans 1
  maxtrans 255
  storage
  (
    initial 64K
    next 1M
    minextents 1
    maxextents unlimited
  );
-- Add comments to the table 
comment on table ORCAL_TEST
  is '测试用表';
-- Add comments to the columns 
comment on column ORCAL_TEST.name
  is '姓名';
comment on column ORCAL_TEST.birth_date
  is '出生日期';
comment on column ORCAL_TEST.study_date
  is '入学日期';

 -- insert data
insert into ORCAL_TEST (name, birth_date, study_date)
values ('小绿','1999-08-09',to_date('2017-09-01 11:11:03','yyyy-mm-dd HH24:MI:SS'));
insert into ORCAL_TEST (name, birth_date, study_date)
values ('小强','1998-04-19',to_date('2017-09-02 10:31:11','yyyy-mm-dd HH24:MI:SS'));
insert into ORCAL_TEST (name, birth_date, study_date)
values ('小刀','1999-11-23',to_date('2017-09-05 13:45:34','yyyy-mm-dd HH24:MI:SS'));
insert into ORCAL_TEST (name, birth_date, study_date)
values ('小红','2000-01-01',to_date('2017-09-03 12:01:06','yyyy-mm-dd HH24:MI:SS'));
```
### 完成后显示结果
![测试表1](https://github.com/Tanglong9344/SQL/blob/master/Orcal/picture/testTable1.png)