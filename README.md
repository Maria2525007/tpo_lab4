# Лабораторная работа 4 — нагрузочное и стресс-тестирование

ИТМО, «Тестирование программного обеспечения», 3 курс.

JMeter-планы для сравнения трёх конфигураций сервера под нагрузкой
(`load_test.jmx` — ступенчатое увеличение до 30 пользователей,
`stress_test.jmx` — поиск точки отказа) против `${HOST}:${PORT}`
(по умолчанию `localhost:8079`). Каждый запрос проверяется на допустимую
длительность (assertion на 640 мс) — в `results/*.jtl` видно, какие
конфигурации укладываются в порог, а какие нет.

Результаты прогонов — `results/config1_load.jtl`, `config2_load.jtl`,
`config3_load.jtl`, `load_all.jtl`, `stress_config3.jtl`. Полный лог —
`jmeter.log`.

## Запуск

```bash
jmeter -n -t load_test.jmx -l results/load_all.jtl -JHOST=localhost -JPORT=8079
```
