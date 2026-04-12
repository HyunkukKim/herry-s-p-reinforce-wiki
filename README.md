# 🧠 P-Reinforce: The Autonomous Knowledge Gardener

[![GitHub Version](https://img.shields.io/badge/version-1.0.0--beta-blue.svg)](https://github.com/HyunkukKim/herry-s-p-reinforce-wiki)
[![Engine](https://img.shields.io/badge/Engine-P--Reinforce-green.svg)](https://github.com/HyunkukKim/herry-s-p-reinforce-wiki)

> **"지식의 파편을 위키의 숲으로."**  
> P-Reinforce는 Andre Karpathy의 'LLM-Wiki' 아키텍처와 강화학습(RL) 이론을 결합한 자율 지식 자동화 에이전트입니다.

---

## 🚀 Overview (개요)
P-Reinforce는 사용자가 던지는 무작위하고 파편화된 정보를 실시간으로 읽어들여, 스스로 의미를 분석하고 최적의 지식 트리(Folder Tree)를 구축합니다. 이 과정에서 발생하는 모든 액션은 사전에 정의된 **강화학습 보상 정책(Reward Function)**에 따라 최적화됩니다.

## 🏗️ Core Architecture (핵심 구조)

### 1. 📂 Folder Hierarchy
- **`00_Raw/`**: 수정되지 않은 데이터의 원본 저장소 (Source of Truth).
- **`10_Wiki/`**: 자율적으로 정원 가꾸기가 수행된 지식 층 (Projects, Topics, Decisions, Skills).
- **`20_Meta/`**: 에이전트의 두뇌 데이터 (Knowledge Graph, RL Policy, Index).

### 2. 🧠 RL-based Decision Logic
지식 배치 시 아래 보상 함수 $R$을 극대화하도록 설계되었습니다.
$$R = w_1(\text{Categorization Accuracy}) + w_2(\text{Graph Connectivity}) + w_3(\text{User Satisfaction})$$

- **Threshold**: 유사도 85% 이상 시 기존 폴더 유지, 미달 시 자동 새 카테고리 생성.
- **Refactoring**: 폴더 내 파일이 12개를 초과하면 지식의 하향 세분화(Refactoring)를 제안/수행합니다.

### 3. 🔗 Bi-directional Linking
모든 지식은 단순한 파일이 아닌, `[[Double Brackets]]` 형태의 쌍방향 링크로 연결되어 하나의 거대한 '외부 뇌'를 형성합니다.

---

## 📝 Wiki Document Template (표준 규격)
모든 문서는 아래와 같은 메타데이터와 구조를 가집니다.

```markdown
---
id: {{UUID}}
category: "[[10_Wiki/Path/To/Folder]]"
confidence_score: 0.0 ~ 1.0 (RL 기반 확신도)
tags: [tag1, tag2]
last_reinforced: YYYY-MM-DD
---

# [[문서 제목]]
## 📌 한 줄 통찰 (Summary)
## 📖 구조화된 지식 (Content)
## ⚠️ 모순 및 업데이트 (Update)
## 🔗 지식 연결 (Graph)
```

---

## 🛠️ Usage (사용 방법)
1.  **Input**: `00_Raw/` 폴더에 메모, PDF, 스크린샷 텍스트 등을 저장합니다.
2.  **Reinforce**: 에이전트(Antigravity)에게 지식 구조화를 요청합니다.
3.  **Sync**: 자동으로 지식 간 링크가 생성되고 GitHub에 버전이 기록됩니다.
4.  **Feedback**: 사용자가 폴더를 옮기거나 "굿"이라고 피드백하면 `Policy.md`에 반영되어 지능이 강화됩니다.

---
*Created & Maintained by P-Reinforce Engine.*
