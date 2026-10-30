# K-EditKit 운영 설정

K-EditKit의 공개 운영 설정 저장소입니다. 앱 소스와 사용자 문서는 포함하지 않습니다.
설치와 업데이트는 Microsoft Store에서 제공합니다.

## 업데이트 확인

K-MemoKit처럼 앱이 Microsoft Store에 업데이트가 있는지 직접 확인합니다.

- 새 버전이 있으면 **무시하고 실행** 또는 **업데이트 이동**을 선택합니다.
- 업데이트 이동을 선택하면 Store의 K-EditKit 제품 화면을 열고 현재 실행을 종료합니다.
- Store 조회는 최대 3초 동안 기다립니다. 연결 실패·시간 초과 시에도 앱을 사용할 수 있습니다.
- 최신 여부를 관리하기 위해 GitHub의 버전 숫자를 올릴 필요가 없습니다.
- 앱과 패키지의 버전은 새 Store 버전을 제출할 때 함께 올립니다.

## 버전별 업데이트 안내

[`update/version.json`](update/version.json)은 K-MemoKit과 같은 `versions` 배열 형식입니다.
실행 허용 버전 기준이나 강제 업데이트 설정이 아닙니다.

```json
{
  "versions": [
    {
      "version": "1.0.0.0",
      "enabled": false,
      "titles": {
        "한국어": "K-EditKit 1.0.0.0 업데이트 안내",
        "English": "K-EditKit 1.0.0.0 Update"
      },
      "contents": {
        "한국어": ["이번 버전의 변경 사항을 적습니다."],
        "English": ["Describe the changes in this release."]
      }
    }
  ]
}
```

- `version`은 안내문을 보여 줄 설치 버전입니다. 더 최신 버전의 안내문을 구버전 앱에 보여 주지 않습니다.
- `enabled: true`이면 해당 버전의 안내문을 표시하고, `false`이면 숨깁니다. 현재 1.0.0.0 항목은 초안으로 숨겨 두었습니다.
- 새 버전 안내가 필요하면 배열에 항목을 추가하고 제목·본문을 수정합니다.
- 안내문은 편집 화면을 연 다음 가져옵니다. GitHub 연결 실패·잘못된 JSON·안내문 누락은 앱 실행을 막지 않습니다.
- **이 공지 다시 보지 않기**는 버전별로 저장됩니다. 다른 버전의 안내문에는 적용되지 않습니다.
- 앱 하단의 버전 표시를 누르면 안내문을 다시 볼 수 있습니다.
- GitHub 설정 변경은 서비스와 HTTP 캐시 상태에 따라 반영에 시간이 걸릴 수 있습니다.

## 향후 부분유료화

[`update/access_settings.json`](update/access_settings.json)은 향후 유료 기능의 무료 개방 정책을 위한 예약 파일입니다.
현재는 모든 기능을 무료로 제공하며, **현재 앱은 이 파일로 기능을 잠그거나 해제하지 않습니다.**
K-MemoKit의 Plus·광고 제거 상품은 K-EditKit과 별개입니다.
K-EditKit의 유료 기능과 Store 상품을 정한 뒤 구매 권한 확인과 기능별 제한을 구현해야 합니다.
이 JSON을 바꾸는 것만으로 결제가 발생하거나 부분유료화가 적용되지는 않습니다.

## 배포 위치

- [Microsoft Store](https://apps.microsoft.com/detail/9NKHGCMW9X7X)
- 업데이트 안내: `https://raw.githubusercontent.com/KaironKit/keditkit-config/main/update/version.json`

설정 저장소에는 비밀번호, 구매 내역, API 키, 사용자 문서를 올리지 마세요.
