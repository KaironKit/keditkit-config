# K-EditKit 운영 설정

K-EditKit의 공개 운영 설정 저장소입니다. 앱 소스와 사용자 문서는 포함하지 않습니다.
설치와 업데이트는 Microsoft Store에서 제공합니다.

## 최신 버전 관리

[`update/version.json`](update/version.json)의 `latest_version`을 수정합니다.

```json
{
  "schema_version": 1,
  "app_id": "ironwriter.K-EditKit",
  "latest_version": "1.0.0.0"
}
```

- 버전은 `1.0.1.0`처럼 숫자 네 자리로 씁니다. 다른 항목은 그대로 둡니다.
- **새 버전을 Microsoft Store에 게시하고 사용자가 실제 업데이트할 수 있는지 확인한 뒤** 이 값을 올리세요. 먼저 올리면 사용자가 업데이트할 수 없는 상태로 차단될 수 있습니다.
- 이 기능을 포함한 앱은 실행할 때 GitHub에서 설정을 새로 읽습니다. 설치된 앱 버전이 이 값보다 낮으면 편집 화면을 열지 않고 업데이트를 안내합니다.
- 인터넷 연결 실패·설정 누락·잘못된 JSON·시간 초과 시에도 편집 화면을 열지 않습니다. 오프라인 유예와 이전 응답을 이용한 실행은 제공하지 않습니다.
- 차단 기준을 되돌려야 하면 `latest_version`을 기존 버전으로 수정합니다. 사용자는 앱을 종료한 뒤 다시 실행합니다.
- 설정 변경은 GitHub의 HTTP 캐시·서비스 상태에 따라 반영에 시간이 걸릴 수 있습니다. 매번 고유 URL과 캐시 재검증 헤더로 요청하지만 즉시 반영을 보장하지는 않습니다.
- 이미 열려 있는 작업 창은 강제로 종료하지 않습니다. 다음 실행에서 확인하므로 진행 중인 작업을 저장할 수 있습니다.
- 이 기능이 없는 예전 배포본이나 변조한 앱까지 제어하는 기능은 아닙니다.

## 향후 부분유료화

[`update/access_settings.json`](update/access_settings.json)은 향후 유료 기능의 무료 개방 정책을 위한 예약 파일입니다.
현재는 모든 기능을 무료로 제공하며, **현재 앱은 이 파일로 기능을 잠그거나 해제하지 않습니다.**
부분유료화 시 앱 업데이트에 Microsoft Store 구매 권한 확인과 기능별 제한을 구현해야 합니다.
이 JSON을 바꾸는 것만으로 결제·구매 확인이 구현되지는 않습니다.

## 배포 위치

- [Microsoft Store](https://apps.microsoft.com/detail/9NKHGCMW9X7X)
- 버전 설정: `https://raw.githubusercontent.com/KaironKit/keditkit-config/main/update/version.json`

설정 저장소에는 비밀번호, 구매 내역, API 키, 사용자 문서를 올리지 마세요.

