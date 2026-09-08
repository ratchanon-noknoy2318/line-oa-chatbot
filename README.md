# Examples

|                Telemed Start                |                     More Info                    |                     About Us                     |                    Health Tip                    |
| :----------------------------------------------: | :----------------------------------------------: | :----------------------------------------------: | :----------------------------------------------: |
| <img src="https://res.cloudinary.com/dpa96jvla/image/upload/v1779581208/1_f1m5iv.png" width="200"> | <img src="https://res.cloudinary.com/dpa96jvla/image/upload/v1779581208/2_ys9ozd.png" width="200"> | <img src="https://res.cloudinary.com/dpa96jvla/image/upload/v1779581208/5_bitxup.png" width="200"> | <img src="https://res.cloudinary.com/dpa96jvla/image/upload/v1779581211/4_qnspxw.png" width="200"> |
|    [JSON](./telemedicine-start.json)   |  [JSON](./telemedicine-info.json)  |         [JSON](./about.json)        |       [JSON](./health-tips.json)       |


|               Doctor Schedule               |                     Announcements                    |
| :----------------------------------------------: | :----------------------------------------------: |
| <img src="https://res.cloudinary.com/dpa96jvla/image/upload/v1779581208/3_ltfdkn.png" width="200"> | <img src="https://res.cloudinary.com/dpa96jvla/image/upload/v1779250757/%E0%B8%AA%E0%B8%81%E0%B8%A3%E0%B8%B5%E0%B8%99%E0%B8%8A%E0%B9%87%E0%B8%AD%E0%B8%95_2026-05-20_111906_nw7dq3.png" width="200"> |
| [JSON](./thai-schedule.json) | [JSON](./announcements.json) |


## Architecture

```mermaid
flowchart TD
    U["LINE User"] --> L["LINE Platform"]

    L -->|Webhook Event| NG["ngrok"]
    NG -->|Forward Request| APP["Local Application"]

    APP -->|Verify| CS["LINE Channel Secret"]
    APP -->|Generate| FM["Flex Message"]

    APP -->|Access Token| API["LINE Messaging API"]
    API -->|Reply Message| L

    L --> U
```
