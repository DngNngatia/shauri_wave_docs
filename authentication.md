# Authentication
Shauri Wave uses OAuth2 as an authorization layer. As such, every API request must contain an Authorize HTTP header with a token. Access tokens are app and user-specific.

To be able to work with our integration API's you will need to already have created an account with [Shauri Wave](https://shauriwave.com). If you don't have an account please visit this link to get started. [Create an accoun on Shauri Wave](https://app.shauriwave.com)


After successfully registering an account, ensure to link your phone number to gain access to all features offered by Shauri Wave. Read this blog on how to onboard a phone number on WhatsApp cloud API on Shauri Wave. [Onboard a phone number on WhatsApp cloud API on Shauri Wave](https://shauriwave.com/blogs/onboard-a-phone-number-on-whatsapp-cloud-api)


# Authentication token
Follow the following steps to access you developer access token.
- Login to your app dashboard [Shauri Wave](https://app.shauriwave.com)
- From you side menu navigation, click on [Account Settings](https://app.shauriwave.com/account-settings)
- Go to the `Webhooks and API keys` tab to access the section for generating API keys.
- Below, you'll find a button labeled `Generate API key` Click on it to generate your authentication access token.
- Ensure that you store it securely. We do not retain the token on our system. If you misplace your token, you can always generate a new one.

### Sample token response

```bash
eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiJ9.eyJhdWQiOiIzIiwianRpIjoiMjQ1NTg5OGM1ZTJhMDQwNDNkODM4ZjFmOGYxNjVkYTgzNmNmMWM5YTk0MzkzNTA1YjM1OTQ3ZDk2ODhjYTg1Y2FmNTkzM2U0MDMxZmYyNjAiLCJpYXQiOjE3MTE2MjY4MzAuNTYwMjQyLCJuYmYiOjE3MTE2MjY4MzAuNTYwMjQ1LCJleHAiOjE3NDMxNjI4MzAuNTQ5MjM3LCJzdWIiOiIxMSIsInNjb3BlcyI6W119.QkuKqUfsEJrLLZMAnptn4KUIgxpAD8Hi-FSzr-6f-nX4eM9wQU1GyR8RsqWxAhqrgt8_VzS56Sly_EOu4nvFd5It6Aka_k9-j6k1lOAEDT43mIR1JZJfiy9QE4rW-haCmy3Yce0ib6O0yix-V1oSpitn-Ljbl1ewK1Bh2N2rEfMutt90NLfOshejoa3z0O7XGBIILU5RL_IOomeLfb3r5v1HhDDynEMqHtxE0BZS_pQgMpX0KczYD3Un9lNPTkwQ3gOb8fit-rdb1jwWveKZUbj9mCcvPPJoBtacr8xp3gPnVDpm3iS657cIqr_Do-Ui8vmnGaD19hiXxTmwKlUScSbNxdOhPNDQBPrIjYfkiJuv-RMgRBEdKi_fYg6Qfh3C04MR65vYEitOJRM8CV5WAKYEGg1GIa7O_ULEi_7YRu0rSjBvhgRRxbMguIVh1o9KghD0uhKfZ-BI2DYPFGEQkabHMrgeHUASPgk1a1WJywLHoZT6OGVyjvMauhLGNj_BLjTFMarleFXEipbqLf2t0ZFwF7ZgxzOaYswfbOcbRKIzzqbKuA1PhEXGgcZIBRJLNmLlVBwAubSlAwERmNsy_8kPW8v8VCVcdJkr2jY0YkoN25JlpJ81RM9-IvSS0SGDVBTHjXos8f4lX5NCB9S7UHH9rkl3u6rWohE2gX1Dqro
```