<script setup>
const features = [
  {
    title: '智能搜索',
    desc: '面向企业知识库的一体化检索，毫秒级召回与多轮追问。',
    img: '/a1.jpeg'
  },
  {
    title: '多模态理解',
    desc: '支持文本、图片与结构化数据的统一理解与生成。',
    img: '/a1.jpeg'
  },
  {
    title: '高可用部署',
    desc: '云边一体与私有化部署，SLA 99.95% 可用性保障。',
    img: '/a2.jpeg'
  }
]

const plans = [
  { name: 'Starter', price: '¥0', items: ['每月 1 万次调用', '社区支持', '基础 API'] },
  { name: 'Pro', price: '¥499', items: ['每月 50 万次调用', '优先支持', '向量检索与RAG'] },
  { name: 'Enterprise', price: '联系销售', items: ['无限调用配额', 'SLA 合同', '私有化部署'] }
]
</script>

<template>
  <div class="ai-site" id="captureBody">
    <section class="hero">
      <div class="container">
        <div class="hero-text">
          <h1>智域 AI — 新一代企业级智能平台</h1>
          <p>用生成式人工智能重构知识工作流，从检索、洞察到决策全链路赋能。</p>
          <div class="cta">
            <a class="btn primary" href="#pricing">立即开始</a>
            <a class="btn ghost" href="#features">查看功能</a>
          </div>
        </div>
        <div class="hero-media">
          <img src="/a3.jpeg" alt="AI Illustration" />
        </div>
      </div>
    </section>
  </div>
  
</template>

<style scoped>
.ai-site {
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, 'Helvetica Neue', Arial, 'PingFang SC', 'Hiragino Sans GB', 'Microsoft YaHei', sans-serif;
  color: #0f172a;
  background: #ffffff;
}

.container {
  width: 100%;
  max-width: 1120px;
  margin: 0 auto;
  padding: 0 20px;
}

.btn {
  display: inline-block;
  padding: 12px 18px;
  border-radius: 10px;
  text-decoration: none;
  transition: all .2s ease;
  font-weight: 600;
}

.btn.primary { background: #3b82f6; color: #fff; }
.btn.primary:hover { background: #2563eb; }
.btn.ghost { background: rgba(59,130,246,.1); color: #2563eb; }
.btn.ghost:hover { background: rgba(59,130,246,.15); }

.hero {
  background: linear-gradient(180deg, #eaf2ff 0%, #ffffff 100%);
  padding: 80px 0;
}
.hero .container { display: grid; grid-template-columns: 1.1fr 0.9fr; gap: 32px; align-items: center; }
.hero h1 { font-size: 44px; line-height: 1.2; margin: 0 0 16px; letter-spacing: .2px; }
.hero p { font-size: 18px; color: #334155; margin: 0 0 24px; }
.hero .cta { display: flex; gap: 12px; }
.hero-media img { width: 100%; height: 420px; object-fit: cover; border-radius: 16px; box-shadow: 0 10px 30px rgba(2,6,23,.08); }

.features { padding: 72px 0; background: #fff; }
.features h2 { font-size: 32px; margin: 0 0 28px; }
.features .grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 20px; }
.features .card { background: #f8fafc; border: 1px solid #e2e8f0; border-radius: 14px; padding: 16px; }
.features .card img { width: 100%; height: 180px; object-fit: cover; border-radius: 10px; margin-bottom: 12px; }
.features .card h3 { margin: 8px 0 6px; font-size: 20px; }
.features .card p { margin: 0; color: #475569; line-height: 1.6; }

.showcase { padding: 80px 0; background: linear-gradient(180deg, #ffffff 0%, #f6f8fb 100%); }
.two-col { display: grid; grid-template-columns: 1fr 1fr; gap: 28px; align-items: center; }
.showcase .text h2 { font-size: 30px; margin: 0 0 12px; }
.showcase .text p { color: #475569; margin: 0 0 12px; }
.showcase .text ul { margin: 0; padding-left: 18px; color: #334155; }
.showcase .media img { width: 100%; height: 360px; object-fit: cover; border-radius: 14px; box-shadow: 0 10px 30px rgba(2,6,23,.08); }

.testimonials { padding: 72px 0; background: #ffffff; }
.testimonials h2 { font-size: 30px; margin: 0 0 24px; }
.testimonials-grid { grid-template-columns: repeat(3, 1fr); }
.testimonials .tcard { background: #0f172a; color: #e2e8f0; border-radius: 14px; padding: 20px; line-height: 1.7; box-shadow: 0 6px 18px rgba(2,6,23,.15); }
.testimonials .tcard span { display: block; color: #94a3b8; margin-top: 10px; font-size: 14px; }

.pricing { padding: 80px 0; background: linear-gradient(180deg, #f6f8fb 0%, #ffffff 100%); }
.pricing h2 { font-size: 30px; margin: 0 0 26px; }
.pricing-grid { grid-template-columns: repeat(3, 1fr); }
.pcard { background: #ffffff; border: 1px solid #e2e8f0; border-radius: 16px; padding: 20px; box-shadow: 0 6px 18px rgba(2,6,23,.05); display: flex; flex-direction: column; gap: 10px; }
.pcard .price { font-size: 28px; font-weight: 700; color: #0f172a; }
.pcard ul { margin: 0; padding-left: 18px; color: #334155; flex: 1; }

.cta-final { padding: 84px 0; background: #0f172a; color: #e2e8f0; text-align: center; }
.cta-final h2 { margin: 0 0 10px; font-size: 32px; }
.cta-final p { margin: 0 0 16px; color: #cbd5e1; }

.footer { padding: 32px 0; background: #0b1220; color: #94a3b8; }
.footer .container { display: grid; grid-template-columns: 1fr auto 1fr; align-items: center; }
.footer .brand { color: #e2e8f0; font-weight: 700; letter-spacing: .3px; }
.footer .links { display: flex; gap: 14px; justify-content: center; }
.footer .links a { color: #cbd5e1; text-decoration: none; font-size: 14px; }
.footer .links a:hover { color: #ffffff; }
.footer .copy { text-align: right; font-size: 12px; }

@media (max-width: 960px) {
  .hero .container { grid-template-columns: 1fr; }
  .two-col { grid-template-columns: 1fr; }
  .features .grid, .testimonials-grid, .pricing-grid { grid-template-columns: 1fr; }
  .hero-media img { height: 300px; }
}

/* 通过固定的段落内边距和图像高度，整体高度约在 2600~3200px */
</style>


