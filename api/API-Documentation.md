# Onsky API Documentation

Contact Support: Nguyen Hoang An  
Email: an2419998@gmail.com  
<span style="color: red"><b>Tài liệu lưu hành nội bộ</b></span>

## Authentication

### <span style="color: #ffb400">POST</span> - Register

`https://microapi.onskycloud.com/lambda-1969541697209631746-svc-client-config/ClientConfigSvc/LoginOrRegister`

The POST Register API is used to register new account for smart health or smart home applications.

**Body**

```json
{
  "Password": "12345612",
  "Email": "example1@onskyhealth.com",
  "Name": "Hello"
}
```

**Expected Response**

```json
{
  "Status": 200,
  "Message": "Login Success",
  "Data": {
    "Id": 1106,
    "UUID": "6188420e-4182-4751-a64b-443218500bd0",
    "FirstName": "Hello",
    "LastName": "Hello",
    "Username": "example1@onskyhealth.com",
    "LastLogin": "2021-10-29T08:12:04.118333Z",
    "LastPasswordChange": "0001-01-01T00:00:00Z",
    "Active": true,
    "Role": "CLIENT_ADMIN",
    "CustomerNumber": "2682114721301136462",
    "Token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJjIjoxMTA1LCJjX24iOiIyNjgyMTE0NzIxMzAxMTM2NDYyIiwiZXhwIjoxNjM1NTIzOTI0LCJpZCI6MTEwNiwiciI6NSwidSI6ImV4YW1wbGUxQG9uc2t5aGVhbHRoLmNvbSIsInVfdWlkIjoiNjE4ODQyMGUtNDE4Mi00NzUxLWE2NGItNDQzMjE4NTAwYmQwIn0.PumUoYMvsIOYoA-CTjRVjGdjjO4hF2Fg4Kh7VqqwEVE",
    "RefreshToken": "949c7b65a386b6b9041d70c1579f80df8de582b7"
  }
}
```

### <span style="color: #ffb400">POST</span> - Login

`https://api.onskycloud.com/authen/v1/api/auth/client `

The POST Login API is used to retrieve the authentication token. After the authentication token is obtained, it must be inserted into the header for all requests.

**Body**

```json
{
  "UserName": "thien@onskyinc.com",
  "Password": "12345612"
}
```

**Expected Response**

```json
{
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJjIjoxMDY2LCJjX24iOiIyNTQyOTM3MTMyNzc5OTYzNDMxIiwiZXhwIjoxNjM1NTIyNzUxLCJpZCI6MTA2NiwiciI6NSwidSI6InRoaWVuQG9uc2t5aW5jLmNvbSIsInVfdWlkIjoiMDQwYmUwODItYmQ2Ni00MjExLWI5ZjgtMmYwYTU0MDY5YzMzIn0.q3ATUkHMSSEYNJJlbeniY8-IPcabq76PYUQJ76OvHuM",
  "expires": "2021-10-29T15:52:31Z",
  "refresh_token": "aa2255950a85aad1f73abbd10590daa89a6bde90"
}
```

### <span style="color: #ffb400">POST</span> - Register new MAC

`https://api.onskycloud.com/iot-service/v1/api/things/register-gateway/{MAC_ADDRESS}`

**Headers: Authorization Bearer Token**  
| Header | Value |
| ----------- | ----------- |
| Authorization | token |

| Path        | Value |
| ----------- | ----- |
| MAC_ADDRESS | 12345 |

**Body**

```json
{
  "macAddress": "12345"
}
```

**Expected Response**

```json

```

## <span style="color: #0cbb51">GET</span> - Get All Devices

`https://api.onskycloud.com/iot-service/v1/api/things/graphql/search?limit={limit}&page={page}&query={query}`

This API helps to get all device that register with the account

**Headers: Authorization Bearer Token**  
| Header | Value |
| ----------- | ----------- |
| Authorization | token |

**Request Params**  
| Key | Value |
| ----------- | ----------- |
| limit | 100 |
| page | 0 |
|query | {pages(key:"",templateName:"Bed Sensor,OnSky gateway"){page,totalItems, things{name,description,displayName,imageUrl,isActive,serial,customerNumber,template{name},properties{name,value}}}}|

**Expected Response**

```json
{
  "data": {
    "pages": {
      "page": 0,
      "things": [
        {
          "customerNumber": "2542937132779963431",
          "description": null,
          "displayName": "Skypad Thien aa_6d",
          "imageUrl": "https://s3-ap-southeast-1.amazonaws.com/onsky-cloud-storage/1969541697209631746/Image/d4f84413-0d54-4d96-9ecc-1cfd5f0a4bb3.png",
          "isActive": false,
          "name": "Skypad Thien aa_6d",
          "properties": [
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": "{\\\"dev_id\\\":\\\"e8:eb:1b:39:aa:6d\\\",\\\"mode\\\":0,\\\"data\\\":[]}"
            }
          ],
          "serial": "e8:eb:1b:39:aa:6d",
          "template": {
            "name": "Bed Sensor"
          }
        },
        {
          "customerNumber": "2542937132779963431",
          "description": null,
          "displayName": "SkyPad Thien 9e_3c",
          "imageUrl": "https://s3-ap-southeast-1.amazonaws.com/onsky-cloud-storage/1969541697209631746/Image/d4f84413-0d54-4d96-9ecc-1cfd5f0a4bb3.png",
          "isActive": false,
          "name": "SkyPad Thien 9e_3c",
          "properties": [
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            },
            {
              "name": null,
              "value": null
            }
          ],
          "serial": "e8:eb:1b:3a:9e:3c",
          "template": {
            "name": "Bed Sensor"
          }
        }
      ],
      "totalItems": 2
    }
  }
}
```

