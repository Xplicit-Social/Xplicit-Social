<section>
<br>
<div align="center">
 <img src="https://github.com/user-attachments/assets/94569955-9ff1-4d72-ac50-702dda769869" width="30%">
</div>
<br>
<hr/>

🩷 **Adult Social Network**

<br>
<br>
<div align="center">
 <img src="https://github.com/user-attachments/assets/f4300c72-edec-4cab-b6c2-7fe1c8f39d37" width="45%">

 </div>

 <hr/>
 
  <h2>❌PLICIT Scalability Plan - From Scratch Architecture</h2>

  <h3>1. Micro-modules, not Microservices</h3>
  <ul>
    <li>Logical backend separation into business modules:
      <ul>
        <li><code>/modules/notifications/</code></li>
        <li><code>/modules/messages/</code></li>
        <li><code>/modules/media/</code></li>
      </ul>
    </li>
    <li>Goal: improved maintainability, targeted unit tests, clean evolution</li>
  </ul>

  <h3>2. Optimized Database</h3>
  <ul>
    <li>Flat tables for high-performance (e.g., notifications ✅)</li>
    <li>Systematic indexing on key columns: <code>userId</code>, <code>type</code>, <code>related_ids</code></li>
    <li>Logical partitioning (by user, date, or type)</li>
    <li>Minimal queries: no <code>SELECT *</code>, no complex joins</li>
    <li>Optional: Redis to accelerate hot-path reads</li>
  </ul>

  <h3>3. Centralized & Smart WebSocket</h3>
  <ul>
    <li>Single shared WebSocket endpoint (via <code>createBunWebSocket()</code>)</li>
    <li>Client managed via SharedWorker + HTTP REST fallback</li>
    <li>Supports multi-tab, WebView, mobile ✅</li>
    <li>No socket.io, no unnecessary multiplexing</li>
  </ul>

  <h3>4. Deduplication & ACKs</h3>
  <ul>
    <li>Unique <code>clientId</code> per client</li>
    <li>ACKs for each critical message (chat, notification)</li>
    <li>Buffer of received messageIds to avoid redundancy</li>
    <li>Filtering on both server and client (based on ID + timestamp)</li>
  </ul>

  <h3>5. Ultra-optimized Frontend Loading</h3>
  <ul>
    <li>TTFP via static HTML + modular JS ✅</li>
    <li>HTML templates using <code>&lt;template&gt;</code> + <code>cloneNode()</code> ✅</li>
    <li>Dynamic CSS loading per page (via <code>&lt;link&gt;</code>)</li>
    <li>Zero SPA, zero unnecessary framework, fast navigation</li>
  </ul>

  <h3>6. Sovereign-grade Security</h3>
  <ul>
    <li>Authentication via mTLS ✅</li>
    <li>HttpOnly cookies (no JWT, no OAuth) ✅</li>
    <li>Nginx HTTP/3 + TLS + Rate Limiting (if needed)</li>
    <li>Targeted logging only on sensitive endpoints</li>
  </ul>

  <h3>7. Lightweight & Effective Monitoring</h3>
  <ul>
    <li>Modular <code>console.log</code></li>
    <li>Bun inspect + per-module logs</li>
    <li><code>/status</code> endpoint with: uptime, WS connections, RAM, CPU</li>
  </ul>

  <h3>8. Full Memory Alpine Linux Optimization</h3>
  <ul>
    <li>Run containers in full memory mode for near-zero disk I/O</li>
    <li>Drastically reduces latency and maximizes throughput</li>
    <li>Fast reboot cycles and stateless micro-environment</li>
    <li>Ideal for ephemeral services and in-RAM computation layers</li>
  </ul>

  <h3>9. Future Horizontal Scaling (if load increases)</h3>
  <ul>
    <li>Secondary container <code>backend-chat</code> for intense WebSocket load</li>
    <li>Lightweight Redis pub/sub for cross-container sync</li>
    <li>Dedicated notification-worker if bulk sending becomes heavy</li>
  </ul>

  <hr>

  <h3>✅ Conclusion</h3>
  <p>Our from scratch stack is <strong>highly scalable</strong> as long as we stick to the philosophy of:<br>
  <strong>modularity, simplicity, and zero unnecessary cloud bloat</strong>.</p>
  <p>We can easily handle <strong>thousands of active users</strong> without migrating to Kubernetes or any GAFAM-grade infrastructure.</p>
  <p><strong>We're ready for the next level</strong> 🚀</p>

  <hr>
  </section>
