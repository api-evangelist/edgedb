---
title: "How we sharded our test suite for 10x faster runs on GitHub Actions"
url: "https://www.geldata.com/blog/how-we-sharded-our-test-suite-for-10x-faster-runs-on-github-actions?ref=rss"
date: "2022-05-02"
feed_url: "https://www.geldata.com/rss.xml"
---
We use GitHub Actions for a heavy CI workflow consisting of thousands of tests that takes 2+ hours. But with a bit of cleverness, we parallelized our workflow and reduce the runtime to just 10 minutes.