## <span style="color: #0cbb51">GET</span> - Get User Profile

`https://api.onskycloud.com/authen/v1/api/clients/{customer_number}/setting`

This Api allows to fetch user profile. This Api needs **customer number** on the path.

**Headers: Authorization Bearer Token**  
| Header | Value |
| ----------- | ----------- |
| Authorization | token |

**Expected Response**

```json
{
  "id": 1066,
  "created_at": "2021-04-02T11:09:10.684423Z",
  "updated_at": "2021-10-16T08:01:03.422331Z",
  "accountNumber": "2542937132779963431",
  "firstName": "phan thien",
  "lastName": " 123",
  "company": {},
  "email": "thien@onskyinc.com",
  "mobile": "123456789",
  "address1": "132 Vu Tong Phan",
  "alias": "thien@onskyinc.com",
  "confirmed": true,
  "imageId": "",
  "imageUrl": "",
  "active": true,
  "parentId": 2,
  "setting": {
    "id": 1065,
    "created_at": "2021-04-02T11:09:10.680654Z",
    "updated_at": "2021-04-02T11:09:10.680654Z",
    "isAllowRegister": true,
    "needConfirm": false,
    "smtp": {
      "host": "",
      "port": 0,
      "password": "",
      "account": ""
    },
    "payment": {},
    "other": {
      "value": ""
    },
    "parentId": 2
  },
  "settingId": 1065,
  "birth_day": "2019-08-02T00:00:00Z",
  "gender": 2,
  "phones": [
    {
      "id": 1,
      "name": "thien",
      "phone": "372846284",
      "isCareTaker": true,
      "locale": "vi-VN",
      "isMaster": true,
      "countryPrefix": "+84",
      "fullNumber": "+84372846284"
    },
    {
      "id": 2,
      "name": "an 1",
      "phone": "12365",
      "isCareTaker": true,
      "locale": "zh-CN",
      "countryPrefix": "+1",
      "fullNumber": "+112365"
    }
  ],
  "wage": 9,
  "height": 99,
  "emergency_setting": {
    "enabled": true
  },
  "locale": {
    "timezone": "Asia/Ho_Chi_Minh",
    "default": "vi_VN",
    "current": "en-us",
    "availables": [""]
  },
  "suspended": false
}
```

## <span style="color: #0cbb51">GET</span> - Get History/Offline data

`https://lambda-api.onskycloud.com/system-micro-statistic-srv/SystemSvc/Offline?serial={MAC}&skip={page}&limit={number_of_data}&from={from_time_long}&to=${to_time_long}`

This Api Allows to fetch history and offline data

**Headers: Authorization Bearer Token**  
| Header | Value |
| ----------- | ----------- |
| Authorization | token |

**Request Params**  
| Key | Value |
| ----------- | ----------- |
| serial | MAC|
| skip | 0 |
|limit | 100 |
| from | from_time_epoch |
| to | to_time_epoch |

**Expected Value**

```json
[
  {
    "Instant_HR": ["61", "61", "61"],
    "Heart_Rate": ["0", "0", "0"],
    "Resp_Rate": ["7", "10", "17"],
    "HRV": ["0", "0", "0"],
    "Total_Motions": ["0", "0", "0"],
    "Room_Temp": ["0", "0", "0"],
    "Room_Hum": ["0", "0", "0"],
    "Body_Temp": ["37", "37", "37"],
    "Total_Snoring": ["0"],
    "Total_Apnea": ["0", "0", "0"],
    "Pnp_bg": ["0.000000", "0.000000", "0.000000"],
    "Pnp_rt": ["0.000000", "0.000000", "0.000000"],
    "Th_bg": ["0", "0", "0"],
    "Th_rt": ["0", "0", "0"],
    "Bed_Occupied": ["1"],
    "hvol": null,
    "t": "2021-10-28T06:50:26Z",
    "rrv": null
  },
  {
    "Instant_HR": ["0", "0", "0"],
    "Heart_Rate": ["59", "59", "59"],
    "Resp_Rate": ["7", "10", "16"],
    "HRV": ["0", "0", "0"],
    "Total_Motions": ["0", "0", "0"],
    "Room_Temp": ["0", "0", "0"],
    "Room_Hum": ["0", "0", "0"],
    "Body_Temp": ["37", "37", "37"],
    "Total_Snoring": ["0"],
    "Total_Apnea": ["0", "5", "0"],
    "Pnp_bg": ["0.000000", "0.000000", "0.000000"],
    "Pnp_rt": ["0.000000", "0.000000", "0.000000"],
    "Th_bg": ["0", "0", "0"],
    "Th_rt": ["0", "0", "0"],
    "Bed_Occupied": ["1"],
    "hvol": null,
    "t": "2021-10-28T02:20:49Z",
    "rrv": null
  }
]
```

> <span style="color: orange"><em>Note:</em></span>  
> The period you want to fetch must follow the epoch second rule.  
> Ex: 1630996200 = Tuesday, September 7, 2021 1:30:00 PM GMT+7:00  
> Link to check epoch second: [epoch-website](https://www.epochconverter.com/)

## <span style="color: #0cbb51">GET</span> - Get the number of History/Offline data

`https://lambda-api.onskycloud.com/system-micro-statistic-srv/SystemSvc/Offline-count?serial={MAC}&skip={page}&limit={number_of_data}&from={from_time_long}&to=${to_time_long}`

**Headers: Authorization Bearer Token**  
| Header | Value |
| ----------- | ----------- |
| Authorization | token |

**Request Params**  
| Key | Value |
| ----------- | ----------- |
| serial | MAC|
| skip | 0 |
|limit | 100 |
| from | from_time_epoch |
| to | to_time_epoch |

**Expected Response**

```json
{
  "count": 1234
}
```
