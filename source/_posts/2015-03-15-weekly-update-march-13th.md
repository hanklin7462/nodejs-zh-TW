title: "io.js 週報 2015.03.13"
date: 2015-03-15 09:02:55
tags:
categories: iojs 週報
---


# io.js 釋出 1.5.1 版

[@rvagg](https://github.com/rvagg) 在 3/9 (一) 釋出了 io.js [v1.5.1](https://iojs.org/dist/v1.5.1/)。可以在 [GitHub 上](https://github.com/iojs/io.js/blob/v1.x/CHANGELOG.md) 找到完整的變更日誌。

### 主要變更

* **tls**: 之前回報的 TLS 記憶體洩漏已經在這次釋出中藉由多個 commit 解決了。現在的測試指出，_可能_ 還有一些洩漏問題。完整的進度追蹤在 [#1075](https://github.com/iojs/io.js/issues/1075)。
* **http**: 修復一個回報在 [joyent/node#9348](https://github.com/joyent/node/issues/9348) 和 [npm/npm#7349](https://github.com/npm/npm/issues/7349) 的錯誤。當 `'error'` 事件發生時，待處理 (pending) 的資料沒有被完整讀出，導致 `socket.destroy()` 的一個 assert 失敗。 (Fedor Indutny) [#1103](https://github.com/iojs/io.js/pull/1103)

### 已知問題

* 可能仍然有與 TLS 相關的記憶體洩漏，細節請參閱 [#1075](https://github.com/iojs/io.js/issues/1075)。
* Windows 仍舊有使用者回報存在一些測試錯誤的情形，我們正優先追查這些問題的原因。請參閱 [#1005](https://github.com/iojs/io.js/issues/1005).
* 在 REPL 中代理對 (Surrogate pair) 會凍結終端 [#690](https://github.com/iojs/io.js/issues/690)
* 不能編譯 io.js 為靜態函式庫 [#686](https://github.com/iojs/io.js/issues/686)
* 1.0.2 重新加入的 `process.send()` 不如文件上所說為同步地，參閱 [#760](https://github.com/iojs/io.js/issues/760) 和 [#774](https://github.com/iojs/io.js/issues/774) 的修補
* 當 DNS 查詢進行到一半時呼叫 `dns.setServers()`，會導致程序當機並 assert 失敗 [#894](https://github.com/iojs/io.js/issues/894)

# 社群消息

* [Tony Pujals](https://twitter.com/subfuzion) 在 [BayNode](http://www.meetup.com/BayNode/events/220246228/) 做了一個關於 io.js 未來規劃的簡報。影片已經在 3/9 上傳到 [vimeo](https://vimeo.com/121707989)，簡報也可以提供給任何人於[各地討論會](ron.buell@rd.io)上使用。
* [Johan Bergström](https://github.com/jbergstroem) 為了 io.js 正準備向 [V8](https://codereview.chromium.org/990063002) 提交一個修補，要在最新版中加入對 Solaris 的支援。
* [NodeUp 84集](http://nodeup.com/eightyfour) 是有關 io.js 最新消息的第一集，參加者是 [Mikeal Rogers](https://github.com/mikeal)，[Trevor Norris](https://github.com/trevnorris)，以及 [Bradley Meck](https://github.com/bmeck)。
* [Mikeal Rogers](https://github.com/mikeal) 接受 [Descriptive](http://descriptive.audio) 於單元稱 [We've Never Had This Many Active Contributors to Core Before](http://descriptive.audio/episodes/12) 中接受採訪。
* [Mark Wolfe](https://twitter.com/wolfeidau) 在 [@melbjs](https://twitter.com/melbjs) 討論會上給了一個 [talk about io.js](https://twitter.com/wolfeidau/status/575785856545378304) 的簡報，
* [dockeri.co](http://dockeri.co/) 正式運行在 io.js 之上，你可以在[這邊](https://twitter.com/wjblankenship/status/575867637680369665)看到公告。
* [Node.js Advisory Board](https://nodejs.org/about/advisory-board/) 正式開始討論 [io.js/Node.js reconciliation proposal](https://github.com/iojs/io.js/issues/978) 和解草案，你可以在[這裡](https://github.com/joyent/nodejs-advisory-board/blob/master/meetings/2015-03-09/minutes.md#nodejsiojs-reconciliation-bb)看到會議記錄。
* 2015-03-11 的 io.js 技術委員會議可以在 [這裡](http://www.youtube.com/watch?v=xXLnNSL0qvU) 看到

# 即將舉行的活動

* [NodeConf](http://nodeconf.com/) 的門票正式販售，6/8~9 於加州奧克蘭。NodeConf Adventure 是 6/11~6/14 於加州沃克溪農場。
* [CascadiaJS](http://2015.cascadiajs.com/) 門票開賣，時間是 7/8~7/10 於華盛頓州。
* [NodeConf EU](http://nodeconf.eu/) 門票開賣，時間是 9/6~9/9 於愛爾蘭瓦特福。

原文：[io.js Week of March 13th](https://medium.com/node-js-javascript/io-js-week-of-march-13th-e3024cc66802)，作者：[@iojs](https://medium.com/@iojs)，翻譯 [@iojs-tw](https://github.com/iojs/iojs-tw)，授權 [CC-BY 4.0](https://creativecommons.org/licenses/by/4.0/deed.zh_TW)
