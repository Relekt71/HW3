# Домашнее задание к занятию 15 «Система сбора логов Elastic Stack»

  ##Состав стека
  
    Сервис	            Имя контейнера	  Роль
    Elasticsearch Hot	  es-hot	          master + data_hot
    Elasticsearch Warm	es-warm	          data_warm
    Logstash	          logstash	        Приём JSON на порту 5000/TCP
    Kibana	            kibana	          Визуализация, порт 5601
    Filebeat	          filebeat	        Сбор логов контейнеров Docker
    Генератор логов	    dummy-logger	    Тестовый JSON в stdout

  ## Запуск стека

    # Запустить все сервисы
    docker compose up -d
    # Проверить статус контейнеров
    docker ps

  ## Результаты выполнения

  Скриншот 1: docker ps (все 6 контейнеров работают)
  
  <img width="1181" height="263" alt="2026-05-22_16-26-21" src="https://github.com/user-attachments/assets/b464554a-7c4d-4c44-9835-73d80846476a" />

  Скриншот 2: Kibana Discover (отображение логов)

  <img width="1539" height="812" alt="2026-05-22_17-04-58" src="https://github.com/user-attachments/assets/02af946b-d4fb-4431-9894-033f56a1cb8a" />

      Создан Index Pattern: logstash-*
      
      Поле времени: @timestamp
      
      Отображаются логи с полями:
      
      @timestamp
      
      message (содержит "random event")
      
      parsed (содержит value)


