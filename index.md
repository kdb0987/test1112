---
layout: default
title: GitHub와 친해지기
description: 바이브코딩 분과 11월 정기 회의 연수 자료 — 코딩의 동반자, GitHub와 친해지기
---

<header class="hero">
  <div class="hero-in">
    <p class="meeting">바이브코딩 분과 11월 정기 회의</p>
    <h1><em>코딩의 동반자,</em><br>GitHub와 친해지기</h1>
    <p class="by">발표 <b>바이브코딩 분과장 김대붕</b></p>
    <svg class="graph" viewBox="0 0 880 130" role="img" aria-label="main 브랜치에서 feature 브랜치가 갈라졌다가 다시 합쳐지는 그림">
      <path class="ln main" d="M0 95 H880"/>
      <path class="ln feat" d="M200 95 C250 95 250 40 300 40 H600 C650 40 650 95 700 95"/>
      <circle class="dot" cx="70" cy="95" r="8" stroke="#3A4C78"/>
      <circle class="dot" cx="200" cy="95" r="8" stroke="#3A4C78"/>
      <circle class="dot late" cx="360" cy="40" r="8" stroke="#1FA88E"/>
      <circle class="dot late" cx="500" cy="40" r="8" stroke="#1FA88E"/>
      <circle class="dot late" cx="700" cy="95" r="10" stroke="#1FA88E" fill="#1FA88E"/>
      <circle class="dot" cx="820" cy="95" r="8" stroke="#3A4C78"/>
      <text x="0" y="122">main</text>
      <text class="late" x="360" y="20">feature</text>
    </svg>
  </div>
</header>

## 깃허브란? {#ch1}

제작하셨던 수많은 코드들, 잘 보관하고 계신가요?
{: .lead}

GitHub는 **코드 전용 저장 · 공유 · 공동작업 플랫폼**입니다.

### GitHub가 필요한 이유

- 저장 및 다운로드, 편집이 편리
- 버전 관리 가능
- 다른 수많은 개발자들의 오픈소스 접근
- 포트폴리오 등의 공유
{: .reasons}

### 버전 관리의 필요성

코드를 여러 차례 고치고 덧붙이다 보면, 폴더는 금세 이렇게 됩니다.

- 학급게시판.html
- 학급게시판_수정.html
- 학급게시판_최종.html
- 학급게시판_최종_진짜최종.html
- 학급게시판_최종_진짜최종(2).html ← 뭐가 바뀐 거지?
{: .files}

버전 관리는 **내가 무엇을 수정했는지 알아볼 수 있도록 기록**을 남기는 일입니다. 파일 이름 대신, 수정할 때마다 한 줄 메모와 함께 저장 시점을 남깁니다.

### Git과 GitHub

<div class="pair">
  <div class="card"><span class="tag">내 컴퓨터</span><strong>Git</strong><small>버전 입력 시스템. 수정할 때마다 기록을 남기는 도구입니다.</small></div>
  <div class="card"><span class="tag">인터넷</span><strong>GitHub</strong><small>코드 저장소. Git으로 남긴 기록을 올려 보관하고 공유하는 곳입니다.</small></div>
</div>

### “AI가 다 알아서 해주던데요?”

**자동화의 역설**: 영국의 심리학자 리잔 베인브리지가 1983년 ‘자동화의 아이러니’라고 이름 붙인 현상입니다.

> 기계가 일을 잘하게 돼 일상 업무를 자동화할수록 사람은 직접 수행할 기회를 점차 잃는다. 감시 책임은 사람에게 남지만, 바로 그 자동화 때문에 감시 능력은 퇴화한다.
>
> 리잔 베인브리지, 「자동화의 아이러니」(1983)

<div class="pair">
  <div class="card">
    <span class="tag">의료</span>
    <strong>폴란드의 관찰 연구</strong>
    <small>AI 보조 대장내시경 도입 후, AI 없이 검사했을 때의 선종 발견율</small>
    <div class="stat"><s>28.4%</s><i>→</i><b>22.4%</b></div>
  </div>
  <div class="card">
    <span class="tag">항공</span>
    <strong>미국 연방항공청, 2013</strong>
    <small>항공사들에 조종사가 수동 비행을 더 자주 하도록 권고했습니다. 비행 데이터를 분석해 보니 수동 조작 실수가 늘고 있었기 때문입니다.</small>
  </div>
</div>

자동조종이 완벽해질수록 사람이 직접 조종하는 시간을 일부러 남겨둬야 한다는 것. AI가 코드를 짜 주더라도 Git과 GitHub의 기본 개념은 직접 알고 있어야 하는 이유입니다.

## 깃허브에 코드 올리고, 내려받기 {#ch2}

필수 용어와 개념부터, 알고는 있자!

### 필수 용어

Repository
: 프로젝트 폴더. 코드와 그 수정 기록이 함께 담긴 저장소입니다.

Branch
: 수정을 위한 복사본. 원본(main)을 건드리지 않고 따로 고쳐 볼 수 있습니다.

Fork
: 남의 레포지토리를 내 계정으로 통째로 복사해 오는 것입니다.

### Git 명령어

처음 한 번, 커밋에 기록될 작성자 이름과 이메일을 설정합니다.

