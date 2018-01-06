
---
layout: post
title:  "HTTP Status Codes"
categories: []
tags: [http]
description: HTTP 상태 코드 및 설명
---

http://osankkk.tistory.com/entry/HTTP-Status-Codes-%EC%9D%91%EB%8B%B5%EA%B2%B0%EA%B3%BC-%EC%83%81%ED%83%9C


200 OK
---
```
The request has succeeded.
정상적으로 응답받음
```

201 Created
---
```
The resource was created successfully.
자원생성이 정상적으로 이루어 졌다.
```

202 Accepted
---
```
The long-running operation was accepted for processing.
장시간작업처리요청을 정상적으로 받았다.
```

204 No Content
---
```
The operation was successful; no data was returned.
정상처리되었으나 반환값이 없다.
```

302 Found
---
```
The resource is a reference to another resource.
다른 자원을 참조하고있다.
```

400 Bad Request
---
```
The request contents are missing or invalid.
요청내용이 없거나 유효하지 않은 호출이다.
```

401 Unauthorized
---
```
The authentication/authorization credentials are invalid.
인증실패
```

403 Forbidden
---
```
The client lacks the proper authorization to perform this request.
요청클라이언트는 이요청을 수행하기 위한 권한이 없습니다.
```

404 Not Found
---
```
The resource was not found at the specified URI.
요청URI로 자원을 찾지 못했다.
```

406 Not Acceptable
---
```
No content can be produced at this URI that matches the request.
URI로 요청한 자원으로 작업을 수행할수 없었다.
```

409 Conflict
---
```
The operation conflicts with a non-CDMI™ access protocol lock or may cause a state transition error on the server.
비표준 CDMI 요청이거나 서버 에러일수 있습니다.
```
