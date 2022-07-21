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
    “Str”,
    “Str”
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
