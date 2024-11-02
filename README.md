# 공통

## DB

- DB 스키마
    1. History(부팅 및 종료기록)
        1. Idx / BigInt : Auto Increment
        2. 등록일 RegDate / DateTime : default currentDate()
        3. 디바이스 Device → Device.macAddress 
        4. 액션타입(Booting/Exit) actType / varchar(20) : not null
    2. License(발급된 라이센스)
        1. Idx / BigInt : Auto Increment
        2. 라이센스 license / varchar(40) : not null
        3. 디바이스 Device → Device.macAddress
        4. 발급일 CreatedAt / DateTime : default currentDate()
        5. 만료일 ExpiredAt / DateTime : nullable
        6. 만료여부 IsExpired / bool: default false 
    3. Device(등록된 디바이스)
        1. Idx / BigInt
        2. macAddress / varchar(30) : not null
        3. 사용여부 IsUsed / bool : default true
    4. ProcessList(화이트&블랙)
        1. Idx / BigInt
        2. 프로세스명 processName / varchar(50) : not null
        3. 블랙/화이트 여부 IsBlack / bool : default true
        4. 등록일 RegDate / DateTime : default CurrentDate()
        5. 자동여부 IsAuto / bool : default false