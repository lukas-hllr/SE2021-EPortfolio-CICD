# Software für die Live-Demo

Hey! Wenn du während der Live-Demo gemeinsam mit mir Programmieren möchstest, musst du folgende Software mitbringen.

## Accounts
- GitHub Account
- Microsoft Azure Account (im Idealfall als Teil des Bildungsprogramms)

## Software
- VS-Code oder JetBrains WebStorm
- Docker
- Node.js (v16.15.0)
- Angular CLI (v13.3.5)
- Ionic CLI (v6.19.1)

# GitHub Actions

GitHub Actions ist die CI/CD Plattform von GitHub. Der Service ermöglicht dir mit dem gleichen Service mit dem du deine Codebasis verwaltest, auch automatisiertes Testing, Deployment und Releasing zu veralten. GitHub stellt hierfür virtuelle Maschinen folgender Betriebssysteme bereit:

- Linux,
- Windows,
- macOS

Der Services ist weitestgehend kostenlos. Lediglich besonders hohe Anforderungen an Rechenleistung und Rechenzeit fallen aus dem kostenlosen Rahmen. Unsere "kleinen" Projekte sind von diesen Leistungsgrenzen glücklicherweise weit entfernt. Genaure Infos hierzu erhälst du [hier](https://docs.github.com/en/actions/learn-github-actions/usage-limits-billing-and-administration).

GitHub Actions Workflows sind durch .yml Dateien definiert. Ein beispielhafter Workflow um ein Angular/Ionic Projekt zu testen sieht folgendermaßen aus.

```YAML
name: Run Unit Tests

on:
  push

jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v2

      - name: Setup Node.js
        uses: actions/setup-node@v1
        with:
          node-version: 17.x

      - name: Install app dependencies
        run: npm install

      - name: Run Unit Tests
        run: npm test
```

Steps mit einem `uses` Parameter verwenden Aktionen vom [GitHub Actions Marketplace](https://github.com/marketplace?type=actions). Dort findest du viele vordefinierte Worflows, die deine Workflows schlank halten können.

# Microsoft Azure

Azure ist die Cloudplattform von Microsoft. Als Student kannst du kostenlos Teil des Azure Bildungsprogramms werden. Dort erhälst du jährlich 100$, womit du beliebige Cloud-Services von Azure in Anspruch nehmen kannst.

Für unsere Zwecke in der SE-Vorlesung eignen sich vor allem die folgenden Services:
- Azure Web Services
- Azure SQL Databases
- [uvm.](https://azure.microsoft.com/de-de/free/students/)

Da sowohl Azure als auch GitHub Dienste von Microsoft sind arbeiten sie Lückenlos zusammen. Beim Erstellen eines WebServices kannst du mit wenigen Klicks einen GitHub Actions Workflow erstellen lassen, der deinen Code in der Cloud verfügbar macht.

Teil des Bildungsprogrammes werden kannst du [hier](https://azure.microsoft.com/de-de/free/students/).

Dein kostenloses Guthaben verwalten kannst du [hier](https://www.microsoftazuresponsorships.com/).