# 생성형 AI 사용 기록

이 과제에서 생성형 AI(ChatGPT, Claude, Gemini, Copilot 등)를 쓸 때마다 아래 표에 **한 줄씩** 추가할 것.

- **날짜**: 사용한 날 (YYYY-MM-DD)
- **도구**: 사용한 AI 도구 이름
- **관련 기능**: F1–F5 중 무엇 (Git 사용법·README 등 기능과 무관하면 `기타`)
- **무엇을 물었나**: 질문·요청 내용을 구체적으로 (예: "pygame 에서 사각형 충돌을 확인하는 함수")
- **결과를 어떻게 반영/수정했나**: 받은 답을 그대로 썼는지, 어디를 고쳤는지, 쓰지 않았다면 왜인지

AI 를 전혀 쓰지 않았다면 표를 지우고 "이 과제에서 생성형 AI 를 사용하지 않았습니다." 라고 적을 것.
아래 `예시` 줄은 지우고 제출할 것.

| 날짜 | 도구 | 관련 기능 | 무엇을 물었나 | 결과를 어떻게 반영/수정했나 |
|---|---|---|---|---|
| 2026-11-16 | Claude (Claude Code) | F1 | `Player` 클래스의 `super().__init__()`, `image`와 `rect`의 역할, `keys`가 `main.py`에서 어떻게 넘어오는지 설명 요청 | 설명만 듣고 `Player`가 `Sprite`를 상속해 `image`·`rect`를 직접 채우는 구조와 `keys`가 `main.py`에서 매 프레임 넘어오는 흐름을 내 말로 정리. 코드 반영 없음 |
| 2026-11-17 | Claude (Claude Code) | F1 | 경계 판정 방식, 이동 코드를 둘 위치, 입력 해석 분리 여부의 선택지와 트레이드오프 설명 요청 | 설명을 듣고 선택은 직접 함: 경계는 먼저 이동한 뒤 넘어갔으면 끝에 맞춰 되돌리는 방식, 이동·입력 해석·경계 보정을 책임별 메서드로 분리 |
| 2026-11-17 | Claude (Claude Code) | F1 | 좌우 이동(`_read_direction`, `_move`)과 화면 경계 보정(`_keep_in_screen`) 코드 작성 요청 | 설계(경계 처리 방식, 책임별 메서드 분리, 입력 해석 분리, 두 단계 커밋)는 내가 정하고 코드 작성만 맡김. 받은 코드는 수정 없이 반영하고 두 커밋으로 나눠 직접 커밋 |
| 2026-11-17 | Claude (Claude Code) | F2 | `handle_events()`가 하는 일, `pygame.event.get()`으로 이벤트를 순회하는 방식, `Group.update()`가 하는 일, `__init__`과 `update`가 불리는 시점의 차이 설명 요청 | 설명 듣고 `KEYDOWN` 분기에서 `shoot()`을 부르고, 총알을 그룹에 넣고, 매 프레임 `Bullet.update()`가 도는 전체 흐름을 직접 정리. 코드 반영 없음 |
| 2026-11-17 | Claude (Claude Code) | F2 | 발사 입력 방식(`KEYDOWN`과 `get_pressed()`), 발사 간격 제한, 총알 제거 위치, 총알 생성과 그룹 등록의 담당, 발사 처리 메서드 분리 여부의 선택지와 트레이드오프 설명 요청 | 설명을 듣고 선택은 직접 함: `KEYDOWN`으로 한 번 누름에 한 발, 간격 제한 없음, 화면 밖 총알은 `Bullet.update()`에서 스스로 제거, `shoot()`은 만들어 반환만 하고 그룹 등록은 `Game`이 담당, 발사 처리는 `Game`의 메서드로 분리 |
| 2026-11-17 | Claude (Claude Code) | F2 | 스페이스 입력 연결(`handle_events`, `fire`)과 총알 생성(`Player.shoot`)·이동·화면 밖 제거(`Bullet.update`) 코드 작성 요청 | 설계(위 선택들)는 내가 정하고 코드 작성만 맡김. 받은 코드는 수정 없이 반영하고 두 커밋으로 나눠 직접 커밋 |
| 2026-11-18 | Claude (Claude Code) | F3 | `pygame.sprite.groupcollide`와 `dokill1`, `dokill2`가 하는 일, `self.screen`과 `blit`, `draw()`와 `blit`의 차이, `set_mode`가 돌려주는 값 설명 요청 | 설명만 듣고 `groupcollide`가 부딪힌 스프라이트를 자동으로 `kill()`한다는 것, `self.screen`이 모든 그림을 얹는 도화지이고 `flip()`으로 보인다는 것을 정리. 코드 반영 없음 |
| 2026-11-18 | Claude (Claude Code) | F3 | 충돌 판정 방식, 점수를 세는 방법, 충돌 처리와 점수 표시를 둘 위치의 선택지와 트레이드오프 설명 요청 | 설명을 듣고 선택은 직접 함: `groupcollide` 사용, 적 그룹을 첫째 인자로 해 맞은 적 수만큼 점수를 올림, 충돌 처리와 HUD 표시를 각각 `Game`의 메서드로 분리 |
| 2026-11-18 | Claude (Claude Code) | F3 | 총알과 적의 충돌 처리·점수 더하기(`handle_bullet_hits`)와 점수 표시(`draw_hud`) 코드 작성 요청 | 설계(위 선택들)는 내가 정하고 코드 작성만 맡김. 받은 코드는 수정 없이 반영하고 두 커밋으로 나눠 직접 커밋 |
| 2026-11-19 | Claude (Claude Code) | F4 | `pygame.sprite.spritecollide`가 `groupcollide`와 다른 점, `dokill`이 지우는 대상, 돌려주는 값, `draw_title()`이 글자를 그리는 방식 설명 요청 | 설명만 듣고 `spritecollide`가 스프라이트 하나와 그룹을 비교해 그룹 쪽만 지우고 리스트를 돌려준다는 것, `draw_title()`이 줄마다 직접 그리거나 목록으로 반복한다는 것을 내 말로 정리. 코드 반영 없음 |
| 2026-11-19 | Claude (Claude Code) | F4 | 플레이어와 적의 충돌 판정 방식, 생명 감소와 게임 오버 판정의 코드 구성, 게임 오버 검사 시점, 게임 오버 화면을 그리는 방식, 생명 0 고정 위치의 선택지와 트레이드오프 설명 요청 | 설명을 듣고 선택은 직접 함: `spritecollide` 사용, 플레이어에 닿은 적 처리와 지나간 적 처리와 게임 오버 판정을 각각 메서드로 나누고 생명을 잃는 두 경우는 상위 메서드로 묶음, 생명은 묶음 메서드 끝에서 0으로 고정 |
| 2026-11-19 | Claude (Claude Code) | F4 | 생명 감소·게임 오버 판정(`handle_life_loss` 등 메서드 네 개)과 게임 오버 화면(`draw_game_over`) 코드 작성 요청 | 설계(위 선택들)는 내가 정하고 코드 작성만 맡김. 받은 코드는 수정 없이 반영하고 두 커밋으로 나눠 직접 커밋 |
| 2026-11-20 | Claude (Claude Code) | F5 | `settings.py`의 `BASE_DIR`과 `HIGHSCORE_FILE`이 경로를 만드는 방식(`dirname`, `abspath`, `join`), `highscore.txt`가 언제 생기는지, 권한 오류가 생기는 경우, `try/except`와 `except Exception as e`로 오류를 잡고 내용을 보이게 하는 방법, `reset()`이 하는 일 설명 요청 | 설명만 듣고 `HIGHSCORE_FILE`이 코드 파일이 있는 폴더 기준의 전체 경로 문자열이라는 것, try/except로 오류를 잡으면 어떤 오류인지 알 수 없으므로 `as e`와 `print`로 직접 드러내야 한다는 것을 정리. 코드 반영 없음 |
| 2026-11-20 | Claude (Claude Code) | F5 | 파일 읽기 오류 처리, 저장 실패 처리, 최고 점수 갱신을 둘 위치, R 키 재시작 처리 위치, 게임 오버 화면 줄을 늘리는 방식, `highscore.txt`를 저장소에서 다루는 방식의 선택지와 트레이드오프 설명 요청 | 설명을 듣고 선택은 직접 함: 오류 종류마다 `except`를 따로 두고 각각 `print`, 저장 실패도 잡아서 `print`, 최고 점수 갱신은 `Game`의 메서드로 분리, R 키는 분기에 직접 `self.reset()`, 점수 줄은 목록 반복으로 그리고 배치 재조정 기획|
| 2026-11-20 | Claude (Claude Code) | F5 | 최고 점수 읽기·저장·갱신(`load_high_score`, `save_high_score`, `update_high_score`)과 R 키 재시작, 게임 오버 화면 재배치 코드 작성 요청 | 설계(위 선택들, 최고 점수 갱신 먼저·재시작과 화면 뒤의 두 단계 커밋, `.gitignore`는 머지 뒤 `main`에서)는 내가 정하고 코드 작성만 맡김. 받은 코드는 수정 없이 반영하고 두 커밋으로 나눠 직접 커밋 |
