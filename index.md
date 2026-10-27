The HTML File (index.html)
HTML
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Dashboard Grid Layout</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>

    <!-- Outer Dashboard Grid Wrapper -->
    <div class="dashboard-container">
        
        <!-- Step 1: Dashboard Header -->
        <header class="dashboard-header">
            <h2>Admin Dashboard</h2>
            <div class="user-profile"><span>Welcome, Alex</span></div>
        </header>

        <!-- Step 2: Sidebar Navigation -->
        <aside class="dashboard-sidebar">
            <nav>
                <ul>
                    <li><a href="#overview" class="active">Overview</a></li>
                    <li><a href="#analytics">Analytics</a></li>
                    <li><a href="#reports">Reports</a></li>
                    <li><a href="#settings">Settings</a></li>
                </ul>
            </nav>
        </aside>

        <!-- Main Content Area -->
        <main class="dashboard-main">
            <h3>Performance Overview</h3>
            
            <!-- Step 3: Statistic Cards (4 cards) -->
            <div class="stats-grid">
                <div class="stat-card">
                    <h4>Total Users</h4>
                    <p class="stat-number">12,480</p>
                    <span class="stat-change positive">+12% this month</span>
                </div>

                <div class="stat-card">
                    <h4>Active Sessions</h4>
                    <p class="stat-number">1,245</p>
                    <span class="stat-change positive">+4% today</span>
                </div>

                <div class="stat-card">
                    <h4>Conversion Rate</h4>
                    <p class="stat-number">3.6%</p>
                    <span class="stat-change negative">-0.4% this week</span>
                </div>

                <div class="stat-card">
                    <h4>Total Revenue</h4>
                    <p class="stat-number">$48,250</p>
                    <span class="stat-change positive">+18% this month</span>
                </div>
            </div>
        </main>

    </div>

</body>
</html>
2. The CSS File (style.css)
CSS
/* Global Reset & Typography */
* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}

body {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    background-color: #f1f5f9;
    color: #1e293b;
    height: 100vh;
}

/* Steps 4 & 5: Outer Dashboard Grid Layout */
.dashboard-container {
    display: grid;
    grid-template-columns: 260px 1fr; /* Sidebar width + flexible main area */
    grid-template-rows: 70px 1fr;     /* Header height + flexible body */
    height: 100vh;
}

/* Step 1: Dashboard Header */
.dashboard-header {
    grid-column: 1 / -1; /* Spans across all columns */
    background-color: #ffffff;
    border-bottom: 1px solid #e2e8f0;
    padding: 0 30px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    box-shadow: 0 1px 3px rgba(0, 0, 0, 0.05);
}

.dashboard-header h2 {
    font-size: 1.25rem;
    color: #0f172a;
}

.user-profile {
    font-weight: 600;
    color: #475569;
}

/* Step 2: Sidebar Styling */
.dashboard-sidebar {
    grid-column: 1;
    background-color: #1e293b;
    color: #ffffff;
    padding: 30px 20px;
}

.dashboard-sidebar ul {
    list-style: none;
    display: flex;
    flex-direction: column;
    gap: 12px;
}

.dashboard-sidebar a {
    color: #94a3b8;
    text-decoration: none;
    font-weight: 600;
    display: block;
    padding: 10px 15px;
    border-radius: 6px;
    transition: background-color 0.2s, color 0.2s;
}

.dashboard-sidebar a:hover, 
.dashboard-sidebar a.active {
    background-color: #334155;
    color: #ffffff;
}

/* Main Content Area */
.dashboard-main {
    grid-column: 2;
    padding: 30px;
    overflow-y: auto;
}

.dashboard-main h3 {
    font-size: 1.5rem;
    margin-bottom: 20px;
    color: #0f172a;
}

/* Step 3 & 6: Statistic Cards Grid & Gaps */
.stats-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
    gap: 20px; /* Step 6: Adds clean spacing between cards */
}

.stat-card {
    background-color: #ffffff;
    border: 1px solid #e2e8f0;
    border-radius: 8px;
    padding: 20px;
    box-shadow: 0 1px 3px rgba(0, 0, 0, 0.05);
}

.stat-card h4 {
    font-size: 0.875rem;
    color: #64748b;
    text-transform: uppercase;
    letter-spacing: 0.5px;
    margin-bottom: 8px;
}

.stat-number {
    font-size: 1.75rem;
    font-weight: 800;
    color: #0f172a;
    margin-bottom: 8px;
}

.stat-change {
    font-size: 0.85rem;
    font-weight: 600;
}

.stat-change.positive {
    color: #10b981;
}

.stat-change.negative {
    color: #ef4444;
}