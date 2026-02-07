
# 🇷🇺 RUZONE country Rules (Sing-box & PassWall)

Автоматизированная сборка правил для прямого доступа к российским ресурсам.

Обновляется ежедневно в **05:00 UTC**.

## 🔗 Прямая ссылка на Rule-Set

`https://github.com/007dimkos/russia-ru-rules/releases/download/release-latest/RUZONEcountry.srs`

---

## 🛠 Настройка

### 1. PassWall 2 (OpenWrt)

В поле **Remote Rule Set** (Удаленные правила) добавь строку:

```text
rule-set:remote:https://github.com/007dimkos/russia-ru-rules/releases/download/release-latest/RUZONEcountry.srs

```

Затем установи для этого правила действие **DIRECT**.

---

### 2. Sing-Box

Добавьте `rule_set` в конфигурацию Sing-Box и правило для него:

```json
{
  "route": {
    "rule_set": [
      {
        "tag": "ru_zone",
        "type": "remote",
        "format": "binary",
        "url": "https://github.com/007dimkos/russia-ru-rules/releases/download/release-latest/RUZONEcountry.srs"
      }
    ],
    "rules": [
      {
        "rule_set": "ru_zone",
        "outbound": "direct"
      }
    ]
  }
}

```
