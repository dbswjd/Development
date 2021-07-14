# JDBC (Java DataBase Connectivity)
Java에서 데이터베이스에 접속할 수 있도록 하는 JAVA API
데이터베이스에서 자료를 쿼리하거나 업데이트 하는 방법 제공

## JDBC Flow
1. JDBC Driver 로드
2. DB 연결
3. DB에 데이터를 읽거나 쓰기 (SQL문)
4. DB 연결 종료 

# DBCP (DataBase Connection Pool)
DB와 connection을 맺고 있는 객체 관리 
WAS가 실행되면서 미리 일정량의 DB Connection 객체를 생성하고 Pool이라는 공간에 저장
저장된 DB Connection 객체는 요청에 따라 필요할 때마다 Pool에서 가져다 쓰고 반환
=> 요청할 때마다 DB Driver에 로드하여 물리적인 Connection 객체를 생성하는 비용이 줄어들음


