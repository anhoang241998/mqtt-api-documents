## Mqtt Documents

### 1. Get Realtime response

**Description:** This MQTT contains realtime data such as heart, respiration,... This data is sent from display to client.  
**Subscribe:**

- Topic: things/SERIAL/realtime_response
- Payload:

```
  [
  {
    "dev_id": "e8:eb:1b:39:5c:7c",
    "data": [
      {
        "Instant_HR": "255",
        "Heart_Rate": "255",
        "Resp_Rate": "255",
        "HRV": "0",
        "Total_Motions": "0",
        "Room_Temp": "34",
        "Room_Hum": "43",
        "Body_Temp": "0",
        "Body_Temp_Var": "0",
        "Total_Snoring": "0",
        "Snoring_Noisy": "0",
        "Total_Apnea": "0",
        "Pnp_bg": "0.000000",
        "Pnp_rt": "0.000000",
        "Th_bg": "0",
        "Th_rt": "0",
        "Bed_Occupied": "0",
        "t": "2021-07-20T09:54:27Z"
      }
    ]
  }
]
```

> _Note:_  
> Snoring_Noisy can be:  
> 0 -> Not Noisy  
> 1 -> Noisy

### 2. Emergency calling

**Description:** This MQTT help to send/get emergency status, send turn off buzzer and calling.  
**Publish:**

- Topic: things/SERIAL/emergency
- Payload:

```
{
  "dev_id": "4c:55:cc:1e:36:8a",
  "mode": "N",
  "data": []
}
```

> _Note:_  
> N = 0: get emergency status  
> N = 1: Turn off emergency calling  
> N = 2: Turn off emergency calling and buzzer  
> N = 3: Turn off buzzer

**Subscribe:**

- Topic: things/SERIAL/emergency_response
- Payload:

```
{
  "dev_id": "4c:55:cc:1e:36:8a",
  "mode": "status",
  "data": []
}
```

> _Note:_  
> status = 0: Emergency case 1 - SOS Button  
> status = 1: Emergency case 2 - Heart Stop  
> status = 2: Emergency case 3 - Breathing Stop  
> status = 5: Emergency case 4 - Seizure Stop  
> status = 10: Normal Case

### 3. Buzzer

**Description:** This MQTT helps to turn on/off buzzer on display.  
**Publish:**

- Topic: things/SERIAL/buzzer
- Payload:

```
{
  "dev_id": "4c:55:cc:1e:36:8a",
  "mode": "Off"
}
```

> _Note:_  
> Mode: On/Off for turn on/off buzzer  
> Mode: Status for get buzzer status

**Subscribe:**

- Topic: things/SERIAL/buzzer_response
- Payload:

```
{
  "dev_id": "4c:55:cc:1e:36:8a",
  "mode": "Off"
}
```

> _Note:_  
> Mode: On/Off for turn on/off buzzer

### 4. Buzzer Volume

**Description:** This MQTT helps set buzzer volume.  
**Publish:**

- Topic: things/SERIAL/buzzer_setting
- Payload:

```
{
  "dev_id": "4c:55:cc:1e:36:8a",
  "mode": "High"
}
```

**Subscribe:**

- Topic: things/SERIAL/buzzer_setting_response
- Payload:

```
{
  "dev_id": "4c:55:cc:1e:36:8a",
  "mode": "High"
}
```

> _Note:_  
> Mode: None Buzzer is disabled
> Mode: Low Buzzer is enabled and its volume is low  
> Mode: Medium Buzzer is enabled and its volume is medium  
> Mode: High Buzzer is enabled and its volume is high

### 5. Vibrate

**Description:** This MQTT helps to turn on/off vibrate on display  
**Publish:**

- Topic: things/SERIAL/vibrate
- Payload:

```
{
  "dev_id": "4c:55:cc:1e:36:8a",
  "mode": "Off"
}
```

**Subscribe:**

- Topic: things/SERIAL/vibrate_response
- Payload:

```
{
  "dev_id": "4c:55:cc:1e:36:8a",
  "mode": "Off"
}
```

> _Note:_  
> Mode: On/Off for turn on/off vibrate

