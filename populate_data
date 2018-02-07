import random
import sqlite3

def create_table_booking_info(db):
    try:
        with sqlite3.connect(db) as con:
            sqlcmd = '''
            DROP TABLE IF EXISTS booking_info;
            CREATE TABLE booking_info(
            booking_id INTEGER PRIMARY KEY AUTOINCREMENT,
            booking_date TEXT,
            room_num TEXT,
            start_time TEXT,
            end_time TEXT,
            booked_by TEXT,
            invitees TEXT);
            '''
            con.executescript(sqlcmd)
    except Exception as e:
        print('Error --> {}'.format(e))


def pop_data_in_booking_info(db,rows = 10):
    invitees_list = ['rt45323','jk34234','tr67345','uo21475','er45421','sd23475','wn124234','uy345856','pu45742','ng34521']
    data = [(
        random.choice(['04022018','05022018']),
        random.choice(['1101','1102','1201','1202','1203','1204']),
        random.choice(['09:00','10:00','11:00']),
        random.choice(['12:00', '13:00', '14:00']),
        random.choice(['tk15570','tj23123']),
        ":".join(random.choices(invitees_list,k=4))
    ) for _ in range(rows)]
    print (data)

    try:
        with sqlite3.connect(db) as con:
            sql_cmd = 'INSERT INTO booking_info(booking_date,room_num,start_time,end_time,booked_by,invitees) VALUES(?,?,?,?,?,?);'
            con.executemany(sql_cmd,data)
    except Exception as e:
        print("Error --> {}".format(e))

def create_table_pop_data_in_room_profile(db):
    try:
        with sqlite3.connect(db) as con:
            sql_cmd = '''
            DROP TABLE IF EXISTS room_profile;
            CREATE TABLE room_profile(
            room_num TEXT,
            room_loc TEXT
            );
            INSERT INTO room_profile VALUES('1101','11_0_1flr11');
            INSERT INTO room_profile VALUES('1102','11_0_2flr11');
            INSERT INTO room_profile VALUES('1201','12_0_1flr12');
            INSERT INTO room_profile VALUES('1202','12_0_2flr12');
            INSERT INTO room_profile VALUES('1203','12_0_3flr12');
            INSERT INTO room_profile VALUES('1204','12_0_4flr12');
            '''
            con.executescript(sql_cmd)
    except Exception as e:
        print("Error --> {}".format(e))


def create_table_room_utilize(db):
    try:
        with sqlite3.connect(db) as con:
            sqlcmd = '''
            DROP TABLE IF EXISTS room_utilize;
            CREATE TABLE room_utilize(
            booking_id INTEGER,
            chkin_date TEXT,
            chkin_time TEXT,
            chkout_time TEXT,
            utilize_status TEXT);
            '''
            con.executescript(sqlcmd)
    except Exception as e:
        print('Error --> {}'.format(e))

if __name__ == '__main__':
    # create_table_booking_info('jongleaw.db')
    # pop_data_in_booking_info('jongleaw.db',10)
    create_table_pop_data_in_room_profile('jongleaw.db')
    create_table_room_utilize('jongleaw.db')
    # print (random.choice(['04022018', '05022018']))
    # invitees_list = ['rt45323', 'jk34234', 'tr67345', 'uo21475', 'er45421', 'sd23475', 'wn124234', 'uy345856',
    #                  'pu45742', 'ng34521']
    # print (random.choices(invitees_list,k=2))
