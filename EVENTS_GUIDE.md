# events.json 운영 안내

앱은 실행할 때 `https://wertvoll9525-hub.github.io/haedong-toemajeon/events.json` 을 받아 이벤트를 적용합니다.
받지 못하면 마지막으로 받은 값 → 앱 내장 기본값 순서로 씁니다. 이 파일만 고쳐 GitHub 에 올리면 앱 업데이트 없이 바뀝니다.

```json
{
  "version": 2,
  "multipliers": {"coin": 1.0, "drop": 1.0, "exp": 1.0},
  "events": [
    {"id": "newyear_att", "type": "attendance", "start": "2027-01-01", "end": "2027-01-14",
     "title_ko": "새해 출석", "title_en": "New Year Check-in", "desc_ko": "매일 출석하고 보상을 받으세요", "desc_en": "Check in daily for rewards",
     "rewards": [{"jade": 100}, {"stone": 300}, {"jade": 200}, {"skill_book": 10}, {"option_stone": 5}, {"awaken_stone": 2}, {"jade": 500}]},
    {"id": "hunt_dec", "type": "kill", "start": "2026-12-01", "end": "2026-12-31",
     "title_ko": "흑무 토벌", "title_en": "Mist Purge", "desc_ko": "요괴를 처치하세요", "desc_en": "Defeat monsters",
     "multipliers": {"drop": 1.5},
     "goals": [{"kills": 1000, "reward": {"jade": 100}}, {"kills": 5000, "reward": {"awaken_stone": 2}}]}
  ]
}
```
- 날짜는 한국 시간 기준 하루 단위(시작일 0시 ~ 종료일 24시).
- 배율은 0.5~5 사이로 제한됩니다.
- 이벤트 `type`: `attendance`(출석형, rewards 배열), `kill`(처치 수형, goals 배열). 그 외는 배율만 적용.