### 6. No Breathing

**Description:** This MQTT helps to set no breathing mode on display  
**Publish:**

- Topic: things/SERIAL/no_breathing
- Payload:

```
{
  "dev_id": "4c:55:cc:1e:36:8a",
  "mode": "Status"
}
```

> _Note:_  
> Mode: Status for get no breathing status on display  
> Mode: Demo set no breathing to demo mode  
> Mode: Low set no breathing to low mode  
> Mode: Medium1 set no breathing to medium 1 mode  
> Mode: Medium2 set no breathing to medium 2 mode  
> Mode: High no set breathing to high mode

**Subscribe:**

- Topic: things/SERIAL/no_breathing_response
- Payload:

```
{
  "dev_id": "4c:55:cc:1e:36:8a",
  "mode": "Low"
}
```

> _Note:_  
> Mode: Demo set no breathing to demo mode  
> Mode: Low set no breathing to low mode  
> Mode: Medium1 set no breathing to medium 1 mode  
> Mode: Medium2 set no breathing to medium 2 mode  
> Mode: High no set breathing to high mode

### 7. Seizure

**Description:** This MQTT helps to turn on/off seizure  
**Publish:**

- Topic: things/SERIAL/seizure_setting
- Payload:

```
{
  "dev_id": "4c:55:cc:1e:36:8a",
  "mode": "Status"
}
```

> _Note:_  
> Mode: Status for get seizure status on display  
> Mode: Yes for turn on seizure  
> Mode: No for turn off seizure

**Subscribe:**

- Topic: things/SERIAL/seizure_setting_response
- Payload:

```
{
  "dev_id": "4c:55:cc:1e:36:8a",
  "mode": "Yes"
}
```

> _Note:_  
> Mode: Yes display had turn on seizure  
> Mode: No display had turn off seizure

### 8. Sleep Display

**Description:** This MQTT helps to sleep display  
**Publish:**

- Topic: things/SERIAL/power_sleep
- Payload:

```
{
  "dev_id": "4c:55:cc:1e:36:8a",
  "mode": "NONE"
}
```

> _Note:_  
> Mode: NONE for get display status  
> Mode: ON/ OFF for turn on/ off display

**Subscribe:**

- Topic: things/SERIAL/power_sleep_response
- Payload:

```
{
  "dev_id": "4c:55:cc:1e:36:8a",
  "mode": "Off"
}
```

> _Note:_  
> Mode: On display is on  
> Mode: Off display is off

### 9. Display Timeout

**Description:** This MQTT helps to set display timeout after amount of time.  
**Publish:**

- Topic: things/setting_time_display
- Payload:

```
{
  "dev_id": "4c:55:cc:1e:36:8a",
  "time": "None"
}
```

> _Note:_  
> time: None for get timeout on display  
> time: 30s for set timeout on display to 30s  
> time: 1m for set timeout on display to 1m  
> time: 2m for set timeout on display to 2m  
> time: 5m for set timeout on display to 5m  
> time: 10m for set timeout on display to 10m  
> time: 25m for set timeout on display to 25m  
> time: 45m for set timeout on display to 45m  
> time: 1h for set timeout on display to 1h  
> time: n for set timeout on display to never

**Subscribe:**

- Topic: things/setting_time_display
- Payload:

```
{
  "dev_id": "4c:55:cc:1e:36:8a",
  "time": "1m"
}
```

### 10. User Info For Display

**Description:** This MQTT helps to config user for display  
**Publish:**

- Topic: things/setting_user_info
- Payload:

```
{
  "customer_id": "12345612",
  "dev_id": "4c:55:cc:1e:36:8a",
  "password": "12345612",
  "token": "eyadnasldnasldnao",
  "user_name: "abc@gmail.com"
}
```

**Subscribe:**

- Topic: things/setting_user_info_response
- Payload:

```
{
  "customer_id": "12345612",
  "dev_id": "4c:55:cc:1e:36:8a",
  "password": "12345612",
  "token": "eyadnasldnasldnao",
  "user_name: "abc@gmail.com"
}
```

