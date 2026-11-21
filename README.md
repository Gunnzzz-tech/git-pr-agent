

<br />

<div align="center">


<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://codium.ai/images/pr_agent/logo-dark.png" width="330">
  <source media="(prefers-color-scheme: light)" srcset="https://codium.ai/images/pr_agent/logo-light.png" width="330">
  <img src="https://codium.ai/images/pr_agent/logo-light.png" alt="logo" width="330">

</picture>
<br>
The Original Open-Source PR Reviewer
<br><br>
<a href="https://github.com/the-pr-agent/pr-agent/commits/main">
<img alt="GitHub" src="https://img.shields.io/github/last-commit/the-pr-agent/pr-agent/main?style=for-the-badge" height="20">
</a>
</div>

---

 This repository contains the open-source PR Agent Project. 
 It is not the Qodo free tier.
 
PR-Agent is an open-source, AI-powered code review agent and a community-maintained legacy project of Qodo. It is distinct from Qodo’s primary AI code review offering, which provides a feature-rich, context-aware experience. Qodo now offers a free tier that integrates seamlessly with GitHub, GitLab, Bitbucket, and Azure DevOps for high-quality automated reviews.



## Table of Contents

- [Getting Started](#getting-started)
- [Why Use PR-Agent?](#why-use-pr-agent)
- [Features](#features)
- [See It in Action](#see-it-in-action)
- [How It Works](#how-it-works)
- [Data Privacy](#data-privacy)
- [Contributing](#contributing)

## Getting Started

> [!NOTE]
> **Docker Hub namespace migration.** Releases `0.34.2` and later are published under [`pragent/pr-agent`](https://hub.docker.com/r/pragent/pr-agent). Older releases (up to and including `v0.31`) remain available at the legacy [`codiumai/pr-agent`](https://hub.docker.com/r/codiumai/pr-agent) namespace as a frozen archive — no new images are pushed there. Update any pinned `image:` / `docker pull` / `uses: docker://` references when upgrading to `0.34.2+`.

### 🚀 Quick Start for PR-Agent

#### 1. GitHub Action (Recommended)

Add automated PR reviews to your repository with a simple workflow file:

```yaml
# .github/workflows/pr-agent.yml
name: PR Agent
on:
  pull_request:
    types: [opened, synchronize]
jobs:
  pr_agent_job:
    runs-on: ubuntu-latest
    steps:
    - name: PR Agent action step
      uses: the-pr-agent/pr-agent@main
      env:
        OPENAI_KEY: ${{ secrets.OPENAI_KEY }}
        GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
```
[Full GitHub Action setup guide](https://docs.pr-agent.ai/installation/github/#run-as-a-github-action)

#### 2. CLI Usage (Local Development)

Run PR-Agent locally on your repository:
```bash
pip install pr-agent
export OPENAI_KEY=your_key_here
pr-agent --pr_url https://github.com/owner/repo/pull/123 review
```
[Complete CLI setup guide](https://docs.pr-agent.ai/usage-guide/automations_and_usage/#local-repo-cli)

#### 3. Other Platforms

- [GitLab webhook setup](https://docs.pr-agent.ai/installation/gitlab/)
- [BitBucket app installation](https://docs.pr-agent.ai/installation/bitbucket/)
- [Azure DevOps setup](https://docs.pr-agent.ai/installation/azure/)

[//]: # (## News and Updates)

[//]: # ()
[//]: # (## Aug 8, 2025)

[//]: # ()
[//]: # ()
[//]: # ()
[//]: # (## Jul 1, 2025)

[//]: # (You can now receive automatic feedback from Qodo Merge in your local IDE after each commit. Read more about it [here]&#40;https://github.com/qodo-ai/agents/tree/main/agents/qodo-merge-post-commit&#41;.)

[//]: # ()
[//]: # ()
[//]: # (## Jun 21, 2025)

[//]: # ()
[//]: # (v0.30 was [released]&#40;https://github.com/the-pr-agent/pr-agent/releases&#41;)

[//]: # ()
[//]: # ()
[//]: # (## Apr 30, 2025)

[//]: # ()
[//]: # (A new feature is now available in the `/improve` tool for Qodo Merge 💎 - Chat on code suggestions.)

[//]: # ()
[//]: # (<img width="512" alt="image" src="https://codium.ai/images/pr_agent/improve_chat_on_code_suggestions_ask.png" />)

[//]: # ()
[//]: # (Read more about it [here]&#40;https://docs.pr-agent.ai/tools/improve/#chat-on-code-suggestions&#41;.)

[//]: # ()
[//]: # ()
