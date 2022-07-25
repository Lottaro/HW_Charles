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
```json
[
    "Sergey",
    "36"
]
```
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
```json
[
    "str",
    "int"
]
```
  
  ***
  
### Функция **BreakPoint**
