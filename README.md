# quizletgravityhack
A simple yet useful hack for Quizlet Gravity.

Highlight and drag this code into your bookmarks bar:
`javascript:let mode = confirm("Ok=Answer w/ Definition\nCancel=Answer w/ Term") ? "term-def" : "def-term"; document.querySelector(".GravityGameplayView-typingPrompt").addEventListener(%27keyup%27, e => { if (e.keyCode == 18) { let terms = window.Quizlet["gravityModeData"].terms; let termsByDef = {}; for (let term of terms) { termsByDef[term.definition] = term.word; } let termsByWord = {}; for (let term of terms) { termsByWord[term.word] = term.definition; } for(let elmt of Array.from(document.querySelectorAll(".GravityTerm-text.TermText span"))) {navigator.clipboard.writeText(mode == "term-def" ? termsByWord[elmt.innerHTML] : termsByDef[elmt.innerHTML])} e.preventDefault();} })`

Click the created bookmarklet after starting a game of gravity. Press Alt to copy the correct answer to your clipboard.
