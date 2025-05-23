<template>
  <div class="about">
    <article class="project-intro">
      <h1>數學診療室：AI 輔助的數學學習診斷工具</h1>

      <div class="meta-info">
        <time>2025-05-24更新</time>
        <div class="tags">
          <span class="tag">教育</span>
          <span class="tag">AI</span>
          <span class="tag">數學教育</span>
          <span class="tag">自由數學</span>
        </div>
      </div>

      <div class="description">
        <p>很多學習者在學數學時遇到的困難，都不只是當前的單元學不會，而是先備知識有漏洞。</p>

        <p>正如波利亞在《怎樣解題》一書中提到的：「當你解決不了一個問題時，一定有一些更基本的問題你還不懂一一找到它們吧！」</p>

        <p>古人說，了解自己不了解什麼東西，是一種智慧。這並不是大家都很容易辦到的事。</p>

        <p>專業的數學教育工作者，其專業之一，很重要的是倒溯法，也就是透過有系統的佈題測驗，往前回推協助學習者找到他基本知識和先備知識的不足之處，找到學生的「近測發展區」，也就是教學真正有效的範圍與程度。</p>

        <div class="example">
          <p>舉例來說，一個對小數學習有困難的學生，很可能是因為分數的概念不好，而分數概念不好，可能是因為對除法和餘數的處理並不了解。所以有經驗的教學者會針對這些先備知識做加強，而不是一直要他做小數單元的題目。</p>
        </div>

        <p>自由數學新上線的實驗功能「數學診療室」，結合 AI 自動佈題與教師手動建立的「先備後續關係資料庫」與開放式的形成性教材，並不是為了取代教育工作者，而是協助教育工作者與數學上遇到困難的學生，透過實際操作了解倒溯先備知識的的重要性。</p>

        <p>歡迎測試並提供意見回饋。</p>
      </div>

      <div class="links">
        <h2>相關連結</h2>
        <ul>
          <li><a href="https://math.alearn.org.tw/one1" target="_blank">倒溯法說明</a></li>
          <li><RouterLink to="/">數學診療室(Beta版)</RouterLink></li>
        </ul>
      </div>
    </article>
  </div>
</template>

<script>
export default {
  name: 'AboutView'
}
</script>

<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    padding: 20px;
    max-width: 800px;
    margin: 0 auto;
  }
}

.project-intro {
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;
  line-height: 1.6;
  color: #333;
}

h1 {
  font-size: 2.5em;
  margin-bottom: 1em;
  color: #2c3e50;
}

.meta-info {
  margin-bottom: 2em;
  color: #666;
}

.tags {
  margin-top: 0.5em;
}

.tag {
  display: inline-block;
  background: #e1f5fe;
  color: #0288d1;
  padding: 0.2em 0.6em;
  border-radius: 3px;
  margin-right: 0.5em;
  font-size: 0.9em;
}

.description {
  margin-bottom: 2em;
}

.description p {
  margin-bottom: 1em;
}

.example {
  background: #f8f9fa;
  padding: 1em;
  border-left: 4px solid #2196f3;
  margin: 1.5em 0;
}

.links {
  margin-top: 2em;
  padding-top: 1em;
  border-top: 1px solid #eee;
}

.links h2 {
  font-size: 1.5em;
  margin-bottom: 1em;
  color: #2c3e50;
}

.links ul {
  list-style: none;
  padding: 0;
}

.links li {
  margin-bottom: 0.5em;
}

.links a {
  color: #2196f3;
  text-decoration: none;
}

.links a:hover {
  text-decoration: underline;
}

time {
  color: #666;
  font-size: 0.9em;
}
</style>
