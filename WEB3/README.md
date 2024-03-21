# WEB3

1. Заходим на http://192.168.12.11:8001/flag получаем 403, 
2. Далее ставим в конце ссылки / и получаем ошибку Not found! 
3. Передаем в параметр name нагрузку: ``` http://192.168.12.11:8001/flag/?name={%25cat%20flag.txt%25} ``` 
4. Отправляем 3000 запросов, в одном из них будет флаг и http-код 200

В ходе решения мы выяснили что используется Jinja2 Template в коде, мы передавали в параметр name {{7 * 7}}, потом заменяли на другие значения, но получали 49, когда уже забыли про {{7 * 7}}. Мы пытались написать код в строке чтобы вывести что-нибудь - у нас выводилось 7.
И потом после кучи попыток мы ввели в параметр name: {%25cat%20flag.txt%25} и нам выдало флаг!

## Очень вероятно, что мы перегрузили наш сервер, и нам выдало флаг по случайности.