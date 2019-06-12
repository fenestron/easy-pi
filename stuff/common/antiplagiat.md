## Просмотр полного отчета антиплагиата из LMS

Заходим в LMS и переходим по ссылкам: Главная -> ВКР/КР -> работа
Попадаем на страницу с адресом вида
`https://lms.hse.ru/?ap&h_id=2D089658-D642-4BF5-B1...`
Заменяем в адресе `ap` на `apview` и получаем адрес вида
`https://lms.hse.ru/?apview&h_id=2D089658-D642-4BF...`
Переходим по этому адресу.

На открывшейся странице открываем инструменты разработчика и переходим на  вкладку с JS-консолью (в Chrome такая вкладка называется Console).
Вводим в консоль этот код, выполняем. Страница с отчётом откроется сама.

```val = document.getElementById('id_row_ap_result_percent').getElementsByClassName('fa-search')[0].getAttribute('onclick').match(/\d+/)[0],$.ajax({url: `/ap_service.php?ap_id=${val}`, success(newUrl) {window.open(newUrl)}})```
