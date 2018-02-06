# jongleaw

#DB creation
create table booking_info(bookingid integer,date varchar(10),room_num varchar(10),start_time varchar(6),end_time varchar(6),booked_by varchar(10),invitees varchar(80));
create table room_profile(room_num varchar(10),room_loc varchar(20));
create table room_utilize(bookingid integer,chkin_time varchar(6),chkout_time varchar(6),utilize_status varchar(20));
create table invitor_credit(date varchar(10),invitor varchar(10),credit integer,credit_act varchar(10),act_reason varchar(20));

#Sample data population
insert into booking_info values(10000,'02022018','1101','09:00','10:00','tk15570','rt45323:jk34234:tr67345:uo21475:er45421');
insert into booking_info values(10001,'02022018','1102','09:00','10:00','we23423','sd23475:wn124234:uy345856:pu45742:ng34521');
