<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Agentic AI System - Study Portal</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Segoe+UI:wght@400;600;700&display=swap');
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Gill Sans', 'Gill Sans MT', 'Segoe UI', Calibri, sans-serif;
            line-height: 1.8;
            color: #1e293b;
            background: linear-gradient(135deg, #f0f4f8 0%, #f8fafc 100%);
            position: relative;
            overflow-x: hidden;
        }
        
        /* Animated background elements */
        body::before {
            content: '';
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: radial-gradient(circle at 20% 50%, rgba(59, 130, 246, 0.05) 0%, transparent 50%),
                        radial-gradient(circle at 80% 80%, rgba(99, 102, 241, 0.05) 0%, transparent 50%);
            pointer-events: none;
            z-index: 1;
        }
        
        .container {
            position: relative;
            z-index: 2;
            max-width: 1200px;
            margin: 0 auto;
            padding: 60px 30px;
        }
        
        /* Header Styling */
        header {
            text-align: center;
            margin-bottom: 80px;
            animation: slideDown 0.8s ease-out;
        }
        
        @keyframes slideDown {
            from {
                opacity: 0;
                transform: translateY(-30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
        
        .header-badge {
            display: inline-block;
            background: linear-gradient(135deg, #3b82f6 0%, #2563eb 100%);
            color: white;
            padding: 8px 20px;
            border-radius: 50px;
            font-weight: 600;
            font-size: 0.85rem;
            margin-bottom: 20px;
            box-shadow: 0 4px 15px rgba(59, 130, 246, 0.3);
        }
        
        h1 {
            font-size: 3.5rem;
            font-weight: 700;
            margin: 20px 0;
            background: linear-gradient(135deg, #3b82f6 0%, #2563eb 50%, #1e40af 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            letter-spacing: -1px;
        }
        
        .subtitle {
            font-size: 1.25rem;
            color: #64748b;
            margin-top: 15px;
            font-weight: 500;
        }
        
        /* Sections */
        section {
            background: white;
            padding: 50px;
            margin-bottom: 40px;
            border-radius: 12px;
            box-shadow: 0 2px 8px rgba(0, 0, 0, 0.08);
            transition: all 0.3s ease;
            animation: fadeInUp 0.6s ease-out;
        }
        
        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(20px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
        
        section:hover {
            box-shadow: 0 8px 24px rgba(0, 0, 0, 0.12);
            transform: translateY(-4px);
        }
        
        h2 {
            font-size: 2rem;
            color: #1e293b;
            margin-bottom: 30px;
            padding-bottom: 15px;
            border-bottom: 3px solid #3b82f6;
            display: inline-block;
            font-weight: 700;
        }
        
        h3 {
            font-size: 1.4rem;
            color: #1e40af;
            margin-top: 25px;
            margin-bottom: 15px;
            font-weight: 600;
        }
        
        .welcome-box {
            background: linear-gradient(135deg, rgba(59, 130, 246, 0.1) 0%, rgba(99, 102, 241, 0.1) 100%);
            border-left: 5px solid #3b82f6;
            padding: 25px;
            margin: 30px 0;
            border-radius: 8px;
        }
        
        .welcome-box p {
            font-size: 1.1rem;
            color: #1e293b;
            margin: 10px 0;
        }
        
        /* Concept Cards */
        .concept-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 25px;
            margin: 30px 0;
        }
        
        .concept-card {
            background: linear-gradient(135deg, #f0f4f8 0%, #f8fafc 100%);
            padding: 25px;
            border-radius: 10px;
            border: 2px solid #e2e8f0;
            transition: all 0.3s ease;
        }
        
        .concept-card:hover {
            border-color: #3b82f6;
            transform: translateY(-5px);
            box-shadow: 0 8px 20px rgba(59, 130, 246, 0.15);
        }
        
        .concept-card h4 {
            color: #2563eb;
            font-size: 1.2rem;
            margin-bottom: 10px;
            font-weight: 600;
        }
        
        .concept-card p {
            color: #475569;
            line-height: 1.6;
        }
        
        /* Tables */
        table {
            width: 100%;
            border-collapse: collapse;
            margin: 25px 0;
            font-size: 0.95rem;
        }
        
        table thead {
            background: linear-gradient(135deg, #3b82f6 0%, #2563eb 100%);
            color: white;
        }
        
        table th {
            padding: 16px;
            text-align: left;
            font-weight: 600;
            letter-spacing: 0.5px;
        }
        
        table td {
            padding: 14px 16px;
            border-bottom: 1px solid #e2e8f0;
        }
        
        table tbody tr {
            transition: all 0.2s ease;
        }
        
        table tbody tr:hover {
            background-color: #f0f4f8;
        }
        
        table tbody tr:nth-child(even) {
            background-color: #f8fafc;
        }
        
        /* Code Block */
        .code-block {
            background: #1e293b;
            color: #e2e8f0;
            padding: 20px;
            border-radius: 8px;
            overflow-x: auto;
            margin: 20px 0;
            font-family: 'Monaco', 'Courier New', monospace;
            font-size: 0.9rem;
            border-left: 4px solid #3b82f6;
        }
        
        .code-block code {
            color: #60a5fa;
        }
        
        /* JSON Response */
        .json-response {
            background: #1e293b;
            color: #e2e8f0;
            padding: 20px;
            border-radius: 8px;
            overflow-x: auto;
            margin: 20px 0;
            font-family: 'Monaco', 'Courier New', monospace;
            font-size: 0.85rem;
            border-left: 4px solid #10b981;
        }
        
        .json-response .key {
            color: #f87171;
        }
        
        .json-response .value {
            color: #86efac;
        }
        
        /* Diagram Container */
        .diagram-container {
            background: linear-gradient(135deg, #f0f4f8 0%, #f8fafc 100%);
            padding: 30px;
            border-radius: 10px;
            margin: 30px 0;
            border: 2px solid #e2e8f0;
            text-align: center;
        }
        
        .diagram-container svg {
            max-width: 100%;
            height: auto;
        }
        
        /* Flowchart styling */
        .flowchart {
            display: flex;
            flex-direction: column;
            gap: 20px;
            margin: 30px 0;
        }
        
        .flow-step {
            display: flex;
            align-items: center;
            gap: 20px;
            animation: slideRight 0.6s ease-out;
        }
        
        @keyframes slideRight {
            from {
                opacity: 0;
                transform: translateX(-20px);
            }
            to {
                opacity: 1;
                transform: translateX(0);
            }
        }
        
        .flow-icon {
            flex-shrink: 0;
            width: 50px;
            height: 50px;
            background: linear-gradient(135deg, #3b82f6 0%, #2563eb 100%);
            color: white;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.5rem;
            font-weight: 700;
        }
        
        .flow-content {
            flex: 1;
            background: #f8fafc;
            padding: 15px 20px;
            border-radius: 8px;
            border-left: 4px solid #3b82f6;
        }
        
        .flow-content strong {
            color: #1e40af;
            font-size: 1.05rem;
        }
        
        /* Tool Cards */
        .tool-cards {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
            margin: 30px 0;
        }
        
        .tool-card {
            background: linear-gradient(135deg, #fef3c7 0%, #fef08a 100%);
            padding: 20px;
            border-radius: 10px;
            border: 2px solid #fcd34d;
            transition: all 0.3s ease;
        }
        
        .tool-card:hover {
            transform: translateY(-8px);
            box-shadow: 0 12px 24px rgba(180, 83, 9, 0.2);
        }
        
        .tool-card h4 {
            color: #b45309;
            font-size: 1.2rem;
            margin-bottom: 10px;
            font-weight: 600;
        }
        
        .tool-card p {
            color: #92400e;
        }
        
        /* Image Container */
        .image-container {
            text-align: center;
            margin: 40px 0;
        }
        
        .image-container img {
            max-width: 100%;
            height: auto;
            border-radius: 12px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
            transition: transform 0.3s ease;
        }
        
        .image-container img:hover {
            transform: scale(1.02);
        }
        
        .image-caption {
            margin-top: 15px;
            color: #64748b;
            font-size: 0.95rem;
            font-style: italic;
        }
        
        /* Footer */
        footer {
            text-align: center;
            padding: 40px;
            color: #64748b;
            border-top: 2px solid #e2e8f0;
            margin-top: 60px;
        }
        
        footer p {
            margin: 10px 0;
            font-size: 0.95rem;
        }
        
        /* Highlight boxes */
        .highlight {
            background: #fef3c7;
            border-left: 4px solid #f59e0b;
            padding: 20px;
            margin: 20px 0;
            border-radius: 6px;
        }
        
        .highlight strong {
            color: #b45309;
        }
        
        /* Success box */
        .success-box {
            background: #d1fae5;
            border-left: 4px solid #10b981;
            padding: 20px;
            margin: 20px 0;
            border-radius: 6px;
        }
        
        .success-box strong {
            color: #047857;
        }
        
        /* Info box */
        .info-box {
            background: #dbeafe;
            border-left: 4px solid #3b82f6;
            padding: 20px;
            margin: 20px 0;
            border-radius: 6px;
        }
        
        .info-box strong {
            color: #1e40af;
        }
        
        /* Lists */
        ul, ol {
            margin: 20px 0 20px 30px;
        }
        
        li {
            margin: 10px 0;
            color: #475569;
        }
        
        /* Links */
        a {
            color: #3b82f6;
            text-decoration: none;
            font-weight: 500;
            transition: color 0.2s ease;
        }
        
        a:hover {
            color: #2563eb;
            text-decoration: underline;
        }
        
        /* Responsive */
        @media (max-width: 768px) {
            h1 {
                font-size: 2.5rem;
            }
            
            h2 {
                font-size: 1.5rem;
            }
            
            .container {
                padding: 30px 15px;
            }
            
            section {
                padding: 25px;
            }
            
            .concept-grid {
                grid-template-columns: 1fr;
            }
            
            table {
                font-size: 0.85rem;
            }
            
            table th, table td {
                padding: 10px 8px;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <div class="header-badge">📚 ADVANCED AGENTIC AI</div>
            <h1>Agentic AI System: Study Portal</h1>
            <p class="subtitle">Moving from simple conversational generation to intelligent actionable execution</p>
        </header>

        <!-- Welcome Section -->
        <section>
            <h2>🎓 Welcome, Chinna Karuppan!</h2>
            <div class="welcome-box">
                <p><strong>Congratulations!</strong> You have successfully built a complete intelligent system incorporating NLP, FastAPI, LLM response generations, Semantic Memory, and RAG.</p>
                <p>Now we move to an <strong>advanced stage</strong>: building an <strong>Agentic AI system</strong> that doesn't just respond, but takes physical actions based on user intent.</p>
            </div>
        </section>

        <!-- Core Concepts Section -->
        <section>
            <h2>📖 Part 1: Core Concepts</h2>
            
            <div class="concept-grid">
                <div class="concept-card">
                    <h4>❓ What is Agentic AI?</h4>
                    <p><strong>Agentic AI</strong> refers to an artificial intelligence model capable of <strong>autonomous decision-making</strong> and <strong>real-world execution</strong>. Unlike standard conversational bots that only suggest answers, Agentic AI acts as an independent agent.</p>
                </div>
                
                <div class="concept-card">
                    <h4>❓ What is Tool/Function Calling?</h4>
                    <p><strong>Tool/Function calling</strong> is the mechanism that enables AI systems to bridge the gap between <strong>human language and code</strong>. When provided with a list of tools, the AI can intelligently output formatted data specifying which tool to invoke.</p>
                </div>
                
                <div class="concept-card">
                    <h4>❓ Action vs. Response</h4>
                    <p>The key difference: <strong>Response Generation</strong> creates conversational strings, while <strong>Action Execution</strong> modifies environments by invoking functions and processing results.</p>
                </div>
            </div>

            <!-- Detailed Explanation -->
            <h3>Deep Dive: How Agentic AI Works</h3>
            <p>Agentic AI systems follow a comprehensive workflow:</p>
            
            <div class="flow-step">
                <div class="flow-icon">1</div>
                <div class="flow-content">
                    <strong>Intent Comprehension</strong> - The system analyzes user input to understand what action is needed
                </div>
            </div>
            
            <div class="flow-step">
                <div class="flow-icon">2</div>
                <div class="flow-content">
                    <strong>Entity Extraction</strong> - Key information is extracted and structured from the user's message
                </div>
            </div>
            
            <div class="flow-step">
                <div class="flow-icon">3</div>
                <div class="flow-content">
                    <strong>Tool Selection</strong> - The system maps intent to the appropriate tool/function
                </div>
            </div>
            
            <div class="flow-step">
                <div class="flow-icon">4</div>
                <div class="flow-content">
                    <strong>Execution</strong> - The selected tool is called with extracted parameters
                </div>
            </div>
            
            <div class="flow-step">
                <div class="flow-icon">5</div>
                <div class="flow-content">
                    <strong>Response Generation</strong> - LLM generates context-aware response based on execution results
                </div>
            </div>

            <!-- Comparison Table -->
            <h3>Response Generation vs. Action Execution</h3>
            <table>
                <thead>
                    <tr>
                        <th>Aspect</th>
                        <th>Response Generation</th>
                        <th>Action Execution (Agentic)</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td><strong>Purpose</strong></td>
                        <td>To converse or inform the user</td>
                        <td>To systematically perform work for the user</td>
                    </tr>
                    <tr>
                        <td><strong>Output Type</strong></td>
                        <td>Standard conversational strings</td>
                        <td>Programmatic decisions and structured parameters</td>
                    </tr>
                    <tr>
                        <td><strong>System State</strong></td>
                        <td>Retains local conversation context only</td>
                        <td>Modifies environments (databases, calendars, files)</td>
                    </tr>
                    <tr>
                        <td><strong>Example</strong></td>
                        <td>"I will schedule that meeting for you." (No action taken)</td>
                        <td>Invokes create_meeting(), confirms execution, returns confirmation</td>
                    </tr>
                    <tr>
                        <td><strong>Complexity</strong></td>
                        <td>Low - text generation only</td>
                        <td>High - requires tool integration & error handling</td>
                    </tr>
                    <tr>
                        <td><strong>User Impact</strong></td>
                        <td>Informational only</td>
                        <td>Direct changes to user's systems</td>
                    </tr>
                </tbody>
            </table>
        </section>

        <!-- Task Architecture Section -->
        <section>
            <h2>🛠 Part 2: System Architecture</h2>
            
            <h3>Decision Engine & Tool Mapping Architecture</h3>
            <p>Our system implements an intelligent decision engine that routes user requests to appropriate tools:</p>
            
            <div class="diagram-container">
                <svg viewBox="0 0 800 600" xmlns="http://www.w3.org/2000/svg">
                    <!-- Title -->
                    <text x="400" y="30" font-size="24" font-weight="bold" text-anchor="middle" fill="#1e293b">
                        Agentic AI Pipeline Architecture
                    </text>
                    
                    <!-- User Input -->
                    <rect x="300" y="60" width="200" height="60" fill="#3b82f6" rx="8"/>
                    <text x="400" y="95" font-size="14" font-weight="bold" text-anchor="middle" fill="white">
                        🤖 User Message
                    </text>
                    
                    <!-- Arrow -->
                    <line x1="400" y1="120" x2="400" y2="150" stroke="#3b82f6" stroke-width="3" marker-end="url(#arrowhead)"/>
                    
                    <!-- Intent & Entity Extraction -->
                    <rect x="250" y="150" width="300" height="70" fill="#10b981" rx="8"/>
                    <text x="400" y="180" font-size="14" font-weight="bold" text-anchor="middle" fill="white">
                        🔍 Intent & Entity Extraction
                    </text>
                    <text x="400" y="205" font-size="12" text-anchor="middle" fill="white">
                        NLP Pipeline Processing
                    </text>
                    
                    <!-- Arrow -->
                    <line x1="400" y1="220" x2="400" y2="250" stroke="#10b981" stroke-width="3" marker-end="url(#arrowhead)"/>
                    
                    <!-- Decision Engine -->
                    <rect x="250" y="250" width="300" height="70" fill="#f59e0b" rx="8"/>
                    <text x="400" y="280" font-size="14" font-weight="bold" text-anchor="middle" fill="white">
                        🧠 Decision Engine
                    </text>
                    <text x="400" y="305" font-size="12" text-anchor="middle" fill="white">
                        Tool Selection & Mapping
                    </text>
                    
                    <!-- Arrows to Tools -->
                    <line x1="250" y1="320" x2="100" y2="360" stroke="#f59e0b" stroke-width="2"/>
                    <line x1="400" y1="320" x2="400" y2="360" stroke="#f59e0b" stroke-width="2"/>
                    <line x1="550" y1="320" x2="700" y2="360" stroke="#f59e0b" stroke-width="2"/>
                    
                    <!-- Tools -->
                    <g>
                        <!-- Tool 1 -->
                        <rect x="20" y="360" width="160" height="60" fill="#ec4899" rx="6"/>
                        <text x="100" y="390" font-size="12" font-weight="bold" text-anchor="middle" fill="white">
                            create_meeting()
                        </text>
                        <text x="100" y="410" font-size="10" text-anchor="middle" fill="white">
                            Schedule Events
                        </text>
                        
                        <!-- Tool 2 -->
                        <rect x="320" y="360" width="160" height="60" fill="#8b5cf6" rx="6"/>
                        <text x="400" y="390" font-size="12" font-weight="bold" text-anchor="middle" fill="white">
                            add_task()
                        </text>
                        <text x="400" y="410" font-size="10" text-anchor="middle" fill="white">
                            Create Tasks
                        </text>
                        
                        <!-- Tool 3 -->
                        <rect x="620" y="360" width="160" height="60" fill="#06b6d4" rx="6"/>
                        <text x="700" y="390" font-size="12" font-weight="bold" text-anchor="middle" fill="white">
                            get_schedule()
                        </text>
                        <text x="700" y="410" font-size="10" text-anchor="middle" fill="white">
                            Fetch Data
                        </text>
                    </g>
                    
                    <!-- Arrows from tools -->
                    <line x1="100" y1="420" x2="150" y2="460" stroke="#ec4899" stroke-width="2"/>
                    <line x1="400" y1="420" x2="400" y2="460" stroke="#8b5cf6" stroke-width="2"/>
                    <line x1="700" y1="420" x2="650" y2="460" stroke="#06b6d4" stroke-width="2"/>
                    
                    <!-- Execution -->
                    <rect x="200" y="460" width="400" height="70" fill="#3b82f6" rx="8"/>
                    <text x="400" y="490" font-size="14" font-weight="bold" text-anchor="middle" fill="white">
                        ⚙️ Tool Execution
                    </text>
                    <text x="400" y="515" font-size="12" text-anchor="middle" fill="white">
                        Process & Return Structured Output
                    </text>
                    
                    <!-- Arrow -->
                    <line x1="400" y1="530" x2="400" y2="560" stroke="#3b82f6" stroke-width="3" marker-end="url(#arrowhead)"/>
                    
                    <!-- Response -->
                    <rect x="250" y="560" width="300" height="60" fill="#10b981" rx="8"/>
                    <text x="400" y="590" font-size="14" font-weight="bold" text-anchor="middle" fill="white">
                        ✨ LLM Response Generation
                    </text>
                    
                    <!-- Arrow marker definition -->
                    <defs>
                        <marker id="arrowhead" markerWidth="10" markerHeight="10" refX="9" refY="3" orient="auto">
                            <polygon points="0 0, 10 3, 0 6" fill="#3b82f6"/>
                        </marker>
                    </defs>
                </svg>
            </div>
        </section>

        <!-- Implementation Steps -->
        <section>
            <h2>🚀 Part 3: Implementation Roadmap</h2>
            
            <h3>Step 1: Define Tools</h3>
            <p>Create simple, reusable tool functions with clear contracts:</p>
            <div class="tool-cards">
                <div class="tool-card">
                    <h4>📅 create_meeting()</h4>
                    <p>Schedules meetings with title, date, and time. Can be simulated without external API.</p>
                </div>
                <div class="tool-card">
                    <h4>✅ add_task()</h4>
                    <p>Creates tasks with description and priority. Returns confirmation with task ID.</p>
                </div>
                <div class="tool-card">
                    <h4>❌ cancel_event()</h4>
                    <p>Removes scheduled events and sends cancellation notifications.</p>
                </div>
                <div class="tool-card">
                    <h4>📋 get_schedule()</h4>
                    <p>Retrieves upcoming events and tasks for a specified timeframe.</p>
                </div>
            </div>

            <h3>Step 2: Tool Design Requirements</h3>
            <div class="info-box">
                <strong>Each tool must:</strong>
                <ul>
                    <li>Accept structured input (entities extracted from user intent)</li>
                    <li>Return structured output with status and metadata</li>
                    <li>Include error handling and validation</li>
                    <li>Maintain audit logs of all executions</li>
                    <li>Support both synchronous and asynchronous operations</li>
                </ul>
            </div>

            <h3>Step 3: Decision Engine Implementation</h3>
            <table>
                <thead>
                    <tr>
                        <th>Intent Detected</th>
                        <th>Extracted Entities</th>
                        <th>Tool Selected</th>
                        <th>Expected Output</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td><strong>schedule</strong></td>
                        <td>title, date, time, attendees</td>
                        <td>create_meeting()</td>
                        <td>Meeting ID, confirmation timestamp</td>
                    </tr>
                    <tr>
                        <td><strong>create_task</strong></td>
                        <td>description, priority, deadline</td>
                        <td>add_task()</td>
                        <td>Task ID, status, created_at</td>
                    </tr>
                    <tr>
                        <td><strong>cancel</strong></td>
                        <td>event_id, reason</td>
                        <td>cancel_event()</td>
                        <td>Cancellation confirmation, timestamp</td>
                    </tr>
                    <tr>
                        <td><strong>query</strong></td>
                        <td>date_range, filter_type</td>
                        <td>get_schedule()</td>
                        <td>Array of events, metadata</td>
                    </tr>
                </tbody>
            </table>

            <h3>Step 4: Tool Execution Pipeline</h3>
            <ol>
                <li><strong>Intent Detection:</strong> Analyze user message using NLP to identify action type</li>
                <li><strong>Entity Extraction:</strong> Parse and structure relevant information from input</li>
                <li><strong>Validation:</strong> Verify all required entities are present and valid</li>
                <li><strong>Tool Selection:</strong> Map detected intent to corresponding function</li>
                <li><strong>Execution:</strong> Call tool with extracted parameters</li>
                <li><strong>Result Processing:</strong> Parse tool output and validate results</li>
                <li><strong>Error Handling:</strong> Manage failures and generate appropriate responses</li>
            </ol>

            <h3>Step 5: LLM Integration</h3>
            <div class="highlight">
                <strong>The LLM's role in Agentic Systems:</strong>
                <p>Rather than generating answers from training data, the LLM uses tool results to craft contextual, natural language responses. This creates a human-like interaction while ensuring accuracy through real tool execution.</p>
            </div>

            <h3>Step 6: Complete Pipeline Flow</h3>
            <div class="diagram-container">
                <svg viewBox="0 0 900 400" xmlns="http://www.w3.org/2000/svg">
                    <!-- Pipeline stages -->
                    <g>
                        <!-- Stage 1 -->
                        <rect x="20" y="150" width="140" height="100" fill="#3b82f6" rx="8"/>
                        <text x="90" y="180" font-size="12" font-weight="bold" text-anchor="middle" fill="white">Intent</text>
                        <text x="90" y="200" font-size="12" font-weight="bold" text-anchor="middle" fill="white">Detection</text>
                        <text x="90" y="230" font-size="10" text-anchor="middle" fill="white">NLP Analysis</text>
                        
                        <!-- Arrow 1 -->
                        <line x1="160" y1="200" x2="190" y2="200" stroke="#3b82f6" stroke-width="3" marker-end="url(#arrowBlue)"/>
                        
                        <!-- Stage 2 -->
                        <rect x="190" y="150" width="140" height="100" fill="#8b5cf6" rx="8"/>
                        <text x="260" y="175" font-size="12" font-weight="bold" text-anchor="middle" fill="white">Entity</text>
                        <text x="260" y="195" font-size="12" font-weight="bold" text-anchor="middle" fill="white">Extraction</text>
                        <text x="260" y="225" font-size="10" text-anchor="middle" fill="white">Parse Information</text>
                        
                        <!-- Arrow 2 -->
                        <line x1="330" y1="200" x2="360" y2="200" stroke="#8b5cf6" stroke-width="3" marker-end="url(#arrowPurple)"/>
                        
                        <!-- Stage 3 -->
                        <rect x="360" y="150" width="140" height="100" fill="#10b981" rx="8"/>
                        <text x="430" y="175" font-size="12" font-weight="bold" text-anchor="middle" fill="white">Tool</text>
                        <text x="430" y="195" font-size="12" font-weight="bold" text-anchor="middle" fill="white">Selection</text>
                        <text x="430" y="225" font-size="10" text-anchor="middle" fill="white">Map to Function</text>
                        
                        <!-- Arrow 3 -->
                        <line x1="500" y1="200" x2="530" y2="200" stroke="#10b981" stroke-width="3" marker-end="url(#arrowGreen)"/>
                        
                        <!-- Stage 4 -->
                        <rect x="530" y="150" width="140" height="100" fill="#f59e0b" rx="8"/>
                        <text x="600" y="175" font-size="12" font-weight="bold" text-anchor="middle" fill="white">Tool</text>
                        <text x="600" y="195" font-size="12" font-weight="bold" text-anchor="middle" fill="white">Execution</text>
                        <text x="600" y="225" font-size="10" text-anchor="middle" fill="white">Call Function</text>
                        
                        <!-- Arrow 4 -->
                        <line x1="670" y1="200" x2="700" y2="200" stroke="#f59e0b" stroke-width="3" marker-end="url(#arrowOrange)"/>
                        
                        <!-- Stage 5 -->
                        <rect x="700" y="150" width="170" height="100" fill="#ec4899" rx="8"/>
                        <text x="785" y="175" font-size="12" font-weight="bold" text-anchor="middle" fill="white">Response</text>
                        <text x="785" y="195" font-size="12" font-weight="bold" text-anchor="middle" fill="white">Generation</text>
                        <text x="785" y="225" font-size="10" text-anchor="middle" fill="white">LLM Output</text>
                    </g>
                    
                    <!-- Arrow markers -->
                    <defs>
                        <marker id="arrowBlue" markerWidth="10" markerHeight="10" refX="9" refY="3" orient="auto">
                            <polygon points="0 0, 10 3, 0 6" fill="#3b82f6"/>
                        </marker>
                        <marker id="arrowPurple" markerWidth="10" markerHeight="10" refX="9" refY="3" orient="auto">
                            <polygon points="0 0, 10 3, 0 6" fill="#8b5cf6"/>
                        </marker>
                        <marker id="arrowGreen" markerWidth="10" markerHeight="10" refX="9" refY="3" orient="auto">
                            <polygon points="0 0, 10 3, 0 6" fill="#10b981"/>
                        </marker>
                        <marker id="arrowOrange" markerWidth="10" markerHeight="10" refX="9" refY="3" orient="auto">
                            <polygon points="0 0, 10 3, 0 6" fill="#f59e0b"/>
                        </marker>
                    </defs>
                </svg>
            </div>
        </section>

        <!-- Proof of Delivery -->
        <section>
            <h2>📸 Part 4: Proof of Delivery & Testing</h2>
            
            <h3>Installation & Setup</h3>
            <p>Ensure all system dependencies are installed and run the application:</p>
            <div class="code-block">
                <code>pip install -r requirements.txt
uvicorn main:app --reload</code>
            </div>

            <h3>Testing the Pipeline (FastAPI Integration)</h3>
            <p>Evaluate our system mapping by running the pipeline endpoint:</p>
            <div class="code-block">
                <code>curl -X POST "http://127.0.0.1:8000/chat" \
     -H "Content-Type: application/json" \
     -d '{"message": "Schedule a project sync tomorrow at 10 AM"}'</code>
            </div>

            <h3>Expected JSON Response</h3>
            <div class="json-response">
<code>{
  <span class="key">"intent"</span>: <span class="value">"create_meeting"</span>,
  <span class="key">"entities"</span>: {
    <span class="key">"title"</span>: <span class="value">"project sync"</span>,
    <span class="key">"date"</span>: <span class="value">"tomorrow"</span>,
    <span class="key">"time"</span>: <span class="value">"10 AM"</span>
  },
  <span class="key">"tool"</span>: <span class="value">"create_meeting"</span>,
  <span class="key">"tool_output"</span>: {
    <span class="key">"status"</span>: <span class="value">"success"</span>,
    <span class="key">"message"</span>: <span class="value">"Meeting scheduled successfully"</span>,
    <span class="key">"meeting_id"</span>: <span class="value">"MTG_20260417_001"</span>,
    <span class="key">"timestamp"</span>: <span class="value">"2026-04-17T10:00:00Z"</span>
  },
  <span class="key">"response"</span>: <span class="value">"Your project sync has been securely scheduled for tomorrow at 10 AM."</span>
}</code>
            </div>

            <div class="success-box">
                <strong>✅ Success Criteria Met:</strong>
                <ul>
                    <li>Intent correctly identified from natural language</li>
                    <li>Entities accurately extracted and structured</li>
                    <li>Appropriate tool automatically selected</li>
                    <li>Tool executed with proper parameters</li>
                    <li>System state updated (meeting created)</li>
                    <li>User receives action-aware response</li>
                </ul>
            </div>
        </section>

        <!-- Key Takeaways -->
        <section>
            <h2>💡 Part 5: Key Takeaways</h2>
            
            <div class="concept-grid">
                <div class="concept-card">
                    <h4>🎯 Intent Matters</h4>
                    <p>Accurate intent detection is the foundation of effective agentic systems. Small improvements in NLP accuracy yield significant improvements in overall system reliability.</p>
                </div>
                
                <div class="concept-card">
                    <h4>🔧 Tools Are Critical</h4>
                    <p>Well-designed tools with clear contracts and comprehensive error handling are essential. Tools should be testable, documented, and maintainable.</p>
                </div>
                
                <div class="concept-card">
                    <h4>📊 Structured Data Wins</h4>
                    <p>JSON responses enable downstream processing. Always return structured data from tools, not just human-readable text.</p>
                </div>
                
                <div class="concept-card">
                    <h4>🔄 Feedback Loops</h4>
                    <p>Log all tool executions and user responses. Use this data to continuously improve intent detection and tool accuracy.</p>
                </div>
                
                <div class="concept-card">
                    <h4>🛡️ Error Handling</h4>
                    <p>Robust error handling makes the difference between a toy system and production-grade software. Anticipate failures and handle them gracefully.</p>
                </div>
                
                <div class="concept-card">
                    <h4>🤖 Human-AI Collaboration</h4>
                    <p>The best agentic systems augment human capabilities. Design for transparency and easy human override when needed.</p>
                </div>
            </div>
        </section>

        <!-- Next Steps -->
        <section>
            <h2>🚀 Next Steps</h2>
            
            <div class="highlight">
                <strong>Ready to build your Agentic AI System?</strong>
                <ol>
                    <li>Start with tool definition - keep initial tools simple but complete</li>
                    <li>Build the intent detection pipeline - use rule-based or ML-based classification</li>
                    <li>Implement entity extraction - use regex, NER, or dependency parsing</li>
                    <li>Create the decision engine - build intent → tool mapping logic</li>
                    <li>Integrate tools and test - validate each tool works correctly</li>
                    <li>Add LLM response generation - craft natural responses from tool outputs</li>
                    <li>Deploy and monitor - track system performance and iterate</li>
                </ol>
            </div>
        </section>

        <footer>
            <p><strong>Agentic AI System: Study Portal</strong></p>
            <p>Built with ❤️ for learning and professional development</p>
            <p>© 2026 AI Learning Initiative | Gill Sans Typography</p>
        </footer>
    </div>
</body>
</html>