### 11. Offline

**Description:** This MQTT offline data will send from display to client.  
**Subscribe:**

- Topic: things/SERIAL/log-response
- Payload:

```
{
  "dev_id":"4c:55:cc:1e:36:8a",
  "data":[
    {
      "Instant_HR": [
        "60",
        "72",
        "80"
      ],
      "Heart_Rate": [
        "62",
        "73",
        "81"
      ],
      "Resp_Rate": [
        "10",
        "16",
        "25"
      ],
      "HRV": [
        "200",
        "300",
        "500"
      ],
      "Total_Motions": ["10"],
      "Room_Temp": [
        "25",
        "27",
        "32"
      ],
      "Room_Hum": [
        "40",
        "50",
        "60"
      ],
      "Body_Temp": [
        "36.5",
        "37",
        "37.5"
      ],
      "Total_Snoring": ["1"],
      "Total_Apnea": ["1"],
      "Pnp_bg": [
        "2.3",
        "5.2",
        "6.3"
      ],
      "Pnp_rt": [
        "2.3",
        "5.2",
        "6.3"
      ],
      "Th_bg": [
        "673843",
        "774843",
        "873843"
      ],
      "Th_rt": [
        "772843",
        "873843",
        "973843"
      ],
      "Bed_Occupied": ["1"],
      "t": "2021-06-24T10:31:12Z"
    }
  ]
}
```

### 12. Calibration

**Description:** This MQTT is send to start calibration or get calibration status.  
**Publish:**

- Topic: things/SERIAL/calibration
- Payload:

```
{
  "dev_id": "4c:55:cc:1e:36:8a",
  "mode": "Calibration"
}
```

> _Note:_  
> Mode: Calibration -> Start Calibration  
> Mode: Status -> get Calibration process status on display

**Subscribe:**

- Topic: things/SERIAL/calibration_response
- Payload:

```
{
  "dev_id": "4c:55:cc:1e:36:8a",
  "mode": "None",
  "time": "60"
}
```

> _Note:_  
> Mode: None -> Display is not calibration  
> Mode: CalibWaitEmpty -> Display start calib bed and needs to empty  
> Mode: CalibEmpty -> Display is calib bed and needs to empty  
> Mode: CalibEmpty_done -> Display finish calib bed  
> Mode: CalibWaitPerson -> Display start calib person  
> Mode: CalibPerson -> Display is calib person  
> Mode: CalibPerson_done -> Display finish calib person  
> Mode: MasterNotDetected -> Error 1: Pad NOT Detected!  
> Mode: BedNotEmpty -> Error 2: Bed is not empty  
> Mode: HaveMovements -> Error 3: when calibration, there are movement on the pad  
> Mode: NoPerson -> Error 4: There are no person when calibration  
> time: "60" -> the time for calibration process

### 13. Get Firmware version (Retain Message)

**Description:** This MQTT helps client to get firmware version on display  
**Publish:**

- Topic: things/SERIAL/ota_get_fw_version
- Payload:

```
{
  "dev_id": "4c:55:cc:1e:36:8a",
  "message": ""
}
```

**Subscribe:**

- Topic: things/SERIAL/ota_get_fw_version_response
- Payload:

```
{
  "dev_id": "4c:55:cc:1e:36:8a",
  "hub": "1.0.0",
  "master": "1.0.0",
  "wifi": "1.0.0",
  "message": ""
}
```

### 14. Auto Update or Manual Update (Retain)

**Description:** This MQTT helps to send/get auto update or manual update mode on display.  
**Publish:**

- Topic: things/SERIAL/ota_setting
- Payload:

```
{
  "dev_id": "4c:55:cc:1e:36:8a",
  "mode": "AUTO",
  "ug_start": "",
  "message": ""
}
```

> _Note:_  
> when mode is auto no need to set ug_start  
> when mode is manual set ug_start to "NO" to set mode on diplay
> when mode is manual and set ug_start to "YES" to start

**Subscribe:**

- Topic: things/SERIAL/ota_setting_response
- Payload:

