# Скрипт для проверки доступности ресурса

```python
#!/usr/bin/env python3
import sys
import requests

def check_resource(url):
    try:
        response = requests.get(url, timeout=5)
        response.raise_for_status()
        print(f"✅ {url} доступен.")
        sys.exit(0)
    except requests.exceptions.RequestException as e:
        print(f"❌ {url} недоступен: {e}")
        sys.exit(1)

if __name__ == "__main__":
    if len(sys.argv) != 2:
        print("Использование: python3 check_resource.py <URL>")
        sys.exit(1)
    check_resource(sys.argv[1])
```
