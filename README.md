# TestDriver [Web]

TestDriver is an AI QA Agent for GitHub. TestDriver allows you to run UI tests on your software using plaintext prompts. Every TestDriver test spawns an ephemeral VM and uploads the results to [Dashcam](https://dashcam.io) for easy debugging.

# Getting Help

TestDriver is made by [Dashcam](https://dashcam.io). Please [join the Dashcam discord for support and questions](https://discord.gg/6TUKZdfCze).

# Getting Started

## Fork This Template Repository

This template repository has the recommended settings for testing websites in Google Chrome with TestDriver. Begin by forking this template repository. Make the repository public or invite the Dashcam staff into your private repository so we can better support you.

<img width="208" alt="CleanShot 2024-03-08 at 16 59 12@2x" src="https://github.com/dashcamio/testdriver-web/assets/318295/b3d6970b-38ba-4a59-9f4c-c9a90a4047e5">

## Add your prompt to the GitHub Action

Dashcam is powered by [our TestDriver GitHub Action](https://github.com/dashcamio/testdriver), there are more details there outlining how TestDriver works. Add your test steps to the `.github/workflows/pr.yml` file under `prompt`.

```yml
name: TestDriver.ai

jobs:
  test:
    name: "TestDriver"
    runs-on: ubuntu-latest
    steps:
      - uses: dashcamio/testdriver@main
        id: testdriver
        with:
          prompt: |
            1. navigate to youtube.com in google chrome
            1. search for cat videos
            1. click the first one
```

### Tips on Prompting

The best way to write your prompt is to open an incognito window and perform the test acttions yourself. Write down each step you take.

1. Every step should be a single action
2. Steps are short and clear. The more information, the more likely TestDriver will be confused.
3. TestDriver works great with text, icons, shapes, and colors. It doesn't work as well with precise positioning (100px above, next to, etc).

## Test Results

TestDriver reports it's results within the GitHub actions interface. 

![CleanShot 2024-03-08 at 17 20 42@2x](https://github.com/dashcamio/testdriver-web/assets/318295/83185198-0550-42c5-ae3e-3734e5e1ddee)

Once you click `Details` you can view the AI-generated test summary and Dashcam results under `Summary`. Click "View Recording" or click on the thumbnail to launch the Dashcam interface.

<img width="1459" alt="CleanShot 2024-03-08 at 17 21 45@2x" src="https://github.com/dashcamio/testdriver-web/assets/318295/b90d6e20-9ff3-476f-8d78-223fa2f76385">

## Dashcam Replay

### AI Logs



### Chrome Logs

The Chrome console logs and network requests are available under the "Chrome" tab:

![CleanShot 2024-03-08 at 17 25 18@2x](https://github.com/dashcamio/testdriver-web/assets/318295/70d3e77c-342f-46cc-95c1-5765bc1fa993)

# Roadmap

- [x] Mac Support
- [ ] Windows Support (5 minutes faster and 10x scale)
- [ ] Account Linking
  - [ ] Publi<img width="1495" alt="CleanShot 2024-03-08 at 17 23 49@2x" src="https://github.com/dashcamio/testdriver-web/assets/318295/c2c6bfe6-0482-4f95-bf48-4d3ffe361487">
sh to your own Dashcam.io Account   
  - [ ] Choose Dashcam Project to upload to
- [ ] Publish GitHub action into the store
- [ ] Streaming results
  - [ ] Streaming Video
  - [ ] Streaming Logs
- [ ] TestDriver Model V2
- [ ] Interface updates
  - [ ] Auto-focus AI logs in Dashcam.io
- [ ] Test Reporting and Analyitcs Dashboard
