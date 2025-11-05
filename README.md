<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Governa Cloud - Technical README</title>
</head>
<body>

<h1>👋 About Me</h1>
<p>Hi, I’m Nicolas!</p>
<p>I’m a technical founder and architect. This page details my work on <strong>Governa Cloud</strong>, highlighting the product reasoning, platform design, and technical architecture behind the system.</p>

<h2>🏗️ Three-Layer Platform Architecture</h2>
<p>The platform is designed as a clear three-layer structure:</p>
<ol>
  <li><strong>Front-End Layer:</strong> React application, hosted separately on its own VM and volume, managing all UI and state for profiles, forums, dashboards, and forms.</li>
  <li><strong>Back-End Layer:</strong> Node.js / Express microservices handling business logic. API wrappers are used for security and internal porting.</li>
  <li><strong>Infrastructure & Database Layer:</strong> Mounted on VMs and volumes. Includes open-source PostgreSQL databases, AI LLM storage, and Kafka notification systems. Internal subnets connect back-end services securely to databases.</li>
</ol>

<h2>📝 Biography & Product Reasoning</h2>

<h3>1️⃣ Product & Platform Vision</h3>
<ol>
  <li>Governa Cloud is a <strong>policy collaboration platform</strong> combining:
    <ul>
      <li>Community discussions (Reddit-style)</li>
      <li>Professional networking (LinkedIn-style)</li>
    </ul>
  </li>
  <li>Supports millions of users with modular, scalable infrastructure.</li>
  <li>Core platform features:
    <ul>
      <li>Forums with threaded posts, moderation, and tagging</li>
      <li>User profiles with dynamic credentials, education, publications, and interests</li>
      <li>Real-time & asynchronous chat</li>
      <li>AI-powered insights & summarizations</li>
      <li>Analytics dashboards monitoring activity</li>
      <li>Event-driven notifications via Kafka</li>
    </ul>
  </li>
  <li>Architecture follows <strong>separation of concerns</strong>, making services modular and maintainable.</li>
</ol>

<h3>2️⃣ Infrastructure Layer & Databases</h3>
<ul>
  <li><strong>Transactional Database:</strong> PostgreSQL (open-source, volume-mounted), storing core entities: users, profiles, posts, forums.</li>
  <li><strong>Analytics Database:</strong> Aggregated metrics and logs for dashboards; separate service/controller/router layer.</li>
  <li><strong>Message Database:</strong> Dedicated DB for chat messages; separate service/controller/router to decouple messaging.</li>
  <li><strong>AI / LLM Storage:</strong> Granite AI open-source model, mounted on its own VM; queries transactional, analytics, and index databases.</li>
  <li><strong>Index / Search Database:</strong> Optimized indices for search, AI summarization, and analytics queries.</li>
  <li><strong>Kafka Notification Service:</strong> Event-driven architecture for asynchronous notifications, connected to all relevant databases.</li>
</ul>

<h3>3️⃣ Back-End Layer: Services, Controllers & Routers</h3>
<p>Each database/service has a corresponding service/controller/router layer for modularity:</p>

<ul>
  <li><strong>Transactional DB:</strong>
    <ul>
      <li>Service: TransactionalService</li>
      <li>Controller: TransactionalController</li>
      <li>Router: TransactionalRouter</li>
    </ul>
  </li>
  <li><strong>Analytics DB:</strong>
    <ul>
      <li>Service: AnalyticsService</li>
      <li>Controller: AnalyticsController</li>
      <li>Router: AnalyticsRouter</li>
    </ul>
  </li>
  <li><strong>Message DB:</strong>
    <ul>
      <li>Service: MessageService</li>
      <li>Controller: MessageController</li>
      <li>Router: MessageRouter</li>
    </ul>
  </li>
  <li><strong>AI / LLM:</strong>
    <ul>
      <li>Service: AIService</li>
      <li>Controller: AIController</li>
      <li>Router: AIRouter</li>
    </ul>
  </li>
  <li><strong>Index/Search DB:</strong>
    <ul>
      <li>Service: SearchService</li>
      <li>Controller: SearchController</li>
      <li>Router: SearchRouter</li>
    </ul>
  </li>
  <li><strong>Kafka Notifications:</strong>
    <ul>
      <li>Service: NotificationService</li>
      <li>Controller: NotificationController</li>
      <li>Router: NotificationRouter</li>
    </ul>
  </li>
</ul>

<h3>4️⃣ Front-End Layer & API Interaction</h3>
<ul>
  <li>React app hosted on a dedicated VM and volume.</li>
  <li>Components are modular and self-contained (e.g., PostForm manages its own state).</li>
  <li>Front-end communicates with back-end via REST APIs using secure internal porting and subnets.</li>
  <li>Service wrappers ensure clean abstraction and allow API evolution without impacting UI.</li>
</ul>

<h3>5️⃣ Data Flow Examples</h3>

<p><strong>Transactional Flow:</strong></p>
<ol>
  <li>User creates a post → front-end calls <code>POST /posts</code></li>
  <li>TransactionalController validates input → TransactionalService inserts into DB</li>
  <li>Event emitted → Kafka triggers notifications</li>
  <li>AnalyticsService consumes event → updates metrics</li>
</ol>

<p><strong>Profile Update Flow:</strong></p>
<ol>
  <li>User updates profile → <code>PUT /profile/:id</code></li>
  <li>ProfileController validates → ProfileService updates transactional DB</li>
  <li>Optional propagation → Analytics DB / Index DB for dashboards and AI queries</li>
</ol>

<p><strong>AI Query Flow:</strong></p>
<ol>
  <li>Front-end requests summary → <code>GET /ai/summary?forumId=xyz</code></li>
  <li>AIController fetches data from Index DB → LLM generates output</li>
  <li>Response returned to front-end; optionally cached</li>
