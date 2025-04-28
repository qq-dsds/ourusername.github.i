<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <title>逐梦兼途</title>
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <style>
        body {
            background: linear-gradient(135deg, #f4f8fb 60%, #eaf6ff 100%);
            color: #222;
            font-family: 'Segoe UI', 'Microsoft YaHei', Arial, sans-serif;
            margin: 0;
            min-height: 100vh;
        }
        header {
            background: linear-gradient(90deg, #3498db 60%, #6dd5fa 100%);
            color: #fff;
            padding: 36px 0 22px 0;
            box-shadow: 0 2px 12px rgba(52,152,219,0.10);
        }
        .header-inner {
            display: flex;
            align-items: center;
            justify-content: center;
            max-width: 1000px;
            margin: 0 auto;
        }
        .logo {
            font-size: 36px;
            font-weight: bold;
            letter-spacing: 2px;
            text-align: left;
            text-shadow: 1px 2px 8px rgba(52,152,219,0.10);
        }
        .tagline {
            font-size: 18px;
            margin-top: 10px;
            opacity: 0.92;
            text-align: left;
            color: #eaf6ff;
            text-shadow: 0 1px 4px rgba(52,152,219,0.10);
        }
        nav {
            background: #fff;
            box-shadow: 0 2px 8px rgba(52,152,219,0.05);
            position: sticky;
            top: 0;
            z-index: 10;
        }
        nav ul {
            display: flex;
            justify-content: center;
            align-items: center;
            list-style: none;
            margin: 0;
            padding: 0;
        }
        nav ul li {
            margin: 0 32px;
        }
        nav ul li a {
            color: #3498db;
            text-decoration: none;
            font-size: 19px;
            font-weight: 500;
            padding: 12px 0;
            border-bottom: 2.5px solid transparent;
            transition: color 0.2s, border-bottom 0.2s;
        }
        nav ul li a:hover, nav ul li a.active {
            color: #217dbb;
            border-bottom: 2.5px solid #f1c40f;
            background: linear-gradient(90deg, #eaf6ff 60%, #f1f8ff 100%);
            border-radius: 2px;
        }
        .container {
            max-width: 1050px;
            margin: 40px auto 0 auto;
            padding: 0 18px;
        }
        .hidden { display: none; }
        .campus-features {
            display: flex;
            flex-wrap: wrap;
            gap: 26px;
            margin-bottom: 40px;
        }
        .feature-card {
            flex: 1 1 240px;
            background: linear-gradient(120deg, #fff 80%, #eaf6ff 100%);
            border-radius: 14px;
            padding: 28px 22px;
            box-shadow: 0 2px 14px rgba(52,152,219,0.10);
            min-width: 220px;
            transition: box-shadow 0.2s, transform 0.2s;
            position: relative;
            border: 1.5px solid #e3eaf2;
        }
        .feature-card:hover {
            box-shadow: 0 8px 32px rgba(52,152,219,0.18);
            transform: translateY(-5px) scale(1.04);
            border-color: #b8e0fa;
        }
        .feature-card h3 {
            color: #3498db;
            margin-bottom: 14px;
            font-size: 21px;
            letter-spacing: 1px;
        }
        .feature-card p {
            font-size: 15px;
            color: #555;
        }
        .job-list {
            background: linear-gradient(120deg, #fff 80%, #eaf6ff 100%);
            border-radius: 14px;
            padding: 32px;
            box-shadow: 0 2px 14px rgba(52,152,219,0.10);
        }
        .job-list h2 {
            color: #3498db;
            margin-bottom: 20px;
            padding-bottom: 10px;
            border-bottom: 1.5px solid #eaeaea;
            font-size: 24px;
        }
        .job-item {
            padding: 20px 0;
            border-bottom: 1px solid #f0f0f0;
            display: flex;
            justify-content: space-between;
            align-items: center;
            transition: background 0.2s;
        }
        .job-item:last-child {
            border-bottom: none;
        }
        .job-item:hover {
            background: #f7faff;
        }
        .job-info h3 {
            color: #2c3e50;
            margin-bottom: 4px;
            font-size: 19px;
        }
        .job-meta {
            display: flex;
            gap: 18px;
            font-size: 15px;
            color: #7f8c8d;
            flex-wrap: wrap;
        }
        .apply-btn, .btn {
            background: linear-gradient(90deg, #3498db 60%, #6dd5fa 100%);
            color: #fff;
            border: none;
            padding: 9px 28px;
            border-radius: 5px;
            cursor: pointer;
            font-size: 16px;
            font-weight: 500;
            transition: background 0.2s, box-shadow 0.2s, transform 0.2s;
            box-shadow: 0 2px 8px rgba(52,152,219,0.10);
        }
        .apply-btn:hover, .btn:hover {
            background: #217dbb;
            transform: translateY(-2px) scale(1.03);
        }
        .campus-forum {
            margin-top: 40px;
            background: linear-gradient(120deg, #fff 80%, #eaf6ff 100%);
            border-radius: 14px;
            padding: 32px;
            box-shadow: 0 2px 14px rgba(52,152,219,0.10);
        }
        .campus-forum h2 {
            color: #3498db;
            margin-bottom: 20px;
            padding-bottom: 10px;
            border-bottom: 1.5px solid #eaeaea;
            font-size: 22px;
        }
        .forum-post {
            margin-bottom: 20px;
            padding-bottom: 14px;
            border-bottom: 1px solid #f0f0f0;
            background: #f9fbfd;
            border-radius: 7px;
            transition: box-shadow 0.2s;
        }
        .forum-post:last-child {
            border-bottom: none;
        }
        .forum-post:hover {
            box-shadow: 0 2px 12px rgba(52,152,219,0.10);
        }
        .post-header {
            display: flex;
            align-items: center;
            margin-bottom: 7px;
        }
        .avatar {
            width: 38px;
            height: 38px;
            background: #3498db;
            color: #fff;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 19px;
            font-weight: bold;
            margin-right: 13px;
            box-shadow: 0 2px 8px rgba(52,152,219,0.10);
        }
        .post-info h4 {
            margin: 0 0 2px 0;
            font-size: 15px;
            color: #222;
        }
        .post-time {
            font-size: 12px;
            color: #7f8c8d;
        }
        .post-content {
            font-size: 14px;
            line-height: 1.7;
            color: #333;
        }
        .profile-info, .resume-upload, .my-applications {
            background: #fff;
            border-radius: 12px;
            padding: 20px 22px 14px 22px;
            box-shadow: 0 2px 10px rgba(52,152,219,0.07);
            margin-bottom: 24px;
        }
        .resume-upload input[type="file"] {
            margin-right: 10px;
        }
        .my-applications table {
            width: 100%;
            border-collapse: collapse;
            font-size: 15px;
        }
        .my-applications th, .my-applications td {
            padding: 9px 4px;
            text-align: left;
        }
        .my-applications th {
            background: #f7f9fb;
        }
        .my-applications tr:not(:last-child) {
            border-bottom: 1px solid #f0f0f0;
        }
        .my-applications span {
            font-weight: bold;
        }
        footer {
            background: #2c3e50;
            color: #fff;
            text-align: center;
            padding: 32px 0 14px 0;
            margin-top: 60px;
            border-radius: 0 0 12px 12px;
            box-shadow: 0 -2px 12px rgba(52,152,219,0.07);
        }
        .footer-links {
            display: flex;
            justify-content: center;
            gap: 36px;
            margin-bottom: 14px;
        }
        .footer-links a {
            color: #fff;
            text-decoration: none;
            font-size: 16px;
            transition: color 0.2s;
        }
        .footer-links a:hover {
            color: #f1c40f;
            text-decoration: underline;
        }
        .copyright {
            font-size: 13px;
            color: #bbb;
        }
        #backToTop {
            position: fixed;
            right: 30px;
            bottom: 40px;
            background: #3498db;
            color: #fff;
            border: none;
            border-radius: 50%;
            width: 46px;
            height: 46px;
            font-size: 23px;
            cursor: pointer;
            box-shadow: 0 2px 12px rgba(52,152,219,0.15);
            display: none;
            z-index: 99;
            transition: background 0.2s;
        }
        #backToTop:hover {
            background: #217dbb;
        }
        /* 响应式优化 */
        @media (max-width: 900px) {
            .container { max-width: 98vw; }
            .campus-features { flex-direction: column; gap: 16px; }
            .feature-card { min-width: unset; }
            .job-list { padding: 14px; }
            .campus-forum { padding: 14px; }
            .header-inner { flex-direction: column; }
            .header-inner img { margin: 18px 0 0 0 !important; }
            .logo, .tagline { text-align: center; }
            #backToTop { right: 12px; bottom: 18px; }
        }
        @media (max-width: 600px) {
            .header-inner img { height: 40px !important; }
            .logo { font-size: 22px; }
            .tagline { font-size: 13px; }
            .feature-card { padding: 14px 8px; }
            .job-list { padding: 6px; }
            .campus-forum { padding: 6px; }
            .footer-links { gap: 16px; }
        }
    </style>
</head>
<body>
    <header>
        <div class="header-inner" style="justify-content: center;">
            <div style="display: flex; flex-direction: column; align-items: flex-start;">
                <div style="display: flex; align-items: center;">
                    <img src="逐梦兼途.jpg" alt="逐梦兼途logo" style="height:60px; margin-right:16px;">
                    <div class="logo" style="text-align:left;">逐梦兼途</div>
                </div>
                <div class="tagline" style="margin-top:8px; text-align:left;">逐梦兼途大学生专属兼职平台 · 学习赚钱两不误</div>
            </div>
        </div>
    </header>
    <nav>
        <ul>
            <li><a href="javascript:void(0)" id="nav-home" class="active" onclick="showPage('home')">首页</a></li>
            <li><a href="javascript:void(0)" id="nav-jobs" onclick="showPage('jobs')">兼职列表</a></li>
            <li><a href="javascript:void(0)" id="nav-forum" onclick="showPage('forum')">校园圈子</a></li>
            <li><a href="javascript:void(0)" id="nav-profile" onclick="showPage('profile')">我的兼职</a></li>
        </ul>
    </nav>
    <div class="container">
        <!-- 首页 -->
        <div id="home" class="page">
            <div class="campus-features">
                <!-- 课程匹配功能 -->
                <div class="feature-card">
                    <h3>课程匹配</h3>
                    <p>
                        <strong>输入你的专业，智能推荐适合你的兼职：</strong><br>
                        <input type="text" id="majorInput" placeholder="如：计算机科学与技术" style="margin:6px 0 8px 0;padding:4px 8px;border-radius:4px;border:1px solid #ccc;width:80%;">
                        <button class="btn" onclick="matchJobs()">一键匹配</button>
                        <div id="matchResult" style="margin-top:10px;color:#3498db;font-size:15px;"></div>
                        <span style="color:#888;font-size:13px;">系统会结合你的专业方向和常见课表，优先推荐不冲突的优质岗位。</span>
                    </p>
                    <div style="margin-top:12px;">
                        <label style="font-weight:bold;">上传课表（可选）：</label>
                        <input type="file" id="scheduleFile" accept=".jpg,.png,.jpeg,.pdf,.xls,.xlsx" style="margin-left:8px;">
                        <span id="scheduleStatus" style="margin-left:10px;color:#27ae60;font-size:14px;"></span>
                    </div>
                    <div style="color:#888;font-size:13px;margin-top:8px;">课程匹配：根据你的专业和课表智能推荐兼职岗位。</div>
                </div>
                <!-- 校园认证功能 -->
                <div class="feature-card">
                    <h3>校园认证</h3>
                    <p>
                        <strong>平台与学校双重审核，兼职更安全：</strong><br>
                        <span style="color:#27ae60;">✔</span> 岗位信息真实可靠<br>
                        <span style="color:#27ae60;">✔</span> 雇主实名认证，杜绝虚假<br>
                        <span style="color:#27ae60;">✔</span> 支持举报、评价与反馈<br>
                        <button class="btn" style="margin-top:8px;" onclick="alert('所有岗位均通过平台和学校双重审核，安全有保障！如遇问题可随时举报。')">了解认证详情</button>
                        <span style="color:#888;font-size:13px;display:block;margin-top:6px;">我们承诺：发现违规岗位，第一时间下架处理。</span>
                    </p>
                    <div style="color:#888;font-size:13px;margin-top:8px;">校园认证：所有兼职岗位均通过平台和学校审核，保障安全。</div>
                </div>
                <!-- 时间灵活功能 -->
                <div class="feature-card">
                    <h3>时间灵活</h3>
                    <p>
                        <strong>多种兼职类型，适配你的时间：</strong><br>
                        <select id="timeType" style="margin:6px 0 8px 0;padding:4px 8px;border-radius:4px;border:1px solid #ccc;">
                            <option>短期兼职</option>
                            <option>长期兼职</option>
                            <option>周末兼职</option>
                            <option>线上兼职</option>
                            <option>寒暑假兼职</option>
                        </select>
                        <button class="btn" onclick="showTimeJobs()">查看推荐</button>
                        <div id="timeJobsResult" style="margin-top:10px;color:#3498db;font-size:15px;"></div>
                        <span style="color:#888;font-size:13px;">根据你的课余时间，灵活选择合适的兼职类型。</span>
                    </p>
                    <div style="color:#888;font-size:13px;margin-top:8px;">时间灵活：支持短期、长期、线上等多种灵活兼职。</div>
                </div>
                <!-- 学长推荐功能 -->
                <div class="feature-card">
                    <h3>学长推荐</h3>
                    <p>
                        <strong>学长学姐真实评价与避坑经验：</strong><br>
                        <button class="btn" onclick="showSeniorReviews()">查看推荐与避坑</button>
                        <div id="seniorReviews" style="margin-top:10px;font-size:15px;color:#666;"></div>
                        <span style="color:#888;font-size:13px;">提前了解岗位优缺点，少走弯路，优先获得高评分兼职。</span>
                    </p>
                    <div style="color:#888;font-size:13px;margin-top:8px;">学长推荐：查看学长学姐的真实兼职评价和经验。</div>
                </div>
            </div>
            <!-- 新增：欢迎语 -->
            <div style="background:#fff;border-radius:10px;padding:22px;margin-bottom:32px;box-shadow:0 2px 8px rgba(52,152,219,0.07);text-align:center;">
                <h2 style="color:#3498db;">欢迎来到逐梦兼途！</h2>
                <p style="font-size:16px;color:#444;">这里为大学生提供安全、丰富、灵活的兼职机会，助力你的成长与梦想。</p>
            </div>
        </div>
        <!-- 兼职列表 -->
        <div id="jobs" class="page hidden">
            <div class="job-list">
                <h2>最新兼职</h2>
                <div style="background:#f7f9fb;padding:10px 16px;border-radius:6px;margin-bottom:18px;color:#666;font-size:15px;">
                    <strong>信用分说明：</strong>
                    信用分反映岗位和雇主的历史评价与平台认证情况，分数越高越可靠。<br>
                    <span style="color:#27ae60;font-weight:bold;">100-90分</span>：绿色，岗位安全可靠，推荐优先申请。<br>
                    <span style="color:#3498db;font-weight:bold;">90-80分</span>：蓝色，岗位较为可靠，建议多关注评价。<br>
                    <span style="color:#f1c40f;font-weight:bold;">80-70分</span>：黄色，岗位需谨慎，建议详细了解后再申请。<br>
                    <span style="color:#e74c3c;font-weight:bold;">70-60分</span>：红色，岗位风险较高，建议慎重申请。
                </div>
                <div class="job-item">
                    <div class="job-info">
                        <h3>校园课程辅导助教</h3>
                        <div class="job-meta">
                            <span>泉州海洋职业学院</span>
                            <span>80-120元/小时</span>
                            <span>每周2-3次</span>
                            <span>信用分：<span style="color:#27ae60;font-weight:bold;">98</span></span>
                        </div>
                    </div>
                    <button class="apply-btn" onclick="alert('请先登录后再申请！')">立即申请</button>
                </div>
                <div class="job-item">
                    <div class="job-info">
                        <h3>图书馆管理员助理</h3>
                        <div class="job-meta">
                            <span>泉州海洋职业学院</span>
                            <span>25元/小时</span>
                            <span>长期兼职</span>
                            <span>信用分：<span style="color:#27ae60;font-weight:bold;">92</span></span>
                        </div>
                    </div>
                    <button class="apply-btn" onclick="alert('请先登录后再申请！')">立即申请</button>
                </div>
                <div class="job-item">
                    <div class="job-info">
                        <h3>线上英语口语陪练</h3>
                        <div class="job-meta">
                            <span>线上工作</span>
                            <span>50-80元/小时</span>
                            <span>时间自由</span>
                            <span>信用分：<span style="color:#3498db;font-weight:bold;">85</span></span>
                        </div>
                    </div>
                    <button class="apply-btn" onclick="alert('请先登录后再申请！')">立即申请</button>
                </div>
                <!-- 新增：编程助教 -->
                <div class="job-item">
                    <div class="job-info">
                        <h3>编程助教</h3>
                        <div class="job-meta">
                            <span>泉州海洋职业学院</span>
                            <span>100元/小时</span>
                            <span>每周1-2次</span>
                            <span>信用分：<span style="color:#27ae60;font-weight:bold;">96</span></span>
                        </div>
                    </div>
                    <button class="apply-btn" onclick="alert('请先登录后再申请！')">立即申请</button>
                </div>
                <!-- 新增：市场调研兼职 -->
                <div class="job-item">
                    <div class="job-info">
                        <h3>市场调研兼职</h3>
                        <div class="job-meta">
                            <span>不限专业</span>
                            <span>30元/份</span>
                            <span>短期/弹性</span>
                            <span>信用分：<span style="color:#f1c40f;font-weight:bold;">75</span></span>
                        </div>
                    </div>
                    <button class="apply-btn" onclick="confirmLowCreditApply(75)">立即申请</button>
                </div>
                <!-- 新增：美术助教 -->
                <div class="job-item">
                    <div class="job-info">
                        <h3>美术助教</h3>
                        <div class="job-meta">
                            <span>艺术学院</span>
                            <span>80元/小时</span>
                            <span>周末兼职</span>
                            <span>信用分：<span style="color:#3498db;font-weight:bold;">82</span></span>
                        </div>
                    </div>
                    <button class="apply-btn" onclick="alert('请先登录后再申请！')">立即申请</button>
                </div>
                <!-- 新增：家教兼职 -->
                <div class="job-item">
                    <div class="job-info">
                        <h3>家教兼职</h3>
                        <div class="job-meta">
                            <span>不限专业</span>
                            <span>60-120元/小时</span>
                            <span>可协商时间</span>
                            <span>信用分：<span style="color:#e74c3c;font-weight:bold;">68</span></span>
                        </div>
                    </div>
                    <button class="apply-btn" onclick="confirmLowCreditApply(68)">立即申请</button>
                </div>
            </div>
        </div>
        <!-- 校园圈子 -->
        <div id="forum" class="page hidden">
            <div class="campus-forum">
                <h2>校园圈子</h2>
                <!-- 先显示已有言论 -->
                <div id="forumPosts">
                    <div class="forum-post">
                        <div class="post-header">
                            <div class="avatar">张</div>
                            <div class="post-info">
                                <h4>张三 (信息工程学院)</h4>
                                <div class="post-time">2小时前 · 泉州海洋职业学院</div>
                            </div>
                        </div>
                        <div class="post-content">
                            刚结束了一个学期的编程助教工作，收获很大！不仅巩固了知识，还认识了很多优秀的学弟学妹。推荐给计算机专业的同学！
                        </div>
                    </div>
                    <div class="forum-post">
                        <div class="post-header">
                            <div class="avatar">李</div>
                            <div class="post-info">
                                <h4>李四 (海工学院)</h4>
                                <div class="post-time">1小时前 · 泉州海洋职业学院</div>
                            </div>
                        </div>
                        <div class="post-content">
                            线上英语陪练真的很锻炼口语能力，而且时间灵活，推荐给想提升英语的同学们！
                        </div>
                    </div>
                    <div class="forum-post">
                        <div class="post-header">
                            <div class="avatar">王</div>
                            <div class="post-info">
                                <h4>王五 (信工学院)</h4>
                                <div class="post-time">30分钟前 · 泉州海洋职业学院</div>
                            </div>
                        </div>
                        <div class="post-content">
                            参加校园活动策划兼职，不仅赚到了零花钱，还提升了自己的组织能力，收获满满！
                        </div>
                    </div>
                    <div class="forum-post">
                        <div class="post-header">
                            <div class="avatar">赵</div>
                            <div class="post-info">
                                <h4>赵六 (艺术体育学院)</h4>
                                <div class="post-time">10分钟前 · 泉州海洋职业学院</div>
                            </div>
                        </div>
                        <div class="post-content">
                            设计类兼职机会其实不少，建议大家多关注校内外的设计比赛和项目，积累作品很重要！
                        </div>
                    </div>
                    <div class="forum-post">
                        <div class="post-header">
                            <div class="avatar">孙</div>
                            <div class="post-info">
                                <h4>孙七 (海工学院)</h4>
                                <div class="post-time">刚刚 · 泉州海洋职业学院</div>
                            </div>
                        </div>
                        <div class="post-content">
                            做市场调研问卷兼职认识了很多朋友，锻炼了沟通能力，强烈推荐！
                        </div>
                    </div>
                </div>
                <!-- 发布表单放在下面 -->
                <form id="forumPostForm" style="margin-top:18px;background:#f7f9fb;padding:14px 16px;border-radius:8px;box-shadow:0 2px 8px rgba(52,152,219,0.06);" onsubmit="addForumPost(event)">
                    <div style="display:flex;gap:10px;align-items:center;">
                        <input type="text" id="forumName" placeholder="你的昵称" style="padding:6px 10px;border-radius:4px;border:1px solid #ccc;width:120px;" required>
                        <input type="text" id="forumDept" placeholder="学院/专业" style="padding:6px 10px;border-radius:4px;border:1px solid #ccc;width:120px;" required>
                        <textarea id="forumContent" placeholder="分享你的兼职/校园生活经验..." style="flex:1;padding:6px 10px;border-radius:4px;border:1px solid #ccc;resize:vertical;" rows="2" required></textarea>
                        <button class="btn" type="submit" style="margin-left:8px;">发布</button>
                    </div>
                </form>
            </div>
        </div>
        <!-- 个人中心/我的兼职 -->
        <div id="profile" class="page hidden">
            <h2>我的兼职</h2>
            <div class="profile-info">
                <h3 style="color:#3498db;font-size:18px;margin:0 0 10px 0;">基本信息</h3>
                <div style="display:flex;flex-wrap:wrap;gap:28px;font-size:15px;color:#444;">
                    <div><strong>姓名：</strong>X同学</div>
                    <div><strong>学校：</strong>泉州海洋学院</div>
                    <div><strong>专业：</strong>汽车制造与实验技术</div>
                    <div><strong>联系方式：</strong>189****8888</div>
                    <div><strong>邮箱：</strong>xiangxx@email.com</div>
                </div>
            </div>
            <div class="resume-upload">
                <h3 style="color:#3498db;font-size:18px;margin:0 0 10px 0;">简历上传</h3>
                <form id="resumeForm" onsubmit="uploadResume(event)">
                    <input type="file" id="resumeFile" accept=".pdf,.doc,.docx" required>
                    <button class="btn" type="submit" style="margin-left:12px;">上传简历</button>
                </form>
                <div id="resumeStatus" style="margin-top:10px;font-size:15px;color:#3498db;"></div>
            </div>
            <div class="my-applications">
                <h3 style="color:#3498db;font-size:18px;margin:0 0 10px 0;">我的兼职申请</h3>
                <table>
                    <thead>
                        <tr>
                            <th>兼职岗位</th>
                            <th>申请时间</th>
                            <th>审核状态</th>
                        </tr>
                    </thead>
                    <tbody id="myApplyList">
                        <tr>
                            <td>校园课程辅导助教</td>
                            <td>2025-04-27</td>
                            <td><span style="color:#fa9b01;">待审核</span></td>
                        </tr>
                        <tr>
                            <td>新媒体运营实习生</td>
                            <td>2025-04-25</td>
                            <td><span style="color:#27ae60;">已通过</span></td>
                        </tr>
                        <tr>
                            <td>市场调研问卷员</td>
                            <td>2025-04-20</td>
                            <td><span style="color:#e74c3c;">已拒绝</span></td>
                        </tr>
                    </tbody>
                </table>
            </div>
            <p style="text-align:center;color:#888;">这里可以展示你的申请记录、简历上传等功能（可根据需求扩展）</p>
        </div>
    </div>
    <!-- 返回顶部按钮 -->
    <button id="backToTop" title="返回顶部" onclick="window.scrollTo({top:0,behavior:'smooth'});">↑</button>
    <footer>
        <div class="footer-links">
            <a href="javascript:void(0)" onclick="showAbout()">关于我们</a>
            <a href="javascript:void(0)" onclick="showContact()">联系我们</a>
            <a href="javascript:void(0)" onclick="showPrivacy()">隐私政策</a>
            <a href="javascript:void(0)" onclick="showHelp()">帮助中心</a>
            <!-- <a href="javascript:void(0)" onclick="showAdminLogin()">管理登录</a> -->
        </div>
        <div class="copyright">
            @ 2025 逐梦兼途 - 大学生兼职服务平台
            <!-- <span style="margin-left:16px;color:#f1c40f;font-size:13px;">管理员可通过“管理登录”入口登录后台</span> -->
        </div>
    </footer>
    <script>
        // 简单的页面切换逻辑
        function showPage(pageId) {
            document.querySelectorAll('.page').forEach(p => p.classList.add('hidden'));
            document.getElementById(pageId).classList.remove('hidden');
            document.querySelectorAll('nav ul li a').forEach(a => a.classList.remove('active'));
            if(document.getElementById('nav-' + pageId)) {
                document.getElementById('nav-' + pageId).classList.add('active');
            }
        }
        // 简历上传功能（仅前端演示，实际需后端支持）
        function uploadResume(event) {
            event.preventDefault();
            const fileInput = document.getElementById('resumeFile');
            const statusDiv = document.getElementById('resumeStatus');
            if (fileInput.files.length > 0) {
                const file = fileInput.files[0];
                statusDiv.textContent = "已上传：" + file.name;
            } else {
                statusDiv.textContent = "请选择文件后再上传。";
            }
        }
        // 校园圈子发帖功能（仅前端演示，刷新即消失）
        function addForumPost(event) {
            event.preventDefault();
            const name = document.getElementById('forumName').value.trim();
            const dept = document.getElementById('forumDept').value.trim();
            const content = document.getElementById('forumContent').value.trim();
            if (!name || !dept || !content) return;
            const avatar = name[0];
            const postHtml = `
                <div class="forum-post">
                    <div class="post-header">
                        <div class="avatar">${avatar}</div>
                        <div class="post-info">
                            <h4>${name} (${dept})</h4>
                            <div class="post-time">刚刚 · 校园圈</div>
                        </div>
                    </div>
                    <div class="post-content">${content.replace(/</g,"&lt;").replace(/>/g,"&gt;")}</div>
                </div>
            `;
            const postsDiv = document.getElementById('forumPosts');
            postsDiv.insertAdjacentHTML('afterbegin', postHtml);
            document.getElementById('forumPostForm').reset();
        }
        // 返回顶部按钮显示逻辑
        window.addEventListener('scroll', function() {
            const btn = document.getElementById('backToTop');
            if (window.scrollY > 200) {
                btn.style.display = 'block';
            } else {
                btn.style.display = 'none';
            }
        });
        // 默认显示首页
        showPage('home');

        // 课程匹配功能演示
        function matchJobs() {
            const major = document.getElementById('majorInput').value.trim();
            let result = '';
            if (!major) {
                result = '请输入你的专业！';
            } else if (major.match(/计算机|软件|信息|人工智能/)) {
                result = '推荐岗位：编程助教、IT技术支持、数据标注、线上答疑、网站维护等。';
            } else if (major.match(/英语|外语|翻译/)) {
                result = '推荐岗位：英语口语陪练、翻译助理、外语家教、留学文书编辑等。';
            } else if (major.match(/管理|市场|经济/)) {
                result = '推荐岗位：活动策划、市场调研、行政助理、运营实习生等。';
            } else if (major.match(/艺术|设计|美术/)) {
                result = '推荐岗位：美术助教、平面设计、摄影摄像、视频剪辑等。';
            } else if (major.match(/教育|师范|心理/)) {
                result = '推荐岗位：家教、助教、心理辅导、课后托管等。';
            } else {
                result = '推荐岗位：问卷调研、校园推广、线上兼职等通用岗位。';
            }
            document.getElementById('matchResult').textContent = result;
        }

        // 时间灵活功能演示
        function showTimeJobs() {
            const type = document.getElementById('timeType').value;
            let result = '';
            switch(type) {
                case '短期兼职':
                    result = '推荐：问卷调研、活动协助、展会临时工、赛事志愿者等。';
                    break;
                case '长期兼职':
                    result = '推荐：图书馆管理员、助教、运营实习生、实验室助理等。';
                    break;
                case '周末兼职':
                    result = '推荐：活动策划、市场推广、家教、摄影摄像等。';
                    break;
                case '线上兼职':
                    result = '推荐：线上答疑、英语陪练、内容编辑、远程设计等。';
                    break;
                case '寒暑假兼职':
                    result = '推荐：实习生、支教、社会调研、夏令营辅导员等。';
                    break;
                default:
                    result = '';
            }
            document.getElementById('timeJobsResult').textContent = result;
        }

        // 学长推荐功能演示
        function showSeniorReviews() {
            document.getElementById('seniorReviews').innerHTML = `
                <div style="margin-bottom:6px;"><strong>编程助教：</strong>“锻炼了表达能力，建议提前备课，和老师多沟通！”</div>
                <div style="margin-bottom:6px;"><strong>市场调研：</strong>“沟通能力提升很快，注意安全，遇到推销要果断拒绝。”</div>
                <div style="margin-bottom:6px;"><strong>线上英语陪练：</strong>“时间灵活，适合英语专业同学，建议准备话题素材。”</div>
                <div style="margin-bottom:6px;"><strong>美术助教：</strong>“积累作品集很有帮助，推荐多参与校内外项目。”</div>
                <div><strong>家教兼职：</strong>“提前和家长沟通好时间和内容，遇到拖欠工资要及时反馈。”</div>
            `;
        }

        // 课表上传演示（仅前端，实际需后端支持）
        document.getElementById('scheduleFile').addEventListener('change', function() {
            const file = this.files[0];
            const status = document.getElementById('scheduleStatus');
            if (file) {
                status.textContent = "已上传：" + file.name;
            } else {
                status.textContent = "";
            }
        });

        function confirmLowCreditApply(score) {
            if (score < 70) {
                if (confirm('该岗位信用分较低（'+score+'分），风险较高，是否仍要申请？')) {
                    alert('已提交申请，请留意岗位风险。');
                }
            } else if (score < 80) {
                if (confirm('该岗位信用分为'+score+'分，建议详细了解后再申请。是否继续？')) {
                    alert('已提交申请，请多关注岗位评价。');
                }
            } else {
                alert('请先登录后再申请！');
            }
        }

        function showAbout() {
            showFooterModal(
                "<h3 style='color:#3498db;margin-top:0;'>关于我们</h3>" +
                "<p>逐梦兼途专注于为大学生提供安全、优质、灵活的兼职与实习机会，助力学生成长与职业发展。我们致力于打造真实可靠的校园兼职生态，欢迎您的加入与监督！</p>"
            );
        }
        function showContact() {
            showFooterModal(
                "<h3 style='color:#3498db;margin-top:0;'>联系我们</h3>" +
                "<p>客服邮箱：<a href='mailto:support@zhumeng.com' style='color:#3498db;'>support@zhumeng.com</a><br>客服电话：400-888-8888<br>工作时间：周一至周五 9:00-18:00</p>"
            );
        }
        function showPrivacy() {
            showFooterModal(
                "<h3 style='color:#3498db;margin-top:0;'>隐私政策</h3>" +
                "<p>我们严格保护用户的个人信息，所有数据仅用于平台服务，不会泄露给第三方。详情请参阅完整隐私政策。</p>"
            );
        }
        function showHelp() {
            showFooterModal(
                "<h3 style='color:#3498db;margin-top:0;'>帮助中心</h3>" +
                "<p>常见问题：<br>1. 如何申请兼职？<br>2. 如何上传简历？<br>3. 如何举报虚假岗位？<br>如有疑问请联系客服。</p>"
            );
        }
        function showFooterModal(html) {
            document.getElementById('footerModalBody').innerHTML = html;
            document.getElementById('footerModal').style.display = 'block';
        }
        function closeFooterModal() {
            document.getElementById('footerModal').style.display = 'none';
        }
    </script>
</body>
</html>
