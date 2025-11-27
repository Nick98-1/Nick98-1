<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>AI/ML Engineer | Full Stack Architect</title>
    
  <style>
        /* Define colors and fonts */
        :root {
            --primary-color: #0077B5; /* LinkedIn Blue */
            --secondary-color: #1E3A8A; /* Dark Blue for emphasis */
            --background-color: #F9FAFB; /* Gray 50 */
            --text-color: #374151; /* Gray 700 */
        }

        /* Basic container and font setup */
        body {
            font-family: 'Inter', sans-serif; /* Assuming Inter or a fallback is available */
            background-color: var(--background-color);
            padding: 1rem; /* p-4 */
        }
        
        /* Main content card structure */
        .bio-container {
            max-width: 800px; /* max-w-3xl */
            margin: 0 auto; /* mx-auto */
            background-color: white;
            box-shadow: 0 20px 25px -5px rgba(0, 0, 0, 0.1), 0 8px 10px -6px rgba(0, 0, 0, 0.1); /* shadow-2xl */
            border-radius: 1rem; /* rounded-2xl */
            padding: 2.5rem; /* p-10 (used larger value for desktop consistency) */
            border: 1px solid #E5E7EB; /* border-gray-100 */
        }
        
        /* Responsive padding adjustments */
        @media (min-width: 640px) { /* sm breakpoint */
            body {
                padding: 2rem; /* sm:p-8 */
            }
            .bio-container {
                padding: 2rem; /* sm:p-8 */
            }
        }

        /* Typography */
        h1 {
            font-size: 1.875rem; /* text-3xl */
            font-weight: 700; /* font-bold */
            color: #1F2937; /* gray-800 */
            margin-bottom: 1rem;
        }

        .intro-paragraph {
            font-size: 1.125rem; /* text-lg */
            color: var(--text-color);
            margin-bottom: 1.5rem;
            display: flex;
            align-items: center;
        }

        .intro-paragraph span {
            font-size: 1.5rem; /* text-2xl */
            margin-right: 0.5rem;
        }

        h2 {
            font-size: 1.25rem; /* text-xl */
            font-weight: 600; /* font-semibold */
            color: var(--secondary-color);
            margin-bottom: 1rem;
            display: flex;
            align-items: center;
        }
        
        .section-content {
            margin-bottom: 2rem;
            border-top: 1px solid #E5E7EB;
            padding-top: 1.5rem;
        }
        
        .list-item {
            display: flex;
            align-items: flex-start;
            margin-bottom: 1rem;
        }

        .list-icon {
            font-size: 1.25rem;
            color: var(--primary-color);
            margin-right: 0.75rem;
            margin-top: 0.25rem;
            flex-shrink: 0;
        }
        
        .list-content strong {
            font-weight: 500;
        }

        .list-inside li {
            margin-left: 1rem;
            list-style-type: disc;
            margin-bottom: 0.75rem;
        }

        .italic-note {
            font-size: 0.875rem; /* text-sm */
            color: #6B7280; /* gray-500 */
            margin-top: 1rem;
            font-style: italic;
        }

        /* Skills Grid */
        .skills-grid {
            display: grid;
            grid-template-columns: 1fr;
            gap: 1rem;
        }

        @media (min-width: 768px) { /* md breakpoint */
            .skills-grid {
                grid-template-columns: repeat(2, 1fr);
            }
            .full-width-skill {
                grid-column: span 2 / span 2;
            }
        }

        .skill-box {
            background-color: #EFF6FF; /* blue-50 */
            padding: 0.75rem; /* p-3 */
            border-radius: 0.5rem; /* rounded-lg */
            box-shadow: 0 1px 2px 0 rgba(0, 0, 0, 0.05); /* shadow-sm */
        }

        .skill-box strong {
            color: var(--primary-color);
            display: block;
            margin-bottom: 0.25rem;
        }

        .skill-box span {
            font-size: 0.875rem; /* text-sm */
        }
    </style>
</head>
<body class="bg-gray-50 p-4 sm:p-8">
    
  <div class="bio-container">
<!-- HEADER / INTRO -->
       <h1 class="text-3xl font-bold text-gray-800 mb-4">
            AI/ML Engineer | Deep Learning & Data Pipelines
        </h1>
        <p class="intro-paragraph">
            <span>👋</span> I am an **AI/ML Engineer and Full Stack Architect** currently driving development for a stealth startup focused on building data-intensive, cloud-native applications.
        </p>

 <!-- ML FOCUS SECTION -->
