# WEB2

### У нас было 2 решения. 
## 1 решение:
1. Переходим сюда: http://192.168.12.13:8090/login?password=password 
2. Далее заменяем следующий div (1) на (2):
   1. Error resolving template [flag], template might not exist or might not be accessible by any of the configured Template Resolvers
   2. ```
        <div th:fragment="main">
            <span th:text="'Hello, + ${flag}"></span>
        </div>
      ```
3. Перезагружаем страницу
4. Далее в сообщении ошибки появляется настоящий флаг 
  
## 2 решение
1. Переходим сюда: http://192.168.12.13:8090/login?adminpassword=password 
2. Далее заменяем следующий div (1) на (2):
   1. Error resolving template [flag], template might not exist or might not be accessible by any of the configured Template Resolvers
   2. ```
        <div th:fragment="main">
            <span th:text="'Hello, + ${flag}"></span>
        </div>
      ```
3. Перезагружаем страницу
4. Меняем в ссылке http://192.168.12.13:8090/login?adminpassword=password adminpassword на password, нажимаем enter
5. Далее в сообщении ошибки появляется настоящий флаг 

## Скорее всего сервер провис и нам выдавало флаг по случайности :P