```
{
  "dev_id": "4c:55:cc:1e:36:8a",
  "message": "",
  "mode": "MANUAL"
}
```

> _Note:_  
> Mode: MANUAL -> On display, mode is manual  
> Mode: AUTO -> On display, mode is auto

### 15. Get Update Process Status (Retain)

**Description:** This MQTT helps to get update OTA status  
**Subscribe:**

- Topic: things/SERIAL/ota_proccess_response
- Payload:

```
{
  "dev_id": "4c:55:cc:1e:36:8a",
  "message": "",
  "mode": "PROCESSING"
}
```

> _Note:_  
> mode: PROCESSING -> display is updating  
> mode: SUCCESSED -> display was updated success  
> mode: ERROR -> display updated fail  
> message: "abc" -> display show message that client will use for showing on dialog.

### 16. On/Off Vibrate

**Description:** This MQTT use for turn on/off vibrate in display  
**Publish:**

- Topic: things/SERIAL/vibrate
- Payload:

```
{
  "mode": "mode"
}
```

> _Note:_  
> mode: On/Off -> display turn on/off vibrate

**Subscribe:**

- Topic: things/SERIAL/vibrate_response
- Payload:

```
{
  "mode": "mode"
}
```

> _Note:_  
> mode: On/Off -> display is on/off vibrate

### 17. Vibrate levels

**Description:** This MQTT use for config the levels of vibrate on display  
**Publish:**

- Topic: things/SERIAL/vibrate_setting
- Payload:

```
{
  "mode": "mode"
}
```

> _Note:_  
> mode: None/Low/Medium/High -> config levels of vibrate on display are none/ low/ medium/ high

**Subscribe:**

- Topic: things/SERIAL/vibrate_setting_response
- Payload:

```
{
  "mode": "mode"
}
```

> _Note:_  
> mode: None/Low/Medium/High -> The display has none/ low/ medium/ high levels of vibrate

### 18. Show Message From Display

**Description:** Clients need to show when receive those message.  
**Subscribe:**

- Topic: things/SERIAL/message_popup_response
- Payload:

```
{
  "message": "message"
}
```

> _Note:_  
> message can be:  
> message: System is starting up. Please sit up or nothing is on pillow for about 1 minute  
> message: Please calibrate the device before use.

### 19. Body Temperature Interval

**Description:** This MQTT use for set body temp interval for display  
**Publish:**

- Topic: things/SERIAL/body_temp_interval
- Payload:

```
{
  "mode": "mode",
  "Time": "x"
}
```

> _Note:_  
> mode: Status -> get body temp interval status  
> x: null/1/2/3/5/10 -> set/get body temp interval from/to display

**Subscribe:**

- Topic: things/SERIAL/body_temp_interval_response
- Payload:

```
{
  "Time": "x"
}
```

### 20. Developer Mode

**Description:** This MQTT use for get data in developer mode  
**Publish:**

- Topic: things/SERIAL/dev_params
- Payload:

```
{
  "mode": "Get"
}
```

**Subscribe:**

- Topic: things/SERIAL/dev_params_response
- Payload:

```
{
  "AvgPksOpti1": [
    "374",
    "423",
    "274"
  ],
  "AvgPksOpti2": [
    "374",
    "423",
    "274"
  ],
  "AvgPksOpti3": [
    "374",
    "423",
    "27",
    "4"
  ],
  "PnpBgRatio1": [
    "374",
    "423",
    "274"
  ],
  "PnpBgRatio2": [
    "374",
    "423",
    "274"
  ],
  "PnpBgRatio3": [
    "374",
    "423",
    "274"
  ]
}
```

### 21. Reset

**Description:** This MQTT use for reset/factory reset hub  
**Publish:**

- Topic: things/SERIAL/system_reset
- Payload:

```
{
  "dev_id": "123456",
  "mode": "mode"
}
```

**Subscribe:**

- Topic: things/SERIAL/system_reset_response
- Payload:

```
{
  "dev_id: "123456",
  "mode": "mode"
}
```

> _Note:_  
> mode: REBOOT -> Reset hub  
> mode: FACTORY_RESET -> Reset all setting to default and reset hub
