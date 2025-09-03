# ⚡ k6 Testing Project

## 📖 Описание
Това репо съдържа **performance и load тестове**, написани с помощта на [k6](https://k6.io/).  
Целта е да се демонстрира как да се:
- Направи **load test** на REST API или уеб приложение
- Събират метрики за latency, response time и throughput
- Анализират резултати за оптимизация на системи

---

## 🛠️ Използвани технологии
- **k6** – модерен инструмент за performance testing
- **JavaScript/ES6** – за писане на тест скриптовете
- **Node.js** (за допълнителни интеграции)
- **GitHub** – версия контрол и споделяне

---

## 🚀 Как да стартираш тестовете

1. **Инсталирай k6:**
   - Linux / macOS:
     ```bash
     brew install k6
     ```
   - Windows:
     [Свали от k6.io](https://k6.io/docs/getting-started/installation/)

2. **Клонирай репото:**
   ```bash
   git clone https://github.com/malkiqmuki/k6Testing.git
   cd k6Testing

3. Стартирай теста:
   k6 run script.js
   Заместваме script.js с конкретния тестов файл от проекта.

4.Генериране на отчет:
  k6 run --out json=results.json script.js
  След това можеш да анализираш резултатите или да ги качиш в Grafana/InfluxDB.


✅ Примерен тест (script.js)
import http from 'k6/http';
import { sleep, check } from 'k6';

export let options = {
  vus: 10,           // 10 виртуални потребителя
  duration: '30s',   // тест за 30 секунди
};

export default function () {
  let res = http.get('https://test-api.example.com/');
  check(res, {
    'status is 200': (r) => r.status === 200,
  });
  sleep(1);
}

🔥 Идеи за надграждане

Добавяне на GitHub Actions workflow за автоматично изпълнение на тестовете
Интеграция с Grafana за визуализации
По-сложни сценарии (Ramp-Up, Soak Testing, Stress Testing)
Поддръжка на CSV входни данни за тестовете

👨‍💻 Автор
GitHub: malkiqmuki
