create database beauty;
use beauty;

create table `user`(
    `idx` int(11) NOT NULL AUTO_INCREMENT COMMENT '키',
    uid varchar(40),
    upw varchar(50) not null,
    uname varchar(20) not null,
    uage int,
    uaddress varchar(130) not null,
    umobile varchar(20) not null,
    `point` int,
    `roleName` varchar(128) DEFAULT 'ROLE_USER' COMMENT '권한(ROLE_USER)',
  PRIMARY KEY (`idx`)
);
create table shop(
   `idx` int(11) NOT NULL AUTO_INCREMENT COMMENT '키',
    stype char(10) not null,
    sname varchar(40) not null,
    sphone varchar(20) not null,
    saddress varchar(130) not null,
    sinfo varchar(130),
    simg varchar(130),
    price int not null,
    `view` int default 0,
  PRIMARY KEY (`idx`)
);
create table reservation(
    `idx` int(11) NOT NULL AUTO_INCREMENT COMMENT '키',
    uidx int not null ,
    sidx int not null,
    `date` varchar(40) not null,
    `time` varchar(40) not null,
    deposit int not null,
  PRIMARY KEY (`idx`),
  foreign key (uidx) references user (idx),
  foreign key (sidx) references shop (idx)
);
create table review(
    `idx` int(11) NOT NULL AUTO_INCREMENT COMMENT '키',
    uidx int not null ,
    sidx int not null,
    `comment` varchar(1024),
    writeTime timestamp not null default now(),
  PRIMARY KEY (`idx`),
  foreign key (uidx) references user (idx),
  foreign key (sidx) references shop (idx)
);




INSERT INTO `user` (uid,upw,uname,uage,uaddress,umobile,point) values ('user1','pw1234','김수지','21','서울', '01011223344', 100000);
INSERT INTO `user` (uid,upw,uname,uage,uaddress,umobile,point) values ('user2','pw1234','이지연','24','춘천', '01044332211', 100000);
INSERT INTO `user` (uid,upw,uname,uage,uaddress,umobile,point) values ('user3','pw1234','박나경','27','부산', '01012341234', 100000);
INSERT INTO `user` (uid,upw,uname,uage,uaddress,umobile,point) values ('user4','pw1234','최현주','32','대전', '01043214321', 100000);
INSERT INTO `user` (uid,upw,uname,uage,uaddress,umobile,point) values ('user5','pw1234','문채영','36','보령', '01013244231', 100000);

INSERT INTO shop (stype,sname,sphone,saddress,sinfo,simg,price,`view`) values ('헤어','예쁨온헤어','0312223333','서울','당신의 머리를 더욱 아름답게 가꿔드립니다~','/img/hair_1.jpg',30000,12);
INSERT INTO shop (stype,sname,sphone,saddress,sinfo,simg,price,`view`) values ('헤어','엔스헤어살롱','0514325677','부산','건강한 아름다움을 드리는 엔스헤어살롱입니다.','/img/hair_2.jpg',50000,51);
INSERT INTO shop (stype,sname,sphone,saddress,sinfo,simg,price,`view`) values ('헤어','라포즈','0531112222','대구','대구 최고의 열펌, 아이롱펌, 특수컬러 전문시술 살롱입니다.','/img/hair_3.jpg',20000,3);
INSERT INTO shop (stype,sname,sphone,saddress,sinfo,simg,price,`view`) values ('헤어','카멜레온','0428887756','대전','고객 만족을 위해 최선을 다하겠으며, 아름다움과 멋스러움을 연출해드리겠습니다.','/img/hair_4.jpg',80000,7);
INSERT INTO shop (stype,sname,sphone,saddress,sinfo,simg,price,`view`) values ('헤어','데이지헤어비스','0423325514','대전','합리적인 가격에 1:1 맞춤 시술!','/img/hair_5.jpg',90000,24);
INSERT INTO shop (stype,sname,sphone,saddress,sinfo,simg,price,`view`) values ('헤어','루아헤어','026428671','서울','언제나 휴식하러 오는 마음이실 수 있도록 최선을 다하겠습니다!','/img/hair_6.jpg',150000,32);
INSERT INTO shop (stype,sname,sphone,saddress,sinfo,simg,price,`view`) values ('헤어','살롱드헤브론','0625426875','광주','확실한 제품, 최고의 실력으로 항상 만족드리겠습니다~','/img/hair_7.jpg',110000,17);
INSERT INTO shop (stype,sname,sphone,saddress,sinfo,simg,price,`view`) values ('헤어','건앤로빈스','0538756948','대구','디자이너 1:1 시술 시스템! 최고의 서비스 건앤로빈스!','/img/hair_8.jpg',210000,9);
INSERT INTO shop (stype,sname,sphone,saddress,sinfo,simg,price,`view`) values ('헤어','허준헤어','025687595','서울','모발이 손상되었다면 크리닉보다 복구펌 추천드립니다.','/img/hair_9.jpg',180000,42);
INSERT INTO shop (stype,sname,sphone,saddress,sinfo,simg,price,`view`) values ('헤어','조으다헤어','0625876934','광주','광주 시내에 위치한 조으다헤어입니다. 환영합니다!','/img/hair_10.jpg',160000,27);

