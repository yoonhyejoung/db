# db

>데이터베이스 접속
$ mysql -u 사용자 명 - dbname

설치 직후에는 root 사용자에 비밀번호가 없으므로 다음과 같이 접속하여 MySQL을 관리할 수 있다.

$ mysql -u root mysql

>비밀번호 변경
mysql을 설치한 직후에는 root계정에 암호가 지정되어 있지 않다.
세가지 방법으로 비밀번호를 변경 할 수 있다.


1. mysqladmin을 이용
     $ mysqladmin -u root password 새 비밀번호
     
     
2. update문을 이용
     $ mysql -u root mysql
     mysql> UPDATE user SET password=password("새 비밀번호") WHERE user='root';
     mysql> FLUSH PRIVLEGES;
     
     
3. Setpassword 이용
    SET PASSWORD ROT root=password("새 비밀번호");
    
일단 root 비밀번호가 설정된 상태에서는 mysql이나 mysqladmin 명령을 실할 할 때 -p 옵션을 붙여주고 기존 비밀번호를 입력해야만 한다.

>사용자 추가/삭제

명령어   mysql> GRANT ALL PRIVILEGES ON dbname.*TO username@localhost IDENTFIE BY 'password';
        mysql> FLUSH PRIVILEGES;
        
        
