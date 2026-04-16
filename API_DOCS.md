# API 문서

## 목차

- [Like - 좋아요 인증 관련 API](#like---좋아요-인증-관련-api)
- [Member - 회원 관련 API](#member---회원-관련-api)
- [Talk - 경기별 톡 관련 API](#talk---경기별-톡-관련-api)
- [CheckIn - 경기 인증 관련 API](#checkin---경기-인증-관련-api)
- [Auth - 인증 및 토큰 관련 API](#auth---인증-및-토큰-관련-api)
- [Game - 경기 조회 관련 API](#game---경기-조회-관련-api)
- [Stat - 야구 기록 통계 관련 API](#stat---야구-기록-통계-관련-api)
- [Stadium - 구장 관련 API](#stadium---구장-관련-api)
- [과거 직관 인증](#과거-직관-인증)
- [Admin](#admin)
- [Stream](#stream)

---

## Like - 좋아요 인증 관련 API

| 메서드 | 경로 | 설명 |
|--------|------|------|
| `POST` | `/api/v1/games/{gameId}/like-batches` | 좋아요 배치 전송 |
| `GET` | `/api/v1/games/{gameId}/likes/counts` | 좋아요 개수 조회 |

---

## Member - 회원 관련 API

| 메서드 | 경로 | 설명 |
|--------|------|------|
| `POST` | `/api/v1/members/me/profile-image/update` | 회원 프로필 이미지 수정 |
| `POST` | `/api/v1/members/me/profile-image/pre-signed` | pre-signed url 조회 |
| `GET` | `/api/v1/members/me/nickname` | 닉네임 조회 |
| `PATCH` | `/api/v1/members/me/nickname` | 닉네임 수정 |
| `PATCH` | `/api/v1/members/me/badges/{badgeId}/representative` | 대표 뱃지 수정 |
| `GET` | `/api/v1/members/favorites` | 응원팀 조회 |
| `PATCH` | `/api/v1/members/favorites` | 응원팀 수정 |
| `GET` | `/api/v1/members/{memberId}` | 프로필 조회 |
| `GET` | `/api/v1/members/me` | 회원 정보 조회 |
| `DELETE` | `/api/v1/members/me` | 회원 탈퇴 |
| `GET` | `/api/v1/members/me/badges` | 뱃지 조회 |

---

## Talk - 경기별 톡(Talk) 관련 API

| 메서드 | 경로 | 설명 |
|--------|------|------|
| `POST` | `/api/v1/talks/{talkId}/reports` | 톡 신고 |
| `GET` | `/api/v1/talks/{gameId}` | 톡 조회 |
| `POST` | `/api/v1/talks/{gameId}` | 톡 생성 |
| `GET` | `/api/v1/talks/{gameId}/latest` | 최신 톡 조회 |
| `GET` | `/api/v1/talks/{gameId}/initial` | 첫 요청에 톡 조회 |
| `DELETE` | `/api/v1/talks/{gameId}/{talkId}` | 톡 삭제 |

---

## CheckIn - 경기 인증 관련 API

| 메서드 | 경로 | 설명 |
|--------|------|------|
| `POST` | `/api/v1/check-ins` | 경기 인증 생성 |
| `GET` | `/api/v1/check-ins/status` | 당일 인증 여부 조회 |
| `GET` | `/api/v1/check-ins/stadiums/fan-rates` | 구장별 팬 점유율 조회 |
| `GET` | `/api/v1/check-ins/stadiums/counts` | 구장별 방문 횟수 조회 |
| `GET` | `/api/v1/check-ins/members` | 인증 내역 조회 |
| `GET` | `/api/v1/check-ins/counts` | 인증 수 조회 |
| `DELETE` | `/api/v1/check-ins/{checkInId}` | 경기 인증 삭제 |

---

## Auth - 인증 및 토큰 관련 API

| 메서드 | 경로 | 설명 |
|--------|------|------|
| `POST` | `/api/v1/auth/refresh` | 토큰 재발급 |
| `POST` | `/api/v1/auth/logout` | 로그아웃 |
| `POST` | `/api/v1/auth/login` | 로그인 |

---

## Game - 경기 조회 관련 API

| 메서드 | 경로 | 설명 |
|--------|------|------|
| `GET` | `/api/v1/games` | 특정 날짜의 경기 목록 조회 |
| `GET` | `/api/v1/games/dates` | 월별 경기 있는 날짜 목록 조회 |

---

## Stat - 야구 기록 통계 관련 API

| 메서드 | 경로 | 설명 |
|--------|------|------|
| `GET` | `/api/v1/stats/win-rate` | 내 팀 인증 승률 조회 |
| `GET` | `/api/v1/stats/win-rate/recent` | 내 팀 최근 10경기 인증 승률 조회 |
| `GET` | `/api/v1/stats/win-rate/opponents` | 상대 팀별 승률 조회 |
| `GET` | `/api/v1/stats/victory-fairy/rankings` | 승리 요정 랭킹 조회 |
| `GET` | `/api/v1/stats/me` | 평균 득, 실, 안타, 피안타, 실책 조회 |
| `GET` | `/api/v1/stats/lucky-stadiums` | 행운의 야구장 조회 |
| `GET` | `/api/v1/stats/counts` | 연도별 승패무/인증 횟수 조회 |

---

## Stadium - 구장 관련 API

| 메서드 | 경로 | 설명 |
|--------|------|------|
| `GET` | `/api/v1/stadiums/games` | 구장별 경기 목록 조회 |

---

## 과거 직관 인증

| 메서드 | 경로 | 설명 |
|--------|------|------|
| `POST` | `/api/v1/past-check-ins` | 과거 직관 인증 생성 |

---

## Admin

| 메서드 | 경로 | 설명 |
|--------|------|------|
| `POST` | `/admin/victory-fairy-rankings/sync` | 승리 요정 랭킹 동기화 |

---

## Stream

| 메서드 | 경로 | 설명 |
|--------|------|------|
| `GET` | `/api/v1/event-stream` | 이벤트 스트림 |
