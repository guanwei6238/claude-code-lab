# claude-code-lab

[English](README.md) | 繁體中文

`claude-code-lab` 是一個用來測試 Claude Code 行為的小型範例專案。

目前這個 repo 先提供 `memory` 範例，透過一組互相衝突的指令與設定檔，讓你觀察 Claude Code 會如何從不同來源載入 memory。

## 目前示範內容

這個 repository 目前示範的是：

- `CLAUDE.md` 如何影響 Claude 的行為
- `.claude/CLAUDE.md` 如何影響 Claude 的行為
- `.claude/rules/*` 如何影響 Claude 的行為
- 如何透過 `setting.json` 遮罩特定文件
- 如何查看 Claude 實際載入了哪些 memory 來源

你可以透過比較 Claude 的回覆語言與預設程式語言，推測最後是由哪個指令來源優先生效。

## 使用方式

1. 先把範例提供的 home 設定複製到你的 Claude home 目錄。

```bash
$ mkdir -p ~/.claude
$ cp -r home.claude/* ~/.claude/
```

2. 進入 `memory` 範例目錄。

```bash
$ cd memory
```

3. 啟動 Claude Code。

```bash
$ claude
```

4. 輸入例如：

```text
hi
寫出一個程式 ...
```

## 觀察重點

請觀察：

- Claude 最後使用哪一種語言回覆
- 在沒有指定程式語言時，Claude 最後選擇輸出哪一種程式語言

這些輸出可以幫助你理解目前是哪些檔案生效了。

## 查看 Claude 載入的 Memory

在 Claude Code 裡執行：

```text
/memory
```

你可以看到 Claude 實際讀取了哪些 memory 相關內容。

## 遮罩特定檔案

你可以修改下列檔案，遮罩特定 memory 來源：

- `memory/.claude/setting.json`

透過 `claudeMdExcludes`，你可以排除：

- 特定的 `CLAUDE.md`
- `.claude/rules/` 底下的規則檔
- 其他 memory 相關檔案

修改設定後，再執行相同提示詞並比較結果，就能看出差異。

註：這個 repo 內另外放了 `settings.local.json` 作為額外的對照案例。

## 筆記

繁體中文筆記連結：

https://hackmd.io/@56etVO4MQ_OKWoWvbGAV_Q/S1XsEwSibe