</ol>

<h3>6️⃣ Deployment & Scalability</h3>
<ul>
  <li>VM and volume isolation for independent scaling and fault tolerance</li>
  <li>Open-source Postgres DB fully self-hosted (not managed)</li>
  <li>Granite AI model deployed on dedicated VM for optimized memory usage</li>
  <li>Load balancers route traffic to multiple front-end or service instances</li>
  <li>Internal subnets secure communication between VMs and databases</li>
</ul>

<h3>7️⃣ Tech Stack Highlights</h3>
<ul>
  <li>Back-end: Node.js, Express, PostgreSQL, Kafka</li>
  <li>Front-end: React, modular components, API wrappers</li>
  <li>AI / NLP: Granite AI LLM, integrated with transactional/analytics/index DBs</li>
  <li>Databases: Transactional, Analytics, Message, Index/Search</li>
  <li>Deployment: Multi-VM, volumes, load balancers, containerized microservices, Oracle Cloud</li>
</ul>

<h3>8️⃣ Key Principles</h3>
<ul>
  <li>Separation of concerns: modular service design</li>
  <li>Scalability: high concurrency and load balancing</li>
  <li>Extensibility: add new services without downtime</li>
  <li>Product-driven architecture: all technical decisions support platform functionality</li>
</ul>

</body>
</html>


<h2>🧩 Technical Stack Overview</h2>

Below is a structured overview of the core languages, frameworks, and technologies I’ve used and know across each major system layer — from front-end UI through back-end orchestration, databases, and cloud infrastructure.

<table>
  <thead>
    <tr>
      <th>🏗️ Layer</th>
      <th>🧠 Technologies / Languages</th>
      <th>⚙️ Description & Purpose</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><b>Front-End</b></td>
      <td>React.js, JavaScript (ES6+), TypeScript, HTML5, CSS3, TailwindCSS, Bootstrap</td>
      <td>Client-facing interface for Governa Cloud. Modular component structure with state management via Context API; API consumption via Axios; hosted on an independent VM and volume.</td>
    </tr>
    <tr>
      <td><b>Back-End</b></td>
      <td>Node.js, Express.js, RESTful APIs, WebSockets, Python (data utilities), JWT, Kafka</td>
      <td>Handles routing, logic, authentication, and message streaming. Built with a service–controller–router pattern and microservice modules for Transactional, AI, Messaging, and Analytics services.</td>
    </tr>
    <tr>
      <td><b>Database Layer</b></td>
      <td>PostgreSQL (open-source), Redis, MongoDB (NoSQL), Firestore (NoSQL), Oracle MySQL (managed), SQLAlchemy (Python ORM)</td>
      <td>Multi-DB structure: transactional SQL for data integrity, NoSQL for messaging and analytics caching, Redis for in-memory caching, and Firestore for scalable, schema-less operations.</td>
    </tr>
    <tr>
      <td><b>AI / Data Processing</b></td>
      <td>Granite AI (open-source LLM), LangChain, Python NLP libraries, RAG pipeline, Embeddings, TensorFlow (lightweight)</td>
      <td>Integrated open-source LLMs for contextual understanding and summarization. Uses embedding databases for semantic indexing and conversational retrieval.</td>
    </tr>
    <tr>
      <td><b>Cloud Infrastructure</b></td>
      <td>Oracle Cloud (VMs & Volumes), OCI CLI, Nginx, Docker, Kubernetes (basics), CI/CD pipelines, GCP Firestore, AWS S3</td>
      <td>Self-managed VM + volume hosting setup. Each service containerized and isolated for scalability. Internal subnets for secure inter-service communication and database access.</td>
    </tr>
    <tr>
      <td><b>APIs & Integration</b></td>
      <td>REST, WebSocket, GraphQL (conceptual), Stripe API, OpenAI API, OAuth2.0, Web3.js (ERC-20 / 721)</td>
      <td>Unified data exchange layer for both user traffic and backend communication. Focus on modular endpoints and secure token-based session management.</td>
    </tr>
    <tr>
      <td><b>Development & Collaboration</b></td>
      <td>Git, GitHub, Jira, Confluence, Postman, VSCode, Agile / Scrum</td>
      <td>Full-cycle development collaboration with version control, API testing, and agile sprint planning for product milestones.</td>
    </tr>
  </tbody>
</table>

<h3>📊 Summary by Category</h3>

<table>
  <thead>
    <tr>
      <th>Category</th>
      <th>Tools / Languages</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><b>Programming Languages</b></td>
      <td>JavaScript (ES6+), Python, SQL, TypeScript</td>
    </tr>
    <tr>
      <td><b>Frameworks</b></td>
      <td>React, Node.js, Express.js, LangChain</td>
    </tr>
    <tr>
      <td><b>Databases</b></td>
      <td>PostgreSQL, Redis, MongoDB, Firestore</td>
    </tr>
    <tr>
      <td><b>AI / ML Tools</b></td>
      <td>Granite AI, OpenAI API, TensorFlow (lite), RAG, Embeddings</td>
    </tr>
    <tr>
      <td><b>Cloud & Deployment</b></td>
      <td>Oracle Cloud, Docker, Nginx, CI/CD, GCP, AWS (S3)</td>
    </tr>
    <tr>
      <td><b>Versioning / Testing</b></td>
      <td>Git, GitHub, Postman, Jest (conceptual)</td>
    </tr>
    <tr>
      <td><b>Security & Auth</b></td>
      <td>JWT, OAuth 2.0, HTTPS, API Key Management</td>
    </tr>
  </tbody>
</table>
