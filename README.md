# Hyperledger-study-27

하이퍼레져 앱 만들기 실습 27일차 - 데이터 가공

1. 가공할 데이터 = JSON.stringify(data)

        {"Key":"CAR0","Record":{"colour":"blue","make":"Toyota","model":"Prius","owner":"Tomoko"}}{"Key":"CAR1","Record":{"colour":"red","make":"Ford","model":"Mustang","owner":"Brad"}}{"Key":"CAR11","Record":{"colour":"1","make":"car","model":"1","owner":"CAR12"}}{"Key":"CAR2","Record":{"colour":"green","make":"Hyundai","model":"Tucson","owner":"Jin Soo"}}{"Key":"CAR3","Record":{"colour":"yellow","make":"Volkswagen","model":"Passat","owner":"Max"}}{"Key":"CAR4","Record":{"colour":"black","make":"Tesla","model":"S","owner":"Adriana"}}{"Key":"CAR5","Record":{"colour":"purple","make":"Peugeot","model":"205","owner":"Michel"}}{"Key":"CAR6","Record":{"colour":"white","make":"Chery","model":"S22L","owner":"Aarav"}}{"Key":"CAR7","Record":{"colour":"violet","make":"Fiat","model":"Punto","owner":"Pari"}}{"Key":"CAR8","Record":{"colour":"indigo","make":"Tata","model":"Nano","owner":"Valeria"}}{"Key":"CAR9","Record":{"colour":"brown","make":"Holden","model":"Barina","owner":"Shotaro"}}
 
2. 원하는 데이터의 형태
 
        1번째 자동차
        자동차 : CAR0, 컬러 : blue, 제조사 : Toyota, 모델 : Prius, 소유주 : Tomoko
        
3. 
 
3. split 사용 = JSON.stringify(data[0]).split('"');
 
         {Key:CAR0,Record:{colour:blue,make:Toyota,model:Prius,owner:Tomoko}}
 
4. 데이터 가공 = data[0] 일 때 

        var total = JSON.stringify(data[0]).split('"');
                  var total = [
                  " 자동차 : " + total[3] 
                  + ", 컬러 : " + total[9] 
                  + ", 제조사 : " + total[13] 
                  + ", 모델 : " + total[17] 
                  + ", 소유주 : " + total[21]
                  ]
                
5. 데이터 추가 = total_a = total_a + total;

6. for문 사용

              var total = '';
              var total_a = '';
              for(var i=0; i < data.length; i++)
              {
                var total = JSON.stringify(data[i]).split('"');
                var total = [
                " 자동차 : " + total[3] 
                + ", 컬러 : " + total[9] 
                + ", 제조사 : " + total[13] 
                + ", 모델 : " + total[17] 
                + ", 소유주 : " + total[21]
                ]
                var total_a = total_a + total;
                document.write(total_a);
              }
        
 7. 출력 결과 보기
 
        1번째 자동차
        자동차 : CAR0, 컬러 : blue, 제조사 : Toyota, 모델 : Prius, 소유주 : Tomoko
        2번째 자동차
        자동차 : CAR1, 컬러 : red, 제조사 : Ford, 모델 : Mustang, 소유주 : Brad
        3번째 자동차
        자동차 : CAR11, 컬러 : 1, 제조사 : car, 모델 : 1, 소유주 : CAR12
        4번째 자동차
        자동차 : CAR2, 컬러 : green, 제조사 : Hyundai, 모델 : Tucson, 소유주 : Jin Soo
        5번째 자동차
        자동차 : CAR3, 컬러 : yellow, 제조사 : Volkswagen, 모델 : Passat, 소유주 : Max
        6번째 자동차
        자동차 : CAR4, 컬러 : black, 제조사 : Tesla, 모델 : S, 소유주 : Adriana
        7번째 자동차
        자동차 : CAR5, 컬러 : purple, 제조사 : Peugeot, 모델 : 205, 소유주 : Michel
        8번째 자동차
        자동차 : CAR6, 컬러 : white, 제조사 : Chery, 모델 : S22L, 소유주 : Aarav
        9번째 자동차
        자동차 : CAR7, 컬러 : violet, 제조사 : Fiat, 모델 : Punto, 소유주 : Pari
        10번째 자동차
        자동차 : CAR8, 컬러 : indigo, 제조사 : Tata, 모델 : Nano, 소유주 : Valeria
        11번째 자동차
        자동차 : CAR9, 컬러 : brown, 제조사 : Holden, 모델 : Barina, 소유주 : Shotaro    