```bash
git config --global user.name "새이름"
git config --global user.email "새계정@이메일.com"
```

| 명령어 | 뜻 |
|---|---|
| `git init` | git 저장소(폴더)를 만들어! |
| `git add .` | 현재 폴더에 있는 파일 선택(스테이징)할게! |
| `git commit -m "할말"` | “할말”로 버전 기록해 줘! |
| `git branch -M main` | 기본 브랜치 이름을 main으로 변경! Git의 기본 이름 master를 GitHub의 기본 이름 main에 맞춥니다. |
| `git remote add origin 주소` | origin이라는 이름으로 GitHub 레포지토리에 연결해 줘! |
| `git push -u origin main` | origin의 main에 업로드해 줘! |
| `git switch -c feature` | feature라는 브랜치 만들어서 이동해! |

### 올리기와 내려받기

학교 컴퓨터에서 작업하다가, 우리 집에 왔을 때!

<div class="track">
  <div class="node"><i>🏫</i><b>학교 컴퓨터</b><small>main</small></div>
  <div class="edge"><span>push</span></div>
  <div class="node hub"><i>☁</i><b>GitHub</b><small>origin / main</small></div>
  <div class="edge"><span>pull · clone</span></div>
  <div class="node"><i>🏠</i><b>집 컴퓨터</b><small>main</small></div>
</div>

### pull과 clone의 차이

| 명령어 | 언제 쓰나요? |
|---|---|
| `git clone 레포지토리주소` | 내 컴퓨터에 아직 없을 때. 저장소 전체를 처음 통째로 내려받습니다. |
| `git pull origin main` | 이미 받아 둔 폴더가 있을 때. 바뀐 부분만 가져와 최신으로 맞춥니다. |

### Fork와 Clone의 차이

| 방법 | 수정 후 push | 설명 |
|---|---|---|
| clone만 | <span class="nope">불가</span> | repository가 내 소유가 아니므로 올릴 수 없습니다. |
| clone → 새 repository 생성 후 push | <span class="yes">가능</span> | 하지만 원본 소스코드에 pull request를 보내기 어렵습니다. |
| fork → clone | <span class="yes">가능</span> | 내 소유의 사본을 만든 뒤 내려받으므로 push도, 원본에 pull request도 할 수 있습니다. |

### 실습하기

웹페이지를 하나 만들어 GitHub에 직접 업로드해 봅시다.

```bash
# 1. 로컬 저장소 초기화
git init
# 2. 파일 추가 및 첫 커밋
git add .
git commit -m "First commit"
# 3. 기본 브랜치 이름을 main으로 맞춤
git branch -M main
# 4. 방금 만든 GitHub 저장소 주소 등록
git remote add origin 주소
# 5. 원격 저장소로 첫 업로드
git push -u origin main
```

### git status: 작업 디렉토리와 스테이징 영역 확인

파일은 세 가지 상태 중 하나에 있습니다. 아래 버튼을 눌러 파일이 어떻게 옮겨 다니는지 확인해 보세요.

<div class="sim" aria-live="polite">
  <div class="zone untracked"><h4>Untracked files</h4><p>새로 생겨 Git이 한 번도 추적한 적 없는 파일</p><div id="z-untracked"></div></div>
  <div class="zone modified"><h4>Changes not staged</h4><p>추적 중이지만 수정 후 아직 git add 하지 않은 파일</p><div id="z-modified"></div></div>
  <div class="zone staged"><h4>Changes to be committed</h4><p>git add로 스테이징 영역(장바구니)에 올라간 파일</p><div id="z-staged"></div></div>
</div>
<div class="controls">
  <button type="button" id="b-edit">파일 수정하기</button>
  <button type="button" id="b-add">git add .</button>
  <button type="button" id="b-commit">git commit</button>
  <output id="sim-msg"></output>
</div>
<ul class="commits" id="commits"></ul>

## 깃허브 탐색하기 {#ch3}

Reverse Engineering 맛보기. 클로드 skill 저장소를 함께 살펴보며 레포지토리 화면의 메뉴를 익혀 봅니다.

### 레포지토리 상단 메뉴

| 메뉴 | 하는 일 |
|---|---|
| **Code** | 코드 파일 |
| **Pull requests** | 수정 요청 |
| **Agents** | 이 저장소와 관련된 AI 코딩 에이전트 작업을 보는 곳 |
| **Actions** | 테스트나 빌드 같은 자동 작업의 실행 결과를 보는 곳 |
| **Projects** | 할 일을 표나 보드로 정리하는 곳 |
| **Security and quality** | 보안과 코드 품질 관련 정보 |
| **Insights** | 기여자와 변경 활동 등 통계 확인 |

## REA 설치 및 체험하기 {#ch4}

클로드 코드로 이미 있는 프로그램을 분석하고 다시 만들어 봅니다.

<div class="pair">
  <div class="card"><span class="tag">게임</span><strong>지뢰찾기</strong><small>분석 후 재현하기</small></div>
  <div class="card"><span class="tag">도구</span><strong>그림판</strong><small>분석 후 재현하기</small></div>
</div>

<section class="qna" id="qna">
  <strong>QnA</strong>
  <p>궁금한 점을 자유롭게 질문해 주세요.</p>
</section>
