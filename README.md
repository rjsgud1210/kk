erd-sql

-----------------------------------
------------Not Smoking-----------

------drop table 
drop table somke_historys;

drop table users;

drop table types;

drop table sexs;

drop table groups;

---------Create


create table groups(usergroupid number(1), gname varchar(10),
constraint g_pk primary key(usergroupid)
);

create table sexs(sexid number(1), us varchar(5),
constraint s_pk primary key(sexid)
);

create table types(typeid number(1), sname varchar(10), constraint t_pk primary key(typeid)); 

create table users(userid number(1), userphone number(10), usergroupid number(1), sexid number(1),
constraint u_pk primary key(userid),
constraint u_fk foreign key(usergroupid) references groups (usergroupid),
constraint u_fk2 foreign key(sexid) references sexs (sexid)
);

 create table smoke_historys( userid number(1),smokeday date, Smokeid number(1), usedmoney number(6), lastsmoke date, totalsmoke number(5), typeid number(1),
 	constraint s_pk2 primary key(Smokeid),
 	constraint s_fk foreign key(typeid) references types (typeid),
 	constraint s_fk2 foreign key(userid) references users (userid)
 );
 

---------Insert
insert into groups values(1,'A');
insert into sexs values(1,'male');
insert into types values(1,'this');
insert into users values(1,01097989887,1,1);
<!--insert into  smoke_historys(1,2014-07-31,1,100,2014-07-30,1,1);-->


---------select

select * from tab;

commit;
