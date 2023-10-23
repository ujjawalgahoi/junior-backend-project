
### Creation of Object Structure
```json
{
	"nickname": "<nickname by user>",
	"sleep-improvement-options": "<option selected by user under sleep-improvement-options>",
	"sleep-struggle-duration": "<option selected by user under sleep-struggle-duration>",
	"bedtime": "<date object selected by user under bedtime>",
	"wakeup-time": "<date object selected by user under wakeup-time>",
	"sleep-duration": "<option selected by user under sleep-duration>"
}
```

### Screen 1: Sleep Improvement Options
**Endpoint:** `/api/sleep-improvement-options`  
**Method:** `GET`  
**Parameters:** none  
**Response:**
```json
{
    "options": [
        "Would go to sleep easily",
        "I would sleep through the night",
        "I'd wake up on time, refreshed"
    ]
}
```

### Screen 2: Sleep Struggle Duration
**Endpoint:** `/api/sleep-struggle-duration`  
**Method:** `GET`  
**Parameters:** None  
**Response:**
```json
{
    "options": [
        "Less than 2 weeks",
        "2 to 8 weeks",
        "More than 8 weeks"
    ]
}
```

### Screen 3: Bedtime Selection
**Endpoint:** `/api/bedtime`  
**Method:** `GET`  
**Parameter:** None  
**Response:**
```json
{
	"options": [
		"display-bedtime"
	]
}
```
On the UI, if the response contains "display-bedtime," the clock interface will be shown; otherwise, an error will be displayed.

### Screen 4: Wakeup Time Selection
**Endpoint:** `/api/wakeup-time`  
**Method:** `GET`  
**Parameter:** None  
**Response:**
```json
{
	"options": [
		"display-wakeup-time"
	]
}
```
On the UI, if the response contains "display-wakeup-time," the clock interface will be shown; otherwise, an error will be displayed.

### Screen 5: Sleep Duration Selection
**Endpoint:** `/api/sleep-duration`  
**Method:** `GET`  
**Parameter:** None  
**Response:**
```json
{
    "options": [
        "6 hrs",
        "7 hrs",
        "8 hrs",
        "9 hrs"
    ]
}
```

### Database Schema (SQL):
```sql
CREATE TABLE SleepSurvey (
    survey_id INT PRIMARY KEY AUTO_INCREMENT,
    nickname VARCHAR(255),
    sleep_improvement_option VARCHAR(255),
    sleep_struggle_duration VARCHAR(255),
    bedtime DATETIME,
    wakeup_time DATETIME,
    sleep_duration VARCHAR(10)
);
```

In this schema:

- `survey_id` is an auto-incremented primary key for uniquely identifying each survey response.
- `nickname` is a VARCHAR field to store the user's nickname.
- `sleep_improvement_option` is a VARCHAR field to store the option selected by the user under sleep-improvement-options.
- `sleep_struggle_duration` is a VARCHAR field to store the option selected by the user under sleep-struggle-duration.
- `bedtime` is a DATETIME field to store the date and time object selected by the user under bedtime.
- `wakeup_time` is a DATETIME field to store the date and time object selected by the user under wakeup-time.
- `sleep_duration` is a VARCHAR field to store the option selected by the user under sleep-duration.
