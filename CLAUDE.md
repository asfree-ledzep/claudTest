# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## 언어 지침

모든 결과값과 설명은 반드시 한글로 작성한다. 코드 주석, 커밋 메시지, 사용자 응답 등 모든 텍스트 출력은 한글을 기본으로 한다.

## Project Overview

Single-file web calculator (`calculator.html`). No build system, package manager, or external dependencies — everything is self-contained in one HTML file.

## Running the Project

Open `calculator.html` directly in a browser:

```powershell
Start-Process "C:\Users\LENOVO\claud_code_workspace\calculator.html"
```

## Architecture

All code lives in `calculator.html` with three sections:

- **CSS** (`<style>`): 3D-styled dark purple theme. Buttons use box-shadow layering to simulate physical depth. `preserve-3d` and `rotateX` were intentionally removed from `.scene` and `.calculator` to prevent click detection misalignment.
- **HTML** (`<body>`): 4-column CSS grid button layout. Button types: `btn-number`, `btn-operator`, `btn-equal`, `btn-clear`, `btn-special`.
- **JavaScript** (`<script>`): State is four variables — `current`, `previous`, `operator`, `shouldReset`. Inline `onclick` handlers call global functions. Keyboard input is supported via `keydown` listener.

### Calculator State Flow

```
inputNumber / inputDot → updates current
inputOperator → saves current→previous, sets operator, sets shouldReset=true
calculate → computes previous op current, result becomes new current
clearAll → resets all state to initial
```
