# Personal Finance // Hungary 💶 🇭🇺

A weblap célja, hogy összegezze a magyarországi befektetési lehetőségeket, és azokat érthetővé tegye. A weboldal nem vállal felelősséget a tartalmak pontosságáért, és nem ad befektetési tanácsot.

Az ihlet az [UKPersonalFinance](https://arc.net/l/quote/gtpbdgvr) reddit sub-ról származik, ami szintén gyártott [egy hasonló oldalt](https://pypi.org/project/mkdocs-material/).

A site automatikusan deployolódik GitHub Pages-re: [https://hungarypersonalfinance.github.io/website/](https://hungarypersonalfinance.github.io/website/).

## Fejlesztés

Egy mkdocs nevű Python library-vel épül a site, ami szimpla markdown file-ból html-t generál. A website "skinje" a [Material for Mkdocs](https://pypi.org/project/mkdocs-material/), ami egy csomó feature-t tartalmaz.

Elindításához pár opció legegyszerűbbtől a bonyolultabbig:

- futtatod a [.vscode/tasks.json](.vscode/tasks.json)-ben is megtalálható commandot

```shell
docker run -it -p 8000:8000 -v ${PWD}:/docs python:3.11-alpine sh -c "cd /docs && pip install -r requirements.txt && mkdocs serve -a 0.0.0.0:8000"
```

- VS Code user-ek: `Command + Shift + P` -> `Run Task` -> `Serve website in Docker`
- VS Code user-ek: meg tudod nyitni a workspace-t konténerben a [Dev Containers](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers) extension-nel. fel fogja kínálni egy pop-upban.
- csinálsz egy virtualenv-et, aktiválod, felrakod a [requirements.txt](requirements.txt) tartalmát, végül `mkdocs serve`-t futtatsz

A site a 8000-es porton lesz elérhető: [http://localhost:8000](http://localhost:8000). A `serve` parancs live-reloadot is tartalmaz. 😉

### Fejlesztési tippek

Markdown lintert futtatunk a CI közben, a [.vscode/extensions.json](.vscode/extensions.json) alapján kapni fogsz egy pop-upot hogy szeretnéd-e az ajánlott extensions-öket felrakni. Minimum a [markdownlint](https://marketplace.visualstudio.com/items?itemName=DavidAnson.vscode-markdownlint)-et érdemes, hogy ne a CI-nál kapd meg a hibákat.