INSERT INTO shop (stype,sname,sphone,saddress,sinfo,simg,price,`view`) values ('네일','네일트리','021234567','서울','서울 내 가장 저렴한 네일샵입니다!','/img/nail_1.jpg',60000,52);
INSERT INTO shop (stype,sname,sphone,saddress,sinfo,simg,price,`view`) values ('네일','유니끄네일','0425877632','대전','전문적인관리로 최상의 서비스를 만끽해보세요.','/img/nail_2.jpg',50000,23);
INSERT INTO shop (stype,sname,sphone,saddress,sinfo,simg,price,`view`) values ('네일','네일706','0531459862','대구','드릴케어로 좀 더 섬세하게 해드려요.','/img/nail_3.jpg',50000,31);
INSERT INTO shop (stype,sname,sphone,saddress,sinfo,simg,price,`view`) values ('네일','네일핏','0518795647','부산','건식케어 방법으로 고객님의 손톱건강을 도와드립니다.','/img/nail_4.jpg',100000,35);
INSERT INTO shop (stype,sname,sphone,saddress,sinfo,simg,price,`view`) values ('네일','네일데이','0625879945','광주','친절하고 잘하는 곳으로 오세요~','/img/nail_5.jpg',80000,4);
INSERT INTO shop (stype,sname,sphone,saddress,sinfo,simg,price,`view`) values ('네일','데일리플랜','0625789634','광주','약해진 손톱, 발톱 케어받으러 오세요.','/img/nail_6.jpg',70000,8);
INSERT INTO shop (stype,sname,sphone,saddress,sinfo,simg,price,`view`) values ('네일','네일라보떼','024231568','서울','이쁜아트 받아보러 오세요~','/img/nail_7.jpg',60000,16);
INSERT INTO shop (stype,sname,sphone,saddress,sinfo,simg,price,`view`) values ('네일','네일사이','0421587963','대전','빠른 유행에 적합한 매달 디자인 변경!','/img/nail_8.jpg',50000,28);
INSERT INTO shop (stype,sname,sphone,saddress,sinfo,simg,price,`view`) values ('네일','러블리네일','0516589632','부산','가성비 좋은 아트비용으로 스트레스 풀러오세요','/img/nail_9.jpg',50000,43);
INSERT INTO shop (stype,sname,sphone,saddress,sinfo,simg,price,`view`) values ('네일','루미가넷','0532589756','대구','꼼꼼하고 철저한 관리로 고객님을 맞이하고 있습니다.','/img/nail_10.jpg',80000,41);

INSERT INTO shop (stype,sname,sphone,saddress,sinfo,simg,price,`view`) values ('마사지','777체형관리','0511234567','부산','뭉친 근육을 시원하게 풀어드립니다~','/img/massage_1.png',100000,56);
INSERT INTO shop (stype,sname,sphone,saddress,sinfo,simg,price,`view`) values ('마사지','다온타이&아로마','0621573458','광주','쾌적하고 편안한 관리해드려요','/img/massage_2.png',150000,43);
INSERT INTO shop (stype,sname,sphone,saddress,sinfo,simg,price,`view`) values ('마사지','7DAYS','0532456871','대구','여드름, 홍조, 깊은주름을 케어해드립니다.','/img/massage_3.png',130000,18);
INSERT INTO shop (stype,sname,sphone,saddress,sinfo,simg,price,`view`) values ('마사지','그린','0515789632','부산','20년 경력의 스페셜리스트가 직접케어 합니다.','/img/massage_4.png',150000,23);
INSERT INTO shop (stype,sname,sphone,saddress,sinfo,simg,price,`view`) values ('마사지','하얀피부스킨케어','027895486','서울','1대1 맞춤 솔루션 100%예약제로 운영합니다.','/img/massage_5.png',50000,34);
INSERT INTO shop (stype,sname,sphone,saddress,sinfo,simg,price,`view`) values ('마사지','더뷰티샵','0423568648','대전','명품 스킨케어로 매끈한 피부로 바꿔드립니다.','/img/massage_6.png',70000,18);
INSERT INTO shop (stype,sname,sphone,saddress,sinfo,simg,price,`view`) values ('마사지','케이테라피','0628971234','광주','피부를 건강하게 피부타입별로 관리해드려요.','/img/massage_7.png',100000,1);
INSERT INTO shop (stype,sname,sphone,saddress,sinfo,simg,price,`view`) values ('마사지','에이스체형관리','0536547897','대구','심신안정, 몸매교정이 가능합니다.','/img/massage_8.png',50000,9);
INSERT INTO shop (stype,sname,sphone,saddress,sinfo,simg,price,`view`) values ('마사지','오예쁘다','023698547','서울','신체 상,하 발란스 리듬을 맞추어 통증완화 시켜드려요','/img/massage_9.png',110000,15);
INSERT INTO shop (stype,sname,sphone,saddress,sinfo,simg,price,`view`) values ('마사지','퀸스킨케어','0425879634','대전','신경조율에 효과있는 아로마관리','/img/massage_10.png',80000,23);


insert into review (uidx, sidx, comment) values (1,5,'사장님 엄청 친절하시고 헤어도 완전 잘 나왔어요ㅜㅜ 짱!');
insert into review (uidx, sidx, comment) values (3,5,'저는 좀 별로였어요... 친절하시긴 하시지만 가게가 조금 지저분한 느낌...');
insert into review (uidx, sidx, comment) values (2,15,'네일맛집ㅜㅜ 이번 신상 자개네일 완전 추천이요! 사무실에서도 예쁘다고 난리예요~');
insert into review (uidx, sidx, comment) values (4,6,'뿌염하러 갔었는데 끝난줄도 몰랐어요... 실장님 완전 손 빠르심.');
insert into review (uidx, sidx, comment) values (5,26,'사장님 손맛 장난 아니에요... 완전 딱딱어깨로 들어갔는데 나올때는 아기어깨... 추천드립니다.');
insert into review (uidx, sidx, comment) values (1,26,'진짜 짱이엥ㅅ요... 저는 실장님께 마사지 받았는데 직장스트레스가 뽝!');
insert into review (uidx, sidx, comment) values (2,1,'어릴 때부터 다니던 헤어샵이라 편안하네요... 역시 앞머리는 사장님께 맡기는게 맘편한...');
