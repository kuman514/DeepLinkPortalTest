# DeepLinkPortalTest

한모금 앱 스킴 테스트용 레포지토리.

## 웹페이지에서 iOS 앱 호출 방법

- 링크를 `{스킴}://{호스트}/{...경로}/` 형태로 작성한다.
- 이 때, `onclick` 프로퍼티에 추가적으로 1.5초~2초 이내에 `visibilitychange` 이벤트가 발생했는지 확인 후 발생하지 않았다면 앱 스토어로 이동하는 한들러를 호출해야 한다.

## 웹페이지에서 Android 앱 호출 방법

- 링크를 `intent://{호스트}/{...경로}/#Intent;scheme={스킴};package={패키지ID};S.browser_fallback_url={패키지ID에해당하는앱이없을때열대체URL의인코딩};end` 형태로 작성하면 된다.
  - `S.browser_fallback_url`은 보통 플레이 스토어 링크 `https%3A%2F%2Fplay.google.com%2Fstore%2Fapps%2Fdetails%3Fid%3D{패키지ID}`가 들어간다.
