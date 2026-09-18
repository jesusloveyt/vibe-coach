# Claude Code로 시작하기

[공통 설치 안내로 돌아가기](./README.md)

이 안내는 **VS Code가 설치되어 있고 연습 폴더가 열린 상태**에서 시작합니다. 아직 준비하지 않았다면 [공통 안내](./README.md)를 먼저 진행하세요.

여기서 설치할 것은 **Anthropic의 Claude Code 확장 프로그램**입니다. 브라우저에서 사용하는 Claude 채팅과 같은 계정을 쓰지만, Claude Code 이용 권한이 필요합니다.

**Claude 무료 계정만으로는 이 과정을 진행할 수 없습니다.** 개인 사용자는 Claude Code가 포함된 Pro 또는 Max 구독을 사용할 수 있습니다. 회사·학교에서 제공하는 계정은 관리자에게 이용 권한을 확인하세요. 비용 없이 시작하고 싶다면 [Codex 안내](./codex.md)를 선택할 수 있습니다. 확인일: **2026-09-19**. [공식 요금 안내](https://claude.com/pricing)

## B-1. 계정과 이용 권한 준비하기

이미 Claude Code를 이용할 수 있는 계정이 있다면 새로 가입하거나 중복 결제하지 말고 B-2로 넘어가세요.

1. 브라우저에서 [Claude](https://claude.ai/)를 엽니다.
2. 계정이 있다면 로그인합니다. 없다면 화면의 가입 안내에 따라 이메일이나 제공되는 로그인 방식을 선택합니다.
3. 이메일 인증 등 화면에서 요청하는 절차를 완료합니다. 확인 메일이 오면 해당 메일의 안내에 따릅니다.
4. 로그인한 계정의 요금제 화면에서 Claude Code 이용 가능 여부를 확인합니다. 구매를 결정했다면 요금제 변경 또는 업그레이드 항목으로 이동합니다.
5. **Claude Code가 포함되는지, 월 결제인지 연 결제인지, 실제 결제 금액은 얼마인지** 확인하고 원하는 경우에만 구독을 진행합니다. 연간 요금의 월 환산 금액과 실제 청구 금액은 다를 수 있습니다.

완료 확인: **본인 계정으로 로그인할 수 있고, Claude Code를 이용할 수 있는 구독 또는 조직 권한이 있습니다.** 정확한 금액과 이용 조건은 [공식 요금 페이지](https://claude.com/pricing)를 확인하세요.

이 안내에서는 일반 Claude 계정으로 연결합니다. 별도 사용량 과금 계정인 Claude Console이나 API 키 설정은 사용하지 않습니다.

> **[스크린샷 자리 · Claude 계정 준비]**  
> 가입 진입 화면과 Claude Code 포함 여부를 확인할 수 있는 요금제 화면. 이메일과 결제 정보는 가려 주세요.
<!-- 교체 예: ![Claude 계정과 Claude Code 이용 권한 확인](./images/claude-account.png) -->

## B-2. VS Code에 Claude Code 설치하기

1. VS Code로 돌아옵니다.
2. 왼쪽의 네모 블록 모양 **Extensions(확장)** 아이콘을 누릅니다. Windows는 **Ctrl+Shift+X**, Mac은 **Cmd+Shift+X**로도 열 수 있습니다.
3. 검색창에 `Claude Code`를 입력합니다.
4. **게시자(Publisher)가 Anthropic인 공식 확장**을 선택합니다. 헷갈린다면 [공식 확장 페이지](https://marketplace.visualstudio.com/items?itemName=anthropic.claude-code)를 이용하세요.
5. **Install(설치)**을 누릅니다. 게시자 신뢰 확인이 나오면 공식 Anthropic 확장인지 확인하고 진행합니다.
6. 설치가 끝나도 나타나지 않으면 VS Code를 닫았다가 다시 엽니다.

완료 확인: **확장이 설치된 상태로 표시됩니다.** VS Code 1.94 이상이 필요하므로 오래된 버전에서 설치가 안 된다면 먼저 VS Code를 업데이트하세요. [공식 VS Code 확장 안내](https://code.claude.com/docs/en/vs-code)

확장에 대화에 필요한 실행 도구가 포함되어 있어, 이 경로에서는 별도의 Claude Code 명령어 도구를 설치하지 않아도 됩니다. Windows에서 Git for Windows가 없으면 PowerShell을 사용하는 경로도 제공됩니다. 첫 설치 때 Git·WSL·Node.js를 일괄 설치할 필요는 없습니다. 특정 오류가 나타날 때 해당 안내를 확인하세요. [확장 구성](https://code.claude.com/docs/en/vs-code), [Windows 실행 안내](https://code.claude.com/docs/en/quickstart)

> **[스크린샷 자리 · Claude Code 설치]**  
> 확장 이름, Anthropic 게시자, Install 버튼을 표시해 주세요.
<!-- 교체 예: ![Anthropic의 Claude Code 확장 설치](./images/claude-install.png) -->

## B-3. Claude Code에 계정 연결하기

1. Windows는 **Ctrl+Shift+P**, Mac은 **Cmd+Shift+P**를 누릅니다. VS Code 위쪽에 기능을 찾는 검색창이 열립니다.
2. `Claude Code`를 입력하고 **Open in New Tab(새 탭에서 열기)** 같은 열기 항목을 선택합니다.
3. Claude Code 화면에서 **Sign in(로그인)**을 누릅니다.
4. 로그인 방식이 여러 개라면 Claude 구독 계정으로 로그인하는 항목을 고릅니다.
5. 브라우저가 열리면 B-1에서 준비한 계정으로 로그인합니다. 유료 구독한 계정과 같은 이메일·로그인 방식인지 확인합니다.
6. 연결 승인 화면의 내용을 확인하고 진행합니다. 완료되면 VS Code로 돌아옵니다. 인증 코드를 돌려주라는 화면이 나온 경우에는 해당 화면의 지시에 따라 Claude Code 로그인 창에만 입력합니다.

완료 확인: **Claude Code 화면에 요청 입력창이 나타납니다.** 처음 사용 안내가 보이면 읽거나 닫고 진행할 수 있습니다. [공식 연결 안내](https://code.claude.com/docs/en/vs-code#get-started)

> **[스크린샷 자리 · Claude Code 로그인]**  
> Sign in 버튼과 연결 후 대화 입력창. 인증 코드와 개인 계정 정보는 가려 주세요.
<!-- 교체 예: ![Claude 계정을 VS Code에 연결](./images/claude-sign-in.png) -->

## B-4. 첫 대화 보내기

**브라우저의 Claude 페이지가 아니라 VS Code의 Claude Code 입력창**을 클릭합니다. 아래 문장을 붙여 넣고 보내기 버튼을 누르세요.

```text
나는 코딩을 처음 배워. 한국어로 짧게 인사해 줘. 아직 파일은 만들지 마.
```

완료 확인: **VS Code 안에서 답변이 나타납니다.** [Starter의 안내 파일 준비하기](../starter/README.md#2-ai에게-줄-안내-파일-준비하기)로 이동하세요.

Starter에서는 `AGENTS.md` 파일을 준비한 뒤, **그 파일을 읽어 달라는 첫 요청을 직접 보내세요.** 도구가 자동으로 읽었을 것이라고 가정하지 않아도 되도록 안내되어 있습니다.

> **[스크린샷 자리 · Claude Code 연결 확인]**  
> 연습 폴더 이름과 첫 요청, Claude Code의 답변이 함께 보이는 화면.
<!-- 교체 예: ![Claude Code의 첫 답변 확인](./images/claude-first-chat.png) -->

## 잘되지 않을 때

| 상황 | 해 볼 일 |
| --- | --- |
| 무료 Claude에서는 대화되는데 여기서는 안 돼요 | Claude Code가 포함된 구독인지 확인합니다. 웹 무료 채팅과 이용 범위가 다릅니다. |
| 결제했는데 업그레이드하래요 | 브라우저와 확장에 로그인한 계정이 같은지 확인합니다. 조직 계정이면 관리자에게 권한을 문의합니다. |
| Claude Code 아이콘이 안 보여요 | B-3의 명령 검색으로 엽니다. 오른쪽 위 아이콘은 파일을 열어야 보일 수 있습니다. |
| 설치할 수 없다고 나와요 | VS Code 버전을 확인하고 업데이트한 뒤 다시 설치합니다. |
| 브라우저 로그인 후에도 연결되지 않아요 | 브라우저에 남아 있는 승인·코드 전달 절차를 완료했는지 확인합니다. VS Code를 다시 열어 봅니다. |
| 사용량을 초과했대요 | 화면의 한도와 다시 사용할 수 있는 시간을 확인합니다. 유료 구독에도 사용량 제한이 있습니다. |
| 파일 수정 전에 허용을 물어요 | 내가 요청한 연습 파일의 변경인지 읽고 승인합니다. 이해하기 어렵다면 먼저 설명을 요청하세요. |

계속 문제가 생기면 [공식 문제 해결 안내](https://code.claude.com/docs/en/vs-code#fix-common-issues)를 참고하거나, 화면의 오류 문구와 멈춘 단계를 안내자에게 알려 주세요.
