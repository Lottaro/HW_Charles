# Домашнее задание по Charles  
  
[Ex_0](#0)  
[Ex_1](#1)  
[Ex_2](#2)  
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
В *Body* приходит ответ  
![Ex_1 0 Postman](https://user-images.githubusercontent.com/51506930/180841877-28d57eff-34e9-45df-b469-68ad17bdcff9.jpg)  
  
Переходим в *Charles*. В меню нажимаем *Tools*, далее из списка выбираем *Rewrite* и откроется *Rewrite settings*  
![Ex_1 1](https://user-images.githubusercontent.com/51506930/180850847-6885bfab-4bb0-4ec4-90b7-7ae9efade953.jpg)  
  
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
  *Value*: **Lottaro**  
Нажимаем *Ok*  
![Ex_1 6](https://user-images.githubusercontent.com/51506930/180852862-eb398e58-2cb0-4b86-a06e-09eb8948d493.jpg)  
   
Снова нажимаем в правой нижней части окна *Rewrite settings* кнопку *Add*, откроется окно *Rewrite Rule*  
В графе *Type* выбираем **Modify Query Param**  
В области *Match* вписываем данные:  
  *Name*: **age**  
  *Value*: **36**  
В области *Replace* вписываем данные:  
  *Name*: **age**  
  *Value*: **37**  
Нажимаем *Ok*  
![Ex_1 7](https://user-images.githubusercontent.com/51506930/180852934-dd014126-714a-4119-a452-389190aaf709.jpg)  
  
Заходим в **Postman**, выбираем **EP_1_1** из домашней работы **HW_Postman_1** и отправляем запрос нажав *Send*  
В *Body* приходит ответ:  
![Ex_1 1 Postman](https://user-images.githubusercontent.com/51506930/180853053-0c7eb71e-5f1a-4325-a1f2-9c53f642c54e.jpg)  
  
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
![Ex_1 4 Breakpoint](https://user-images.githubusercontent.com/51506930/180854149-b50d01ed-2195-4868-a3a5-cb27b843170a.jpg)  
  
В этом окне видим измененный запрос  
![Ex_1 5 Breakpoint](https://user-images.githubusercontent.com/51506930/180854087-349baea3-b3e6-49d1-8a45-b74d56455dca.jpg)  
  
Нажимаем *Execute* отправляя запрос далее. В **Postman** в *Body* приходит ответ  
![Ex_1 1 Postman](https://user-images.githubusercontent.com/51506930/180854012-b208daea-27dc-458f-8410-cabd3f285f15.jpg)  
  
  ***  
  
## **Charles Ex_2**<a name="2"><a>  
```
Method: POST
EndPoint: /user_info_3
request form data: 
 name: str
 age: int
 salary: int

response: 
{'name': name,
          'age': age,
          'salary': salary,
          'family': {'children': [['Alex', 24], ['Kate', 12]],
                     'u_salary_1_5_year': salary * 4}}

Task:
Сделать и в Rewrite, и в BreakPoint (можно отключить чтобы не стопило на каждом запросе)
 ⁃ Подменить body в Charles так чтобы в запросе ушла salary которую вы вписали в Postman, а в u_salary_1_5_year цифра вернулась меньше оригинальной из запроса.
```  
 Заходим в **Postman**, выбираем **EP_1_2** из домашней работы **HW_Postman_1** и отправляем запрос нажав *Send*  
В *Body* приходит ответ  
![Ex_2 1 Postman](https://user-images.githubusercontent.com/51506930/180856769-6a267736-15ef-4656-a8ea-7c40e4b084b0.jpg)  
  
Переходим в *Charles*. В меню нажимаем *Tools*, далее из списка выбираем *Rewrite* и откроется *Rewrite settings*  
![Ex_1 1](https://user-images.githubusercontent.com/51506930/180850847-6885bfab-4bb0-4ec4-90b7-7ae9efade953.jpg)  
  
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
   
В графе *Type* выбираем **Body**  
В области *Match* вписываем данные:  
  *Value*: **60000**  
В области *Replace* вписываем данные:  
  *Value*: **50000**  
Нажимаем *Ok*  
![Ex_2 6 Rewrite](https://user-images.githubusercontent.com/51506930/180858408-a2007d9f-de29-4fd4-98d6-44d20c31c635.jpg)  
  
  Заходим в **Postman**, выбираем **EP_1_1** из домашней работы **HW_Postman_1** и отправляем запрос нажав *Send*  
В *Body* приходит ответ:  
![Ex_2 2 Postman](https://user-images.githubusercontent.com/51506930/180859097-51da8dd8-417b-46d0-85ad-1779f5cbb51a.jpg)  
  
### Функция **BreakPoint**
В *Charles*, в меню нажимаем *Proxy*, далее из списка выбираем *Breakpoint Settings* и откроется *Breakpoint Settings*  
![Ex_1 1 Breakpoint](https://user-images.githubusercontent.com/51506930/180837332-2fc138de-0926-48cd-aafc-aff63ca12a6b.jpg)  
  
Ставим галочку в *Enable Breakpoint* и нажимаем кнопку *Add*, которая распологается ниже, откроется окно *Edit Breakpoint*  
![Ex_2 2 Breakpoint](https://user-images.githubusercontent.com/51506930/180860768-c3dfa969-f6ac-4e6a-b928-ecf8ce91b0a0.jpg)  
  
Вписываем данные:  
*Scheme*: **POST**  
*Protocol*: **http**  
*Host*: **162.55.220.72**  
*Port*: **5005**  
*Path*: **/user_info_3**  
Ставим галочку в чекбокс *Request*  
Нажимаем *Ok*  
![Ex_2 3 Breakpoint](https://user-images.githubusercontent.com/51506930/180861355-fa3c2b1b-5ae8-4e73-8cd5-76b2fc6529e6.jpg)  