<div class="section-content">
            <h2 class="text-xl font-semibold text-secondary mb-4">
                Primary Focus: Machine Learning Pipeline 🧠
            </h2>
            <p style="color: #4B5563; margin-bottom: 1rem;">
                My primary focus is on the machine learning pipeline, specializing in Natural Language Processing (NLP) and integrating large language models (LLMs). This includes hands-on experience with:
            </p>
<ul style="list-style: none; padding: 0;">
        <li class="list-item">
                    <span class="list-icon">🔧</span>
                    <div class="list-content">
                        <strong style="color: #374151;">Model Adapters (LoRA):</strong> Implementing LoRA (Low-Rank Adaptation) and other parameter-efficient techniques to fine-tune Transformer models.
                    </div>
                </li>
                <li class="list-item">
                    <span class="list-icon">⚛️</span>
                    <div class="list-content">
                        <strong style="color: #374151;">Vector Embeddings:</strong> Generating and managing high-dimensional Context Vector Embeddings for advanced search, retrieval, and contextual analysis.
                    </div>
                </li>
                <li class="list-item">
                    <span class="list-icon">⚙️</span>
                    <div class="list-content">
                        <strong style="color: #374151;">Data Pipelines:</strong> Designing and deploying scalable, robust data pipelines to handle the entire ML lifecycle—from data ingestion and processing to model deployment and monitoring.
                    </div>
                </li>
            </ul>
        </div>
<!-- FULL STACK & CLOUD FOUNDATION -->
        <div class="section-content">
            <h2 class="text-xl font-semibold text-secondary mb-4">
                <span style="font-size: 1.5rem; margin-right: 0.5rem;">🏗️</span> Foundational Experience (Full Stack & Cloud)
            </h2>
            <p style="color: #4B5563; margin-bottom: 1rem;">
                My work relies on a strong foundation in scalable full-stack development and multi-cloud architecture. Previously, I architected and deployed <strong style="color: var(--primary-color);">Poli Cloud</strong>, a global policy collaboration platform. This experience provided deep expertise in:
            </p>
            
<ul class="list-inside" style="color: var(--text-color); margin-top: 0; padding-left: 0; margin-left: 1.5rem;">
                <li>
                    <strong style="font-weight: 500;">Architecture & Scaling:</strong> Building and deploying containerized web applications across multi-cloud environments (OCI, now expanding to AWS).
                </li>
                <li>
                    <strong style="font-weight: 500;">DevOps & CI/CD:</strong> Practical DevOps practices, utilizing Bash scripting for build automation, environment setup, and CI/CD orchestration.
                </li>
                <li>
                    <strong style="font-weight: 500;">Tech Stack Mastery:</strong> React (frontend), JavaScript, Node.js, Docker, SQL/NoSQL, and extensive cloud resource configuration (VMs, block volumes, object storage, database instances).
                </li>
            </ul>
            <p class="italic-note">
                I apply a cloud-agnostic approach, ensuring infrastructure designed for OCI can be mirrored on AWS or other major providers. I am currently expanding my AWS proficiency, covering SDK integration, IAM policies, Lambda functions, and CI/CD pipelines.
            </p>
        </div>
<!-- KEY SKILLS SUMMARY -->
        <div class="section-content" style="border-top: 1px solid #E5E7EB; padding-top: 1.5rem; margin-bottom: 0;">
            <h2 class="text-xl font-semibold text-secondary mb-4">
                <span style="font-size: 1.5rem; margin-right: 0.5rem;">🛠️</span> Key Skills
            </h2>
            
 <div class="skills-grid">
                <div class="skill-box">
                    <strong>👉 Machine Learning/AI:</strong>
                    <span>NLP • LoRA Adapters • Transformer Models • Vector Embeddings • Python (Libraries) • Data Pipelines</span>
                </div>
                <div class="skill-box">
                    <strong>👉 Full Stack:</strong>
                    <span>JavaScript • React • Node.js • SQL/NoSQL</span>
                </div>
                <div class="skill-box full-width-skill">
                    <strong>👉 Cloud & DevOps:</strong>
                    <span>Docker • Kubernetes (Concepts) • AWS • Oracle Cloud (OCI) • Bash • CI/CD • Cloud Architecture</span>
                </div>
            </div>
        </div>

  </div>

</body>
</html>

