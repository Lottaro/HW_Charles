# Домашнее задание по Charles  
  
[Ex_0](#0)  
[Ex_1](#1)  
[Ex_2]  
[Ex_3]  
[Ex_4]  
[Ex_5]  
[Ex_6]  
  
  ***  
  
## **Charles Ex_0**<a name="0"><a>
### Функция **Rewrite**
```
Сфокусироваться на ниже перечисленных запросах:  
Protocol: http  
IP: 162.55.220.72  
Port: 5005  
```  
Отправляем запрос в **Postman** из домашнего задания по **Postman**, где использовались такие же  
параметры. После это в **Charles** в *Structure* выбираем из списка http://162.55.220.72:5005,  
вызываем контекстное меню и из списка *Focus*  
  
## **Charles Ex_1**<a name="1"><a>  
```  
Method: GET
EndPoint: /get_method
request url params: 
 name: str
 age: int

response: 
[
    “str”,
    “int”
]

Task:
Сделать и в Rewrite, и в BreakPoint (можно отключить чтобы не стопило на каждом запросе)
 ⁃ Подменить url в Charles чтобы в запросе ушло имя которые вы вписали в Postman, а вернулось то, которое вы подставили в Charles.
```
Заходим в **Postman**, выбираем **EP_1_1** из домашней работы **HW_Postman_1** и отправляем запрос нажав *Send*  
В *Body* приходит ответ:  
![Ex_1 0 Postman](https://user-images.githubusercontent.com/51506930/180841877-28d57eff-34e9-45df-b469-68ad17bdcff9.jpg)  
  
Переходим в *Charles*. В меню нажимаем *Tools*, далее из списка выбираем *Rewrite* и откроется *Rewrite settings*  
![Ex_1 1](https://user-images.githubusercontent.com/51506930/180311980-6b0fd0e7-80c5-4b23-85ec-1318749801e5.jpg)  
  
Ставим галочку в *Enable Rewrite* и нажимаем кнопку *Add*, которая распологается ниже  
![Ex_1 2](https://user-images.githubusercontent.com/51506930/180829543-7c61cc77-3f83-4f9e-8a44-12c7dfdae7bd.jpg)  
  
Далее в правой верхней части окна нажимаем кнопку *Add*, откроется окно *Edit Location*  
![Ex_1 3](https://user-images.githubusercontent.com/51506930/180830812-853b2193-e4eb-414e-a546-92217d8ed553.jpg)  
  
Вписываем данные:  
*Protocol*: **http**  
*Host*: **162.55.220.72**  
*Port*: **5005**  
*Path*: **/get_method**  
 Нажимаем *Ok*  
![Ex_1 4](https://user-images.githubusercontent.com/51506930/180830942-d4c13bab-8052-4c0a-8e85-b089b8349790.jpg)  
  
Жмем в правой нижней части окна *Rewrite settings* кнопку *Add*, откроется окно *Rewrite Rule*  
![Ex_1 5](https://user-images.githubusercontent.com/51506930/180831686-7bfe72a9-8863-410a-9796-2536975baf10.jpg)  
  
В графе *Type* выбираем **Modify Query Param**  
В области *Match* вписываем данные:  
  *Name*: **name**  
  *Value*: **Sergey**  
В области *Replace* вписываем данные:  
  *Name*: **name**  
  *Value*: **str**  
Нажимаем *Ok*  
![Ex_1 6](https://user-images.githubusercontent.com/51506930/180833190-b02b1492-adcf-4b9f-a73e-50b71ee988b9.jpg)  
  
Снова нажимаем в правой нижней части окна *Rewrite settings* кнопку *Add*, откроется окно *Rewrite Rule*  
В графе *Type* выбираем **Modify Query Param**  
В области *Match* вписываем данные:  
  *Name*: **age**  
  *Value*: **36**  
В области *Replace* вписываем данные:  
  *Name*: **age**  
  *Value*: **int**  
Нажимаем *Ok*  
![Ex_1 7](https://user-images.githubusercontent.com/51506930/180834280-ea833e10-91bc-4760-b184-98517a0c7eb9.jpg)  

Заходим в **Postman**, выбираем **EP_1_1** из домашней работы **HW_Postman_1** и отправляем запрос нажав *Send*  
В *Body* приходит ответ:  
![Ex_1 1 Postman](https://user-images.githubusercontent.com/51506930/180841369-d01c5ea5-5a20-4cb1-b6c3-7680e1e798f5.jpg)
  
### Функция **BreakPoint**
В *Charles*, в меню нажимаем *Proxy*, далее из списка выбираем *Breakpoint Settings* и откроется *Breakpoint Settings*  
![Ex_1 1 Breakpoint](https://user-images.githubusercontent.com/51506930/180837332-2fc138de-0926-48cd-aafc-aff63ca12a6b.jpg)  
  
Ставим галочку в *Enable Breakpoint* и нажимаем кнопку *Add*, которая распологается ниже, откроется окно *Edit Breakpoint*  
![Ex_1 2 Breakpoint](https://user-images.githubusercontent.com/51506930/180837938-70a2b17f-ccbd-4588-bde4-1b8bc8002508.jpg)  
  
Вписываем данные:  
*Scheme*: **GET**  
*Protocol*: **http**  
*Host*: **162.55.220.72**  
*Port*: **5005**  
*Path*: **/get_method**  
Ставим галочку в чекбокс *Request*  
 Нажимаем *Ok*  
![Ex_1 3 Breakpoint](https://user-images.githubusercontent.com/51506930/180839158-397dfcf4-fb57-43e3-91d0-70af1315f74c.jpg)  
  
Заходим в **Postman**, выбираем **EP_1_1** из домашней работы **HW_Postman_1** и отправляем запрос нажав *Send*  
В *Body* идет ожидание запроса так как **Charles** перехватил запрос. В **Charles** открывается окно *Breakpoints* в котором мы открываем вкладку *Edit Request*  
![Ex_1 4 Breakpoint](https://user-images.githubusercontent.com/51506930/180840024-a6891902-56ac-4448-8373-dd09bd8a9cea.jpg)  
  
В этом окне вы виде уже измененный запрос  
![Ex_1 5 Breakpoint](https://user-images.githubusercontent.com/51506930/180840316-5cbcc93f-f29d-461a-802f-22d9439db18e.jpg)  
  
Нажимаем *Execute* отправляя запрос далее. В **Postman** в *Body* приходит ответ:  
![Ex_1 1 Postman](https://user-images.githubusercontent.com/51506930/180841451-a850cbbe-9f1e-4971-b55d-26023be529d5.jpg)  

