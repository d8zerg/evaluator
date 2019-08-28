# evaluator
Test task. Like Measurement Protocol (GA) service.

Необходимо реализовать сервис на Golang для сбора пользовательских метрик метрик (очень простой аналог Google Analytics (Measurement Protocol)). 


* Метрики отсылаются по HTTP с различных других подсистем (в том числе с клиентских браузеров и приложений) часто
* Метрики отсылаются под одной (не батчем)
* Формат тела запроса - на ваше усмотрение, например, можно только тип события слать
* Потеря метрик не критична, но нежелательна
* Метрики нужно складировать в хранилище
* Хранилище - произвольное (достаточно писать в файл в произвольном формате), но, есть ограничение - писать в хранилище нужно не часто и пачками, например, не чаще чем раз в 5 секунд

Хорошо, если ваше решение будет:
* Тестируемое
* Держать нагрузку

Пример запроса для отладки http://localhost:8080/api/v1/catch?t=event&val=7555 

Сбрасывает накопленный кэш в data.csv

Продолжительность кеширования конфигурируется в config.toml
