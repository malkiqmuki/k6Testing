# ⚡ k6 Testing Project

## 📖 Description
This repository contains **performance and load tests** written with [k6](https://k6.io/).  
The goal is to demonstrate how to:
- Perform a **load test** on a REST API or web application
- Collect metrics such as latency, response time, and throughput
- Analyze results for system optimization

---

## 🛠️ Technologies Used
- **k6** – modern performance testing tool  
- **JavaScript/ES6** – for writing test scripts  
- **Node.js** – for additional integrations  
- **GitHub** – version control and collaboration  

---

## 🚀 How to Run the Tests

1. **Install k6:**
   
   - Linux / macOS:
     ```bash
     brew install k6
     ```
   - Windows:  
     [Download from k6.io](https://k6.io/docs/getting-started/installation/)

2. **Clone the repository:**
   
   ```bash
   
   git clone https://github.com/malkiqmuki/k6Testing.git
   
   cd k6Testing

3. **Run a test:**
   
   k6 run script.js
   
   Replace script.js with the specific test file from the project.

4.**Generate a report:**

  k6 run --out json=results.json script.js
  
  Then you can analyze the results or import them into Grafana/InfluxDB.

✅ Example Test (script.js)

import http from 'k6/http';

import { sleep, check } from 'k6';

export let options = {
  vus: 10,           // 10 virtual users
  duration: '30s',   // test duration: 30 seconds
};

export default function () 
{
  let res = http.get('https://test-api.example.com/');
  
  check(res, {
    'status is 200': (r) => r.status === 200,
  });
  
  sleep(1);
}

🔥 Ideas for Improvements

Add a GitHub Actions workflow for automated test execution

Integrate with Grafana for visualizations

Implement more complex scenarios (Ramp-Up, Soak Testing, Stress Testing)

Support CSV input data for parameterized tests

👨‍💻 Author
GitHub: malkiqmuki
