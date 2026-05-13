# ChineseGod-gif.github.io<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>大学生心理特质测试 | 发现你的内在人格</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://cdn.jsdelivr.net/npm/font-awesome@4.7.0/css/font-awesome.min.css" rel="stylesheet">
    <script src="https://cdn.jsdelivr.net/npm/chart.js@4.4.8/dist/chart.umd.min.js"></script>
    
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        primary: '#6366F1',
                        secondary: '#EC4899',
                        accent: '#8B5CF6',
                        dark: '#1E1B4B',
                        light: '#F8FAFC'
                    },
                    fontFamily: {
                        sans: ['Inter', 'system-ui', 'sans-serif'],
                    },
                    animation: {
                        'float': 'float 3s ease-in-out infinite',
                        'pulse-slow': 'pulse 3s cubic-bezier(0.4, 0, 0.6, 1) infinite',
                    }
                },
            }
        }
    </script>
    
    <style type="text/tailwindcss">
        @layer utilities {
            .text-gradient {
                background-clip: text;
                -webkit-background-clip: text;
                -webkit-text-fill-color: transparent;
            }
            .bg-glass {
                backdrop-filter: blur(10px);
                background-color: rgba(255, 255, 255, 0.8);
            }
            .card-shadow {
                box-shadow: 0 10px 25px -5px rgba(99, 102, 241, 0.1), 0 8px 10px -6px rgba(99, 102, 241, 0.1);
            }
        }
        
        @keyframes float {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-10px); }
        }
    </style>
</head>
<body class="bg-gradient-to-br from-light via-purple-50 to-indigo-50 min-h-screen font-sans">
    <!-- 导航栏 -->
    <nav class="fixed top-0 w-full bg-glass z-50 border-b border-purple-100">
        <div class="container mx-auto px-4 py-3 flex justify-between items-center">
            <div class="flex items-center space-x-2">
                <i class="fa fa-star text-primary text-xl"></i>
                <span class="font-bold text-dark text-lg">人格探索实验室</span>
            </div>
            <button id="adminBtn" class="text-gray-500 hover:text-primary transition-colors">
                <i class="fa fa-lock mr-1"></i> 管理后台
            </button>
        </div>
    </nav>

    <!-- 主容器 -->
    <main class="container mx-auto px-4 pt-24 pb-16">
        <!-- 欢迎页面 -->
        <section id="welcomeSection" class="max-w-3xl mx-auto text-center">
            <div class="mb-8 animate-float">
                <div class="w-32 h-32 bg-gradient-to-br from-primary to-secondary rounded-full mx-auto flex items-center justify-center mb-6 card-shadow">
                    <i class="fa fa-compass text-white text-5xl"></i>
                </div>
            </div>
            
            <h1 class="text-[clamp(2rem,5vw,3.5rem)] font-bold mb-4 text-gradient bg-gradient-to-r from-primary to-secondary">
                大学生心理特质测试
            </h1>
            <p class="text-gray-600 text-lg mb-8 max-w-xl mx-auto">
                深入探索你的内心世界，发现独一无二的你。完成测试，获取专属人格分析报告，还有机会找到志同道合的伙伴！
            </p>
            
            <div class="bg-white rounded-2xl p-6 mb-8 card-shadow">
                <div class="flex items-center justify-center space-x-8 text-gray-500 mb-4">
                    <div class="flex flex-col items-center">
                        <i class="fa fa-clock-o text-2xl mb-2 text-primary"></i>
                        <span>约5分钟</span>
                    </div>
                    <div class="flex flex-col items-center">
                        <i class="fa fa-shield text-2xl mb-2 text-primary"></i>
                        <span>匿名测试</span>
                    </div>
                    <div class="flex flex-col items-center">
                        <i class="fa fa-share-alt text-2xl mb-2 text-primary"></i>
                        <span>一键分享</span>
                    </div>
                </div>
                <p class="text-sm text-gray-400">本测试仅供学术研究和个人参考，数据严格保密</p>
            </div>
            
            <button id="startBtn" class="bg-gradient-to-r from-primary to-secondary text-white font-bold py-4 px-12 rounded-full text-lg hover:shadow-lg transform hover:-translate-y-1 transition-all duration-300 card-shadow">
                开始探索 <i class="fa fa-arrow-right ml-2"></i>
            </button>
            
            <p class="mt-6 text-gray-400 text-sm">已有 <span class="font-bold text-primary">12,587</span> 人完成测试</p>
        </section>

        <!-- 基本信息页面 -->
        <section id="basicInfoSection" class="max-w-3xl mx-auto hidden">
            <div class="mb-8">
                <div class="flex justify-between items-center mb-2">
                    <span class="text-sm font-medium text-gray-500">基本信息</span>
                    <span class="text-sm font-medium text-primary">匿名采集，严格保密</span>
                </div>
                <div class="w-full bg-gray-200 rounded-full h-2">
                    <div class="bg-gradient-to-r from-primary to-secondary h-2 rounded-full transition-all duration-500" style="width: 0%"></div>
                </div>
            </div>
            
            <div class="bg-white rounded-2xl p-8 mb-6 card-shadow">
                <h2 class="text-xl font-semibold text-dark mb-6">个人基本信息</h2>
                <p class="text-gray-500 mb-6">请填写以下基本信息，仅用于学术研究分析，我们将严格保护您的隐私</p>
                
                <form id="basicInfoForm" class="space-y-6">
                    <!-- 性别 -->
                    <div>
                        <label class="block text-sm font-medium text-gray-700 mb-3">1. 性别</label>
                        <div class="flex space-x-6">
                            <label class="flex items-center cursor-pointer">
                                <input type="radio" name="gender" value="male" class="w-5 h-5 text-primary focus:ring-primary">
                                <span class="ml-2 text-gray-700">男</span>
                            </label>
                            <label class="flex items-center cursor-pointer">
                                <input type="radio" name="gender" value="female" class="w-5 h-5 text-primary focus:ring-primary">
                                <span class="ml-2 text-gray-700">女</span>
                            </label>
                        </div>
                        <p class="text-red-500 text-sm mt-1 hidden" id="genderError">请选择您的性别</p>
                    </div>
                    
                    <!-- 年龄 -->
                    <div>
                        <label for="age" class="block text-sm font-medium text-gray-700 mb-3">2. 年龄</label>
                        <input type="number" id="age" min="16" max="30" class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-primary focus:border-primary transition-colors" placeholder="请输入您的年龄">
                        <p class="text-red-500 text-sm mt-1 hidden" id="ageError">请输入有效的年龄（16-30岁）</p>
                    </div>
                    
                    <!-- 是否独生子女 -->
                    <div>
                        <label class="block text-sm font-medium text-gray-700 mb-3">3. 是否独生子女</label>
                        <div class="flex space-x-6">
                            <label class="flex items-center cursor-pointer">
                                <input type="radio" name="onlyChild" value="yes" class="w-5 h-5 text-primary focus:ring-primary">
                                <span class="ml-2 text-gray-700">是</span>
                            </label>
                            <label class="flex items-center cursor-pointer">
                                <input type="radio" name="onlyChild" value="no" class="w-5 h-5 text-primary focus:ring-primary">
                                <span class="ml-2 text-gray-700">否</span>
                            </label>
                        </div>
                        <p class="text-red-500 text-sm mt-1 hidden" id="onlyChildError">请选择是否为独生子女</p>
                    </div>
                    
                    <!-- 生源地 -->
                    <div>
                        <label class="block text-sm font-medium text-gray-700 mb-3">4. 生源地</label>
                        <div class="flex space-x-6">
                            <label class="flex items-center cursor-pointer">
                                <input type="radio" name="hometown" value="urban" class="w-5 h-5 text-primary focus:ring-primary">
                                <span class="ml-2 text-gray-700">城镇</span>
                            </label>
                            <label class="flex items-center cursor-pointer">
                                <input type="radio" name="hometown" value="rural" class="w-5 h-5 text-primary focus:ring-primary">
                                <span class="ml-2 text-gray-700">农村</span>
                            </label>
                        </div>
                        <p class="text-red-500 text-sm mt-1 hidden" id="hometownError">请选择您的生源地</p>
                    </div>
                    
                    <!-- 家庭类型 -->
                    <div>
                        <label class="block text-sm font-medium text-gray-700 mb-3">5. 家庭类型</label>
                        <div class="flex space-x-6">
                            <label class="flex items-center cursor-pointer">
                                <input type="radio" name="familyType" value="singleParent" class="w-5 h-5 text-primary focus:ring-primary">
                                <span class="ml-2 text-gray-700">单亲家庭</span>
                            </label>
                            <label class="flex items-center cursor-pointer">
                                <input type="radio" name="familyType" value="twoParent" class="w-5 h-5 text-primary focus:ring-primary">
                                <span class="ml-2 text-gray-700">非单亲家庭</span>
                            </label>
                        </div>
                        <p class="text-red-500 text-sm mt-1 hidden" id="familyTypeError">请选择您的家庭类型</p>
                    </div>
                </form>
            </div>
            
            <div class="flex justify-end">
                <button id="submitBasicInfoBtn" class="bg-primary text-white font-medium py-3 px-8 rounded-full hover:bg-primary/90 transition-colors">
                    继续答题 <i class="fa fa-arrow-right ml-2"></i>
                </button>
            </div>
        </section>

        <!-- 问卷页面 -->
        <section id="questionSection" class="max-w-3xl mx-auto hidden">
            <div class="mb-8">
                <div class="flex justify-between items-center mb-2">
                    <span class="text-sm font-medium text-gray-500">问题 <span id="currentQuestion">1</span>/<span id="totalQuestions">57</span></span>
                    <span id="sectionTitle" class="text-sm font-medium text-primary">第一部分：自我认知</span>
                </div>
                <div class="w-full bg-gray-200 rounded-full h-2">
                    <div id="progressBar" class="bg-gradient-to-r from-primary to-secondary h-2 rounded-full transition-all duration-500" style="width: 0%"></div>
                </div>
            </div>
            
            <div class="bg-white rounded-2xl p-8 mb-6 card-shadow">
                <h2 id="questionText" class="text-xl font-semibold text-dark mb-6"></h2>
                <div id="optionsContainer" class="space-y-3"></div>
            </div>
            
            <div class="flex justify-between">
                <button id="prevBtn" class="bg-gray-100 text-gray-700 font-medium py-3 px-6 rounded-full hover:bg-gray-200 transition-colors disabled:opacity-50 disabled:cursor-not-allowed">
                    <i class="fa fa-arrow-left mr-2"></i> 上一题
                </button>
                <button id="nextBtn" class="bg-primary text-white font-medium py-3 px-6 rounded-full hover:bg-primary/90 transition-colors disabled:opacity-50 disabled:cursor-not-allowed" disabled>
                    下一题 <i class="fa fa-arrow-right ml-2"></i>
                </button>
            </div>
        </section>

        <!-- 结果页面 -->
        <section id="resultSection" class="max-w-4xl mx-auto hidden">
            <div class="text-center mb-10">
                <div class="inline-block mb-4">
                    <div id="resultBadge" class="bg-gradient-to-r from-primary to-secondary text-white font-bold py-3 px-8 rounded-full text-xl">
                        加载中...
                    </div>
                </div>
                <h2 class="text-[clamp(1.8rem,4vw,3rem)] font-bold mb-3 text-dark">你的人格特质分析</h2>
                <p class="text-gray-600 max-w-2xl mx-auto">基于你的回答，我们为你生成了专属的心理特质报告</p>
            </div>
            
            <!-- 雷达图 -->
            <div class="bg-white rounded-2xl p-6 mb-8 card-shadow">
                <h3 class="text-lg font-semibold mb-4 text-dark">五维人格特质图谱</h3>
                <div class="h-80">
                    <canvas id="radarChart"></canvas>
                </div>
            </div>
            
            <!-- 详细分析 -->
            <div class="grid md:grid-cols-2 gap-6 mb-8">
                <div class="bg-white rounded-2xl p-6 card-shadow">
                    <h3 class="text-lg font-semibold mb-4 flex items-center text-dark">
                        <i class="fa fa-lightbulb-o text-yellow-500 mr-2"></i> 核心特质
                    </h3>
                    <div id="coreTraits" class="space-y-3 text-gray-600"></div>
                </div>
                
                <div class="bg-white rounded-2xl p-6 card-shadow">
                    <h3 class="text-lg font-semibold mb-4 flex items-center text-dark">
                        <i class="fa fa-heart text-red-500 mr-2"></i> 成长建议
                    </h3>
                    <div id="growthTips" class="space-y-3 text-gray-600"></div>
                </div>
            </div>
            
            <!-- 推荐内容 -->
            <div class="grid md:grid-cols-2 gap-6 mb-8">
                <div class="bg-white rounded-2xl p-6 card-shadow">
                    <h3 class="text-lg font-semibold mb-4 flex items-center text-dark">
                        <i class="fa fa-youtube-play text-red-600 mr-2"></i> 推荐博主
                    </h3>
                    <div id="recommendedBloggers" class="space-y-3"></div>
                </div>
                
                <div class="bg-white rounded-2xl p-6 card-shadow">
                    <h3 class="text-lg font-semibold mb-4 flex items-center text-dark">
                        <i class="fa fa-users text-blue-500 mr-2"></i> 适合你的圈子
                    </h3>
                    <div id="recommendedGroups" class="space-y-3"></div>
                </div>
            </div>
            
            <!-- 分享卡片 -->
            <div class="bg-gradient-to-r from-primary/10 to-secondary/10 rounded-2xl p-6 mb-8 border border-primary/20">
                <h3 class="text-lg font-semibold mb-4 text-center text-dark">分享你的专属人格标签</h3>
                <div id="shareCard" class="bg-white rounded-xl p-6 mb-6 max-w-sm mx-auto card-shadow">
                    <div class="text-center">
                        <div id="shareBadge" class="inline-block bg-gradient-to-r from-primary to-secondary text-white font-bold py-2 px-6 rounded-full mb-4">
                            加载中...
                        </div>
                        <p class="text-gray-500 mb-4">在大学生心理特质测试中获得了</p>
                        <div class="flex justify-center space-x-2 mb-4">
                            <span class="bg-purple-100 text-purple-800 text-xs font-medium px-2.5 py-0.5 rounded-full" id="tag1">标签1</span>
                            <span class="bg-blue-100 text-blue-800 text-xs font-medium px-2.5 py-0.5 rounded-full" id="tag2">标签2</span>
                            <span class="bg-green-100 text-green-800 text-xs font-medium px-2.5 py-0.5 rounded-full" id="tag3">标签3</span>
                        </div>
                        <p class="text-sm text-gray-400">扫码查看你的完整报告</p>
                        <div class="w-24 h-24 bg-gray-200 rounded mx-auto mt-2 flex items-center justify-center">
                            <i class="fa fa-qrcode text-gray-400 text-2xl"></i>
                        </div>
                    </div>
                </div>
                
                <div class="flex flex-wrap justify-center gap-3">
                    <button id="shareLinkBtn" class="bg-white text-primary border border-primary font-medium py-2 px-5 rounded-full hover:bg-primary/5 transition-colors">
                        <i class="fa fa-link mr-2"></i> 复制链接
                    </button>
                    <button id="shareWechatBtn" class="bg-green-500 text-white font-medium py-2 px-5 rounded-full hover:bg-green-600 transition-colors">
                        <i class="fa fa-wechat mr-2"></i> 微信分享
                    </button>
                    <button id="shareWeiboBtn" class="bg-red-500 text-white font-medium py-2 px-5 rounded-full hover:bg-red-600 transition-colors">
                        <i class="fa fa-weibo mr-2"></i> 微博分享
                    </button>
                </div>
            </div>
            
            <div class="text-center">
                <button id="restartBtn" class="bg-gray-100 text-gray-700 font-medium py-3 px-8 rounded-full hover:bg-gray-200 transition-colors">
                    <i class="fa fa-refresh mr-2"></i> 重新测试
                </button>
            </div>
        </section>

        <!-- 管理员登录页面 -->
        <section id="adminLoginSection" class="max-w-md mx-auto hidden">
            <div class="bg-white rounded-2xl p-8 card-shadow">
                <div class="text-center mb-6">
                    <div class="w-16 h-16 bg-primary/10 rounded-full mx-auto flex items-center justify-center mb-4">
                        <i class="fa fa-lock text-primary text-2xl"></i>
                    </div>
                    <h2 class="text-2xl font-bold text-dark">管理员登录</h2>
                    <p class="text-gray-500 mt-2">请输入管理员密码以查看数据</p>
                </div>
                
                <form id="adminLoginForm">
                    <div class="mb-6">
                        <label for="adminPassword" class="block text-sm font-medium text-gray-700 mb-2">密码</label>
                        <input type="password" id="adminPassword" class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-primary focus:border-primary transition-colors" placeholder="请输入管理员密码" required>
                        <p id="loginError" class="text-red-500 text-sm mt-2 hidden">密码错误，请重试</p>
                    </div>
                    
                    <button type="submit" class="w-full bg-primary text-white font-medium py-3 px-4 rounded-lg hover:bg-primary/90 transition-colors">
                        登录
                    </button>
                </form>
                
                <div class="text-center mt-6">
                    <button id="backToHomeBtn" class="text-gray-500 hover:text-primary transition-colors">
                        <i class="fa fa-arrow-left mr-1"></i> 返回首页
                    </button>
                </div>
            </div>
        </section>

        <!-- 管理员数据页面 -->
        <section id="adminDataSection" class="max-w-7xl mx-auto hidden">
            <div class="flex justify-between items-center mb-8">
                <h2 class="text-2xl font-bold text-dark">数据管理后台</h2>
                <div class="flex space-x-3">
                    <button id="exportCsvBtn" class="bg-green-500 text-white font-medium py-2 px-5 rounded-lg hover:bg-green-600 transition-colors">
                        <i class="fa fa-download mr-2"></i> 导出CSV
                    </button>
                    <button id="logoutBtn" class="bg-gray-100 text-gray-700 font-medium py-2 px-5 rounded-lg hover:bg-gray-200 transition-colors">
                        <i class="fa fa-sign-out mr-2"></i> 退出登录
                    </button>
                </div>
            </div>
            
            <!-- 统计概览 -->
            <div class="grid grid-cols-2 md:grid-cols-4 gap-4 mb-8">
                <div class="bg-white rounded-xl p-5 card-shadow">
                    <div class="text-gray-500 text-sm mb-1">总提交数</div>
                    <div id="totalSubmissions" class="text-3xl font-bold text-dark">0</div>
                </div>
                <div class="bg-white rounded-xl p-5 card-shadow">
                    <div class="text-gray-500 text-sm mb-1">今日新增</div>
                    <div id="todaySubmissions" class="text-3xl font-bold text-primary">0</div>
                </div>
                <div class="bg-white rounded-xl p-5 card-shadow">
                    <div class="text-gray-500 text-sm mb-1">平均完成时间</div>
                    <div id="avgTime" class="text-3xl font-bold text-secondary">0:00</div>
                </div>
                <div class="bg-white rounded-xl p-5 card-shadow">
                    <div class="text-gray-500 text-sm mb-1">分享率</div>
                    <div id="shareRate" class="text-3xl font-bold text-accent">0%</div>
                </div>
            </div>
            
            <!-- 数据表格 -->
            <div class="bg-white rounded-2xl overflow-hidden card-shadow">
                <div class="overflow-x-auto">
                    <table class="min-w-full divide-y divide-gray-200">
                        <thead class="bg-gray-50">
                            <tr>
                                <th scope="col" class="px-4 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">ID</th>
                                <th scope="col" class="px-4 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">提交时间</th>
                                <th scope="col" class="px-4 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">性别</th>
                                <th scope="col" class="px-4 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">年龄</th>
                                <th scope="col" class="px-4 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">独生子女</th>
                                <th scope="col" class="px-4 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">生源地</th>
                                <th scope="col" class="px-4 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">家庭类型</th>
                                <th scope="col" class="px-4 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">人格类型</th>
                                <th scope="col" class="px-4 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">自尊</th>
                                <th scope="col" class="px-4 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">满意度</th>
                                <th scope="col" class="px-4 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">情绪</th>
                                <th scope="col" class="px-4 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">自我概念</th>
                                <th scope="col" class="px-4 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">心理韧性</th>
                                <th scope="col" class="px-4 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">操作</th>
                            </tr>
                        </thead>
                        <tbody id="dataTableBody" class="bg-white divide-y divide-gray-200">
                            <!-- 数据将通过JS动态填充 -->
                        </tbody>
                    </table>
                </div>
            </div>
            
            <div id="noDataMessage" class="text-center py-16 hidden">
                <div class="text-gray-400 text-5xl mb-4">
                    <i class="fa fa-inbox"></i>
                </div>
                <h3 class="text-lg font-medium text-gray-900 mb-2">暂无数据</h3>
                <p class="text-gray-500">还没有用户提交测试结果</p>
            </div>
        </section>
    </main>

    <!-- 页脚 -->
    <footer class="bg-white border-t border-gray-200 py-6">
        <div class="container mx-auto px-4 text-center text-gray-500 text-sm">
            <p>© 2025 人格探索实验室 | 本测试仅供学术研究和个人参考</p>
            <p class="mt-1">所有数据严格保密，仅用于科学研究目的</p>
        </div>
    </footer>

    <!-- 提示框 -->
    <div id="toast" class="fixed bottom-6 right-6 bg-dark text-white px-6 py-3 rounded-lg shadow-lg transform translate-y-20 opacity-0 transition-all duration-300 z-50">
        <span id="toastMessage">操作成功</span>
    </div>

    <script>
        // ==================== 服务器配置 ====================
        // 请将以下URL替换为您的后端API地址
        const API_CONFIG = {
            submitUrl: 'https://your-server.com/api/submit-test', // 提交测试数据接口
            // 如果您还没有后端，可以将下面的enableServer设置为false，使用本地存储
            enableServer: false, 
            timeout: 10000 // 请求超时时间(毫秒)
        };

        // 问卷数据
        const questions = [
            // 第一部分：自尊量表 (10题)
            { section: "第一部分：自我认知", text: "我感到我是一个有价值的人，至少与其他人在同一水平。", options: ["非常不符合", "不符合", "符合", "非常符合"], values: [1, 2, 3, 4], dimension: "selfEsteem" },
            { section: "第一部分：自我认知", text: "我感到我有许多好的品质。", options: ["非常不符合", "不符合", "符合", "非常符合"], values: [1, 2, 3, 4], dimension: "selfEsteem" },
            { section: "第一部分：自我认知", text: "归根结底，我倾向于觉得自己是一个失败者。", options: ["非常不符合", "不符合", "符合", "非常符合"], values: [4, 3, 2, 1], dimension: "selfEsteem" }, // 反向计分
            { section: "第一部分：自我认知", text: "我能像大多数人一样把事情做好。", options: ["非常不符合", "不符合", "符合", "非常符合"], values: [1, 2, 3, 4], dimension: "selfEsteem" },
            { section: "第一部分：自我认知", text: "我感到自己值得自豪的地方不多。", options: ["非常不符合", "不符合", "符合", "非常符合"], values: [4, 3, 2, 1], dimension: "selfEsteem" }, // 反向计分
            { section: "第一部分：自我认知", text: "我对自己持肯定态度。", options: ["非常不符合", "不符合", "符合", "非常符合"], values: [1, 2, 3, 4], dimension: "selfEsteem" },
            { section: "第一部分：自我认知", text: "总的来说，我对自己是满意的。", options: ["非常不符合", "不符合", "符合", "非常符合"], values: [1, 2, 3, 4], dimension: "selfEsteem" },
            { section: "第一部分：自我认知", text: "我希望我能为自己赢得更多尊重。", options: ["非常不符合", "不符合", "符合", "非常符合"], values: [4, 3, 2, 1], dimension: "selfEsteem" }, // 反向计分
            { section: "第一部分：自我认知", text: "我确实时常感到毫无用处。", options: ["非常不符合", "不符合", "符合", "非常符合"], values: [4, 3, 2, 1], dimension: "selfEsteem" }, // 反向计分
            { section: "第一部分：自我认知", text: "我时常认为自己一无是处。", options: ["非常不符合", "不符合", "符合", "非常符合"], values: [4, 3, 2, 1], dimension: "selfEsteem" }, // 反向计分
            
            // 第二部分1：生活满意度 (5题)
            { section: "第二部分：生活态度", text: "我生活中的大多数方面接近我的理想。", options: ["完全不符合", "比较不符合", "有点不符合", "说不清", "有点符合", "比较符合", "完全符合"], values: [1, 2, 3, 4, 5, 6, 7], dimension: "lifeSatisfaction" },
            { section: "第二部分：生活态度", text: "我的生活条件很好。", options: ["完全不符合", "比较不符合", "有点不符合", "说不清", "有点符合", "比较符合", "完全符合"], values: [1, 2, 3, 4, 5, 6, 7], dimension: "lifeSatisfaction" },
            { section: "第二部分：生活态度", text: "我对自己的生活感到满意。", options: ["完全不符合", "比较不符合", "有点不符合", "说不清", "有点符合", "比较符合", "完全符合"], values: [1, 2, 3, 4, 5, 6, 7], dimension: "lifeSatisfaction" },
            { section: "第二部分：生活态度", text: "迄今为止我在生活中得到了想得到的重要东西。", options: ["完全不符合", "比较不符合", "有点不符合", "说不清", "有点符合", "比较符合", "完全符合"], values: [1, 2, 3, 4, 5, 6, 7], dimension: "lifeSatisfaction" },
            { section: "第二部分：生活态度", text: "如果我能回头重走人生之路，我几乎不想改变任何东西。", options: ["完全不符合", "比较不符合", "有点不符合", "说不清", "有点符合", "比较符合", "完全符合"], values: [1, 2, 3, 4, 5, 6, 7], dimension: "lifeSatisfaction" },
            
            // 第二部分2：情绪量表 (20题) - 分为积极情绪和消极情绪，这里合并为一个情绪维度
            { section: "第三部分：情绪状态", text: "感兴趣的", options: ["几乎没有", "比较少", "中等程度", "比较多", "极其多"], values: [1, 2, 3, 4, 5], dimension: "emotionalState", type: "positive" },
            { section: "第三部分：情绪状态", text: "心烦的", options: ["几乎没有", "比较少", "中等程度", "比较多", "极其多"], values: [5, 4, 3, 2, 1], dimension: "emotionalState", type: "negative" }, // 反向计分
            { section: "第三部分：情绪状态", text: "精神活力高的", options: ["几乎没有", "比较少", "中等程度", "比较多", "极其多"], values: [1, 2, 3, 4, 5], dimension: "emotionalState", type: "positive" },
            { section: "第三部分：情绪状态", text: "心神不宁的", options: ["几乎没有", "比较少", "中等程度", "比较多", "极其多"], values: [5, 4, 3, 2, 1], dimension: "emotionalState", type: "negative" }, // 反向计分
            { section: "第三部分：情绪状态", text: "劲头足的", options: ["几乎没有", "比较少", "中等程度", "比较多", "极其多"], values: [1, 2, 3, 4, 5], dimension: "emotionalState", type: "positive" },
            { section: "第三部分：情绪状态", text: "内疚的", options: ["几乎没有", "比较少", "中等程度", "比较多", "极其多"], values: [5, 4, 3, 2, 1], dimension: "emotionalState", type: "negative" }, // 反向计分
            { section: "第三部分：情绪状态", text: "恐惧的", options: ["几乎没有", "比较少", "中等程度", "比较多", "极其多"], values: [5, 4, 3, 2, 1], dimension: "emotionalState", type: "negative" }, // 反向计分
            { section: "第三部分：情绪状态", text: "敌意的", options: ["几乎没有", "比较少", "中等程度", "比较多", "极其多"], values: [5, 4, 3, 2, 1], dimension: "emotionalState", type: "negative" }, // 反向计分
            { section: "第三部分：情绪状态", text: "热情的", options: ["几乎没有", "比较少", "中等程度", "比较多", "极其多"], values: [1, 2, 3, 4, 5], dimension: "emotionalState", type: "positive" },
            { section: "第三部分：情绪状态", text: "自豪的", options: ["几乎没有", "比较少", "中等程度", "比较多", "极其多"], values: [1, 2, 3, 4, 5], dimension: "emotionalState", type: "positive" },
            { section: "第三部分：情绪状态", text: "易怒的", options: ["几乎没有", "比较少", "中等程度", "比较多", "极其多"], values: [5, 4, 3, 2, 1], dimension: "emotionalState", type: "negative" }, // 反向计分
            { section: "第三部分：情绪状态", text: "警觉性高的", options: ["几乎没有", "比较少", "中等程度", "比较多", "极其多"], values: [1, 2, 3, 4, 5], dimension: "emotionalState", type: "positive" },
            { section: "第三部分：情绪状态", text: "害羞的", options: ["几乎没有", "比较少", "中等程度", "比较多", "极其多"], values: [5, 4, 3, 2, 1], dimension: "emotionalState", type: "negative" }, // 反向计分
            { section: "第三部分：情绪状态", text: "备受鼓舞的", options: ["几乎没有", "比较少", "中等程度", "比较多", "极其多"], values: [1, 2, 3, 4, 5], dimension: "emotionalState", type: "positive" },
            { section: "第三部分：情绪状态", text: "紧张的", options: ["几乎没有", "比较少", "中等程度", "比较多", "极其多"], values: [5, 4, 3, 2, 1], dimension: "emotionalState", type: "negative" }, // 反向计分
            { section: "第三部分：情绪状态", text: "意志坚定的", options: ["几乎没有", "比较少", "中等程度", "比较多", "极其多"], values: [1, 2, 3, 4, 5], dimension: "emotionalState", type: "positive" },
            { section: "第三部分：情绪状态", text: "注意力集中的", options: ["几乎没有", "比较少", "中等程度", "比较多", "极其多"], values: [1, 2, 3, 4, 5], dimension: "emotionalState", type: "positive" },
            { section: "第三部分：情绪状态", text: "坐立不安的", options: ["几乎没有", "比较少", "中等程度", "比较多", "极其多"], values: [5, 4, 3, 2, 1], dimension: "emotionalState", type: "negative" }, // 反向计分
            { section: "第三部分：情绪状态", text: "有活力的", options: ["几乎没有", "比较少", "中等程度", "比较多", "极其多"], values: [1, 2, 3, 4, 5], dimension: "emotionalState", type: "positive" },
            { section: "第三部分：情绪状态", text: "害怕的", options: ["几乎没有", "比较少", "中等程度", "比较多", "极其多"], values: [5, 4, 3, 2, 1], dimension: "emotionalState", type: "negative" }, // 反向计分
            
            // 第三部分：自我概念清晰度 (12题)
            { section: "第四部分：自我认知", text: "我对自己的一些看法经常互相矛盾。", options: ["完全不符合", "比较不符合", "有时符合", "比较符合", "完全符合"], values: [5, 4, 3, 2, 1], dimension: "selfConcept" }, // 反向计分
            { section: "第四部分：自我认知", text: "有时我对自己持有一种看法，另一些时候我又会有另一种不同的看法。", options: ["完全不符合", "比较不符合", "有时符合", "比较符合", "完全符合"], values: [5, 4, 3, 2, 1], dimension: "selfConcept" }, // 反向计分
            { section: "第四部分：自我认知", text: "我花很长时间来思索我究竟是什么样的一种人。", options: ["完全不符合", "比较不符合", "有时符合", "比较符合", "完全符合"], values: [5, 4, 3, 2, 1], dimension: "selfConcept" }, // 反向计分
            { section: "第四部分：自我认知", text: "有时候我感觉我不全是我看起来的那个样子。", options: ["完全不符合", "比较不符合", "有时符合", "比较符合", "完全符合"], values: [5, 4, 3, 2, 1], dimension: "selfConcept" }, // 反向计分
            { section: "第四部分：自我认知", text: "回想过去，我不确定我到底是什么样的人。", options: ["完全不符合", "比较不符合", "有时符合", "比较符合", "完全符合"], values: [5, 4, 3, 2, 1], dimension: "selfConcept" }, // 反向计分
            { section: "第四部分：自我认知", text: "我很少体验到我性格不同方面的冲突。", options: ["完全不符合", "比较不符合", "有时符合", "比较符合", "完全符合"], values: [1, 2, 3, 4, 5], dimension: "selfConcept" },
            { section: "第四部分：自我认知", text: "有时候我觉得我对别人的了解好于对自己的了解。", options: ["完全不符合", "比较不符合", "有时符合", "比较符合", "完全符合"], values: [5, 4, 3, 2, 1], dimension: "selfConcept" }, // 反向计分
            { section: "第四部分：自我认知", text: "我对自己的看法似乎比较频繁的变化。", options: ["完全不符合", "比较不符合", "有时符合", "比较符合", "完全符合"], values: [5, 4, 3, 2, 1], dimension: "selfConcept" }, // 反向计分
            { section: "第四部分：自我认知", text: "如果让我来描述自己的性格，或许每天我的描述都不一样。", options: ["完全不符合", "比较不符合", "有时符合", "比较符合", "完全符合"], values: [5, 4, 3, 2, 1], dimension: "selfConcept" }, // 反向计分
            { section: "第四部分：自我认知", text: "即使是想告诉别人我真正是什么样子的，我认为我也做不到。", options: ["完全不符合", "比较不符合", "有时符合", "比较符合", "完全符合"], values: [5, 4, 3, 2, 1], dimension: "selfConcept" }, // 反向计分
            { section: "第四部分：自我认知", text: "一般来说，我能清晰地知道我是谁，我是什么样的人。", options: ["完全不符合", "比较不符合", "有时符合", "比较符合", "完全符合"], values: [1, 2, 3, 4, 5], dimension: "selfConcept" },
            { section: "第四部分：自我认知", text: "因为不知道自己真正想要什么，因此对我来说下定决心做一件事很难。", options: ["完全不符合", "比较不符合", "有时符合", "比较符合", "完全符合"], values: [5, 4, 3, 2, 1], dimension: "selfConcept" }, // 反向计分
            
            // 第四部分：心理韧性 (10题)
            { section: "第五部分：抗压能力", text: "当事情发生变化时，我能够适应。", options: ["从不", "很少", "有时", "经常", "总是"], values: [0, 1, 2, 3, 4], dimension: "resilience" },
            { section: "第五部分：抗压能力", text: "无论人生路途中发生任何事情，我都能处理它。", options: ["从不", "很少", "有时", "经常", "总是"], values: [0, 1, 2, 3, 4], dimension: "resilience" },
            { section: "第五部分：抗压能力", text: "面临难题时，我试着去看到事情积极的一面。", options: ["从不", "很少", "有时", "经常", "总是"], values: [0, 1, 2, 3, 4], dimension: "resilience" },
            { section: "第五部分：抗压能力", text: "经历磨炼会让我更有力量。", options: ["从不", "很少", "有时", "经常", "总是"], values: [0, 1, 2, 3, 4], dimension: "resilience" },
            { section: "第五部分：抗压能力", text: "我很容易从疾病、受伤或困难中恢复过来。", options: ["从不", "很少", "有时", "经常", "总是"], values: [0, 1, 2, 3, 4], dimension: "resilience" },
            { section: "第五部分：抗压能力", text: "我相信即使遇到障碍我也能够实现我的目标。", options: ["从不", "很少", "有时", "经常", "总是"], values: [0, 1, 2, 3, 4], dimension: "resilience" },
            { section: "第五部分：抗压能力", text: "压力之下，我仍然能够集中精神地思考问题。", options: ["从不", "很少", "有时", "经常", "总是"], values: [0, 1, 2, 3, 4], dimension: "resilience" },
            { section: "第五部分：抗压能力", text: "我不会轻易被打败打到。", options: ["从不", "很少", "有时", "经常", "总是"], values: [0, 1, 2, 3, 4], dimension: "resilience" },
            { section: "第五部分：抗压能力", text: "在处理生活中的挑战和困难时，我觉得我是个坚强人。", options: ["从不", "很少", "有时", "经常", "总是"], values: [0, 1, 2, 3, 4], dimension: "resilience" },
            { section: "第五部分：抗压能力", text: "我能够处理一些不愉快或痛苦的感觉，例如悲伤、生气。", options: ["从不", "很少", "有时", "经常", "总是"], values: [0, 1, 2, 3, 4], dimension: "resilience" }
        ];

        // 32种人格称号 (基于5个维度的高低组合)
        const personalityTypes = {
            "high-high-high-high-high": {
                title: "宇宙级阳光战神",
                description: "你是行走的小太阳，自带光芒，无论遇到什么困难都能微笑面对。你的内心强大到离谱，是朋友们的精神支柱。",
                tags: ["人间理想", "正能量爆棚", "六边形战士"],
                color: "from-yellow-400 to-orange-500"
            },
            "high-high-high-high-low": {
                title: "温柔治愈系天使",
                description: "你有着温暖的内心和强大的共情能力，总能在别人需要的时候给予安慰。虽然偶尔会感到疲惫，但你的善良从未改变。",
                tags: ["人间小天使", "治愈系", "温柔本身"],
                color: "from-pink-400 to-rose-500"
            },
            "high-high-high-low-high": {
                title: "清醒的现实主义者",
                description: "你对自己有着清晰的认知，不盲目自信也不过度自卑。你知道自己想要什么，并且会为之努力奋斗。",
                tags: ["人间清醒", "目标明确", "实干家"],
                color: "from-blue-400 to-indigo-500"
            },
            "high-high-high-low-low": {
                title: "佛系生活艺术家",
                description: "你享受当下的生活，不追求功名利禄，更注重内心的平静和满足。你的生活充满了小确幸和仪式感。",
                tags: ["佛系青年", "生活美学家", "知足常乐"],
                color: "from-green-400 to-teal-500"
            },
            "high-high-low-high-high": {
                title: "外冷内热的冰山",
                description: "表面上你看起来冷静自持，甚至有点高冷，但内心其实非常温暖。你不善于表达情感，但会用行动证明你的关心。",
                tags: ["冰山美人", "口嫌体正直", "默默守护"],
                color: "from-cyan-400 to-blue-500"
            },
            "high-high-low-high-low": {
                title: "优雅的贵族",
                description: "你有着良好的教养和优雅的气质，待人接物总是彬彬有礼。你追求高品质的生活，有自己独特的品味。",
                tags: ["贵族气质", "品味不凡", "优雅永不过时"],
                color: "from-purple-400 to-violet-500"
            },
            "high-high-low-low-high": {
                title: "理性的思考者",
                description: "你有着敏锐的洞察力和强大的逻辑思维能力，善于分析问题和解决问题。你总是能保持冷静，做出正确的判断。",
                tags: ["智商担当", "逻辑怪", "问题解决者"],
                color: "from-indigo-400 to-purple-500"
            },
            "high-high-low-low-low": {
                title: "慵懒的猫系青年",
                description: "你像猫一样慵懒又神秘，喜欢独处，享受一个人的时光。你不喜欢被束缚，追求自由随性的生活。",
                tags: ["猫系", "慵懒风", "自由灵魂"],
                color: "from-amber-400 to-yellow-500"
            },
            "high-low-high-high-high": {
                title: "打不死的小强",
                description: "你的生命力极其顽强，无论遇到多大的挫折都能重新站起来。你有着不服输的精神和坚韧不拔的意志。",
                tags: ["坚韧不拔", "永不言弃", "生命力MAX"],
                color: "from-red-400 to-pink-500"
            },
            "high-low-high-high-low": {
                title: "乐观的悲观主义者",
                description: "你总是做最坏的打算，但会尽最大的努力。你能看到事情的阴暗面，但依然选择相信美好。",
                tags: ["清醒的乐观", "未雨绸缪", "现实主义"],
                color: "from-teal-400 to-cyan-500"
            },
            "high-low-high-low-high": {
                title: "孤独的勇士",
                description: "你习惯了一个人战斗，不喜欢麻烦别人。你有着强大的内心和独立的人格，能够独自面对生活中的各种挑战。",
                tags: ["独立自强", "孤勇者", "一人成军"],
                color: "from-slate-400 to-gray-500"
            },
            "high-low-high-low-low": {
                title: "低调的实力派",
                description: "你不喜欢张扬，总是默默努力，用实力说话。你有着过人的才华，但从不炫耀，是真正的宝藏男孩/女孩。",
                tags: ["宝藏选手", "低调奢华", "实力派"],
                color: "from-emerald-400 to-green-500"
            },
            "high-low-low-high-high": {
                title: "高冷的学霸",
                description: "你智商超群，学习能力极强，是别人眼中的学霸。你不喜欢社交，更愿意把时间花在自己感兴趣的事情上。",
                tags: ["学霸本霸", "智商天花板", "高冷学霸"],
                color: "from-blue-500 to-indigo-600"
            },
            "high-low-low-high-low": {
                title: "精致的利己主义者",
                description: "你非常清楚自己想要什么，并且会为了自己的目标而努力。你注重个人感受，追求精致的生活。",
                tags: ["人间清醒", "精致生活", "目标导向"],
                color: "from-rose-400 to-pink-500"
            },
            "high-low-low-low-high": {
                title: "特立独行的思想家",
                description: "你有着独特的思想和见解，不随波逐流，敢于坚持自己的观点。你喜欢思考人生，探索世界的本质。",
                tags: ["思想者", "特立独行", "与众不同"],
                color: "from-violet-400 to-purple-500"
            },
            "high-low-low-low-low": {
                title: "神秘的隐士",
                description: "你非常低调，不喜欢引人注目，总是独来独往。你有着丰富的内心世界，但很少向别人展示。",
                tags: ["神秘主义", "隐士", "内心丰富"],
                color: "from-gray-500 to-slate-600"
            },
            "low-high-high-high-high": {
                title: "努力的追光者",
                description: "虽然你偶尔会对自己不够自信，但你一直在努力成为更好的自己。你积极向上，充满了正能量。",
                tags: ["努力奋斗", "追光者", "未来可期"],
                color: "from-yellow-300 to-amber-400"
            },
            "low-high-high-high-low": {
                title: "敏感的艺术家",
                description: "你有着细腻的情感和丰富的想象力，对美有着独特的感知力。你善于发现生活中的美好，并用自己的方式表达出来。",
                tags: ["艺术细胞", "感性", "想象力丰富"],
                color: "from-pink-300 to-rose-400"
            },
            "low-high-high-low-high": {
                title: "温暖的小太阳",
                description: "你性格开朗，待人热情，总是能给身边的人带来快乐。虽然你偶尔也会有不开心的时候，但很快就能调整过来。",
                tags: ["小太阳", "开心果", "温暖治愈"],
                color: "from-orange-300 to-yellow-400"
            },
            "low-high-high-low-low": {
                title: "知足常乐的普通人",
                description: "你不追求轰轰烈烈的人生，只希望过着平淡幸福的生活。你容易满足，懂得感恩，珍惜身边的人和事。",
                tags: ["平凡幸福", "知足常乐", "感恩生活"],
                color: "from-green-300 to-emerald-400"
            },
            "low-high-low-high-high": {
                title: "慢热的守护者",
                description: "你性格比较内向，不善于主动与人交往，但一旦成为朋友，你会非常忠诚和可靠。你会默默守护你在乎的人。",
                tags: ["慢热型", "忠诚可靠", "守护者"],
                color: "from-blue-300 to-indigo-400"
            },
            "low-high-low-high-low": {
                title: "温柔的倾听者",
                description: "你性格温柔，善解人意，是朋友们最好的倾诉对象。你总是能耐心地倾听别人的烦恼，并给予安慰和建议。",
                tags: ["倾听者", "善解人意", "温柔体贴"],
                color: "from-purple-300 to-violet-400"
            },
            "low-high-low-low-high": {
                title: "安静的观察者",
                description: "你喜欢观察周围的人和事，不喜欢参与其中。你有着敏锐的观察力，能够注意到别人忽略的细节。",
                tags: ["观察者", "细节控", "安静内敛"],
                color: "from-teal-300 to-cyan-400"
            },
            "low-high-low-low-low": {
                title: "佛系躺平大师",
                description: "你对什么都看得很淡，不争不抢，随遇而安。你认为人生苦短，应该及时行乐，不要给自己太大的压力。",
                tags: ["躺平大师", "随遇而安", "佛系人生"],
                color: "from-lime-300 to-green-400"
            },
            "low-low-high-high-high": {
                title: "倔强的小草",
                description: "虽然你现在可能对自己不够自信，对生活也不太满意，但你有着顽强的生命力。只要给你一点阳光，你就能茁壮成长。",
                tags: ["顽强不屈", "小草精神", "潜力股"],
                color: "from-green-500 to-emerald-600"
            },
            "low-low-high-high-low": {
                title: "emo界的天花板",
                description: "你比较多愁善感，容易陷入负面情绪中。但你也有着丰富的内心世界和独特的艺术天赋。",
                tags: ["emo达人", "文艺青年", "多愁善感"],
                color: "from-slate-500 to-gray-600"
            },
            "low-low-high-low-high": {
                title: "打工人的倔强",
                description: "虽然生活对你不太友好，但你依然在努力坚持。你有着不服输的精神，相信只要努力就一定会有回报。",
                tags: ["打工人", "努力搬砖", "永不言弃"],
                color: "from-amber-500 to-orange-600"
            },
            "low-low-high-low-low": {
                title: "人间小苦瓜",
                description: "你最近可能遇到了一些不顺心的事情，心情比较低落。但请相信，一切都会好起来的，风雨过后总会有彩虹。",
                tags: ["有点丧", "需要抱抱", "会好起来的"],
                color: "from-gray-400 to-slate-500"
            },
            "low-low-low-high-high": {
                title: "迷茫的探索者",
                description: "你现在可能对自己和未来都感到有些迷茫，但你一直在努力寻找方向。不要着急，慢慢来，你总会找到属于自己的道路。",
                tags: ["探索者", "寻找自我", "未来可期"],
                color: "from-indigo-500 to-purple-600"
            },
            "low-low-low-high-low": {
                title: "玻璃心的小公主/小王子",
                description: "你内心比较脆弱，容易受到伤害。你渴望被爱和被保护，希望有人能懂你的小心思。",
                tags: ["玻璃心", "需要被爱", "小公主/小王子"],
                color: "from-pink-500 to-rose-600"
            },
            "low-low-low-low-high": {
                title: "孤独的流浪者",
                description: "你感觉自己与这个世界格格不入，总是一个人独来独往。你渴望找到志同道合的朋友，但又不知道如何与人交往。",
                tags: ["孤独患者", "流浪者", "寻找同类"],
                color: "from-gray-600 to-slate-700"
            },
            "low-low-low-low-low": {
                title: "需要被拯救的小可怜",
                description: "你现在可能正处于人生的低谷期，感到非常无助和绝望。请不要放弃，总会有人来爱你，总会有光会照亮你。",
                tags: ["需要关爱", "抱抱你", "一切都会好的"],
                color: "from-blue-600 to-indigo-700"
            }
        };

        // 推荐博主数据
        const bloggers = {
            selfEsteem: {
                high: [
                    { name: "所长林超", desc: "商业思维与个人成长", platform: "B站" },
                    { name: "崔催cui", desc: "自信表达与沟通技巧", platform: "小红书" }
                ],
                low: [
                    { name: "沈奕斐", desc: "社会学教授，教你爱自己", platform: "B站" },
                    { name: "塔拉的自我提升", desc: "从自卑到自信的蜕变", platform: "小红书" }
                ]
            },
            lifeSatisfaction: {
                high: [
                    { name: "李子柒", desc: "东方田园生活美学", platform: "YouTube" },
                    { name: "房琪kiki", desc: "旅行与生活的美好", platform: "抖音" }
                ],
                low: [
                    { name: "半佛仙人", desc: "人间清醒，毒舌但真实", platform: "B站" },
                    { name: "罗翔说刑法", desc: "法治与人生哲学", platform: "B站" }
                ]
            },
            emotionalState: {
                high: [
                    { name: "papi酱", desc: "搞笑幽默，解压神器", platform: "抖音" },
                    { name: "绵羊料理", desc: "美食治愈一切", platform: "B站" }
                ],
                low: [
                    { name: "李松蔚", desc: "心理学视角看问题", platform: "知乎" },
                    { name: "简单心理", desc: "专业心理健康科普", platform: "公众号" }
                ]
            },
            selfConcept: {
                high: [
                    { name: "老番茄", desc: "清晰的自我定位", platform: "B站" },
                    { name: "刘擎教授", desc: "西方思想与自我认知", platform: "B站" }
                ],
                low: [
                    { name: "陈果", desc: "复旦大学哲学教授", platform: "抖音" },
                    { name: "KnowYourself", desc: "自我探索与成长", platform: "公众号" }
                ]
            },
            resilience: {
                high: [
                    { name: "何同学", desc: "科技与创意的力量", platform: "B站" },
                    { name: "张伟丽", desc: "格斗冠军的坚韧", platform: "微博" }
                ],
                low: [
                    { name: "武志红", desc: "心理学与自我成长", platform: "公众号" },
                    { name: "海蓝博士", desc: "情绪管理与抗挫力", platform: "小红书" }
                ]
            }
        };

        // 推荐圈子数据
        const groups = {
            selfEsteem: {
                high: ["自信表达训练营", "个人成长交流群"],
                low: ["自我接纳小组", "自卑与超越读书会"]
            },
            lifeSatisfaction: {
                high: ["生活美学分享群", "小确幸打卡圈"],
                low: ["人间清醒俱乐部", "现实生活讨论组"]
            },
            emotionalState: {
                high: ["快乐星球居民", "搞笑段子手聚集地"],
                low: ["情绪树洞", "心理互助小组"]
            },
            selfConcept: {
                high: ["自我探索深度交流", "哲学思辨小组"],
                low: ["寻找自我之旅", "身份认同讨论圈"]
            },
            resilience: {
                high: ["抗压能力提升营", "挑战不可能小组"],
                low: ["温柔治愈所", "慢慢来不着急"]
            }
        };

        // 全局变量
        let currentQuestionIndex = 0;
        let answers = {};
        let basicInfo = {};
        let startTime;
        let radarChart;

        // DOM元素
        const welcomeSection = document.getElementById('welcomeSection');
        const basicInfoSection = document.getElementById('basicInfoSection');
        const questionSection = document.getElementById('questionSection');
        const resultSection = document.getElementById('resultSection');
        const adminLoginSection = document.getElementById('adminLoginSection');
        const adminDataSection = document.getElementById('adminDataSection');
        
        const startBtn = document.getElementById('startBtn');
        const submitBasicInfoBtn = document.getElementById('submitBasicInfoBtn');
        const prevBtn = document.getElementById('prevBtn');
        const nextBtn = document.getElementById('nextBtn');
        const restartBtn = document.getElementById('restartBtn');
        const adminBtn = document.getElementById('adminBtn');
        const backToHomeBtn = document.getElementById('backToHomeBtn');
        const logoutBtn = document.getElementById('logoutBtn');
        const exportCsvBtn = document.getElementById('exportCsvBtn');
        
        const currentQuestionSpan = document.getElementById('currentQuestion');
        const totalQuestionsSpan = document.getElementById('totalQuestions');
        const sectionTitleSpan = document.getElementById('sectionTitle');
        const progressBar = document.getElementById('progressBar');
        const questionText = document.getElementById('questionText');
        const optionsContainer = document.getElementById('optionsContainer');
        
        const resultBadge = document.getElementById('resultBadge');
        const shareBadge = document.getElementById('shareBadge');
        const tag1 = document.getElementById('tag1');
        const tag2 = document.getElementById('tag2');
        const tag3 = document.getElementById('tag3');
        const coreTraits = document.getElementById('coreTraits');
        const growthTips = document.getElementById('growthTips');
        const recommendedBloggers = document.getElementById('recommendedBloggers');
        const recommendedGroups = document.getElementById('recommendedGroups');
        
        const shareLinkBtn = document.getElementById('shareLinkBtn');
        const shareWechatBtn = document.getElementById('shareWechatBtn');
        const shareWeiboBtn = document.getElementById('shareWeiboBtn');
        
        const adminLoginForm = document.getElementById('adminLoginForm');
        const adminPassword = document.getElementById('adminPassword');
        const loginError = document.getElementById('loginError');
        
        const totalSubmissions = document.getElementById('totalSubmissions');
        const todaySubmissions = document.getElementById('todaySubmissions');
        const avgTime = document.getElementById('avgTime');
        const shareRate = document.getElementById('shareRate');
        const dataTableBody = document.getElementById('dataTableBody');
        const noDataMessage = document.getElementById('noDataMessage');
        
        const toast = document.getElementById('toast');
        const toastMessage = document.getElementById('toastMessage');

        // 初始化
        function init() {
            totalQuestionsSpan.textContent = questions.length;
            
            // 事件监听
            startBtn.addEventListener('click', showBasicInfo);
            submitBasicInfoBtn.addEventListener('click', submitBasicInfo);
            prevBtn.addEventListener('click', goToPrevQuestion);
            nextBtn.addEventListener('click', goToNextQuestion);
            restartBtn.addEventListener('click', restartTest);
            adminBtn.addEventListener('click', showAdminLogin);
            backToHomeBtn.addEventListener('click', showWelcome);
            logoutBtn.addEventListener('click', logout);
            exportCsvBtn.addEventListener('click', exportToCsv);
            adminLoginForm.addEventListener('submit', handleAdminLogin);
            
            shareLinkBtn.addEventListener('click', copyShareLink);
            shareWechatBtn.addEventListener('click', () => showToast("请截图分享到微信"));
            shareWeiboBtn.addEventListener('click', shareToWeibo);
        }

        // 显示基本信息页面
        function showBasicInfo() {
            welcomeSection.classList.add('hidden');
            basicInfoSection.classList.remove('hidden');
        }

        // 提交基本信息
        function submitBasicInfo() {
            // 重置所有错误提示
            document.querySelectorAll('.text-red-500').forEach(el => el.classList.add('hidden'));
            
            // 获取表单数据
            const gender = document.querySelector('input[name="gender"]:checked')?.value;
            const age = document.getElementById('age').value;
            const onlyChild = document.querySelector('input[name="onlyChild"]:checked')?.value;
            const hometown = document.querySelector('input[name="hometown"]:checked')?.value;
            const familyType = document.querySelector('input[name="familyType"]:checked')?.value;
            
            // 验证数据
            let isValid = true;
            
            if (!gender) {
                document.getElementById('genderError').classList.remove('hidden');
                isValid = false;
            }
            
            if (!age || isNaN(age) || age < 16 || age > 30) {
                document.getElementById('ageError').classList.remove('hidden');
                isValid = false;
            }
            
            if (!onlyChild) {
                document.getElementById('onlyChildError').classList.remove('hidden');
                isValid = false;
            }
            
            if (!hometown) {
                document.getElementById('hometownError').classList.remove('hidden');
                isValid = false;
            }
            
            if (!familyType) {
                document.getElementById('familyTypeError').classList.remove('hidden');
                isValid = false;
            }
            
            if (!isValid) return;
            
            // 保存基本信息
            basicInfo = {
                gender,
                age: parseInt(age),
                onlyChild,
                hometown,
                familyType
            };
            
            // 开始测试
            startTest();
        }

        // 开始测试
        function startTest() {
            basicInfoSection.classList.add('hidden');
            questionSection.classList.remove('hidden');
            startTime = Date.now();
            currentQuestionIndex = 0;
            answers = {};
            renderQuestion();
        }

        // 渲染当前问题
        function renderQuestion() {
            const question = questions[currentQuestionIndex];
            currentQuestionSpan.textContent = currentQuestionIndex + 1;
            sectionTitleSpan.textContent = question.section;
            progressBar.style.width = `${((currentQuestionIndex + 1) / questions.length) * 100}%`;
            questionText.textContent = question.text;
            
            optionsContainer.innerHTML = '';
            question.options.forEach((option, index) => {
                const optionElement = document.createElement('div');
                optionElement.className = `flex items-center p-4 rounded-lg border-2 cursor-pointer transition-all ${
                    answers[currentQuestionIndex] === index ? 'border-primary bg-primary/5' : 'border-gray-200 hover:border-primary/50'
                }`;
                optionElement.innerHTML = `
                    <div class="w-6 h-6 rounded-full border-2 ${
                        answers[currentQuestionIndex] === index ? 'border-primary bg-primary' : 'border-gray-300'
                    } flex items-center justify-center mr-3 flex-shrink-0">
                        ${answers[currentQuestionIndex] === index ? '<i class="fa fa-check text-white text-xs"></i>' : ''}
                    </div>
                    <span>${option}</span>
                `;
                optionElement.addEventListener('click', () => selectOption(index));
                optionsContainer.appendChild(optionElement);
            });
            
            // 更新按钮状态
            prevBtn.disabled = currentQuestionIndex === 0;
            nextBtn.disabled = answers[currentQuestionIndex] === undefined;
            
            // 更新下一题按钮文本
            if (currentQuestionIndex === questions.length - 1) {
                nextBtn.innerHTML = '查看结果 <i class="fa fa-arrow-right ml-2"></i>';
            } else {
                nextBtn.innerHTML = '下一题 <i class="fa fa-arrow-right ml-2"></i>';
            }
        }

        // 选择选项
        function selectOption(index) {
            answers[currentQuestionIndex] = index;
            renderQuestion();
        }

        // 上一题
        function goToPrevQuestion() {
            if (currentQuestionIndex > 0) {
                currentQuestionIndex--;
                renderQuestion();
            } else {
                // 回到基本信息页面
                questionSection.classList.add('hidden');
                basicInfoSection.classList.remove('hidden');
            }
        }

        // 下一题
        function goToNextQuestion() {
            if (currentQuestionIndex < questions.length - 1) {
                currentQuestionIndex++;
                renderQuestion();
            } else {
                submitTest();
            }
        }

        // 提交测试
        async function submitTest() {
            const endTime = Date.now();
            const completionTime = Math.round((endTime - startTime) / 1000);
            
            // 计算各维度得分
            const scores = calculateScores();
            
            // 确定人格类型
            const personalityType = getPersonalityType(scores);
            
            // 准备完整数据
            const fullData = {
                ...basicInfo,
                timestamp: new Date().toISOString(),
                completionTime,
                personalityTitle: personalityType.title,
                scores,
                shared: false
            };
            
            // 显示加载状态
            nextBtn.disabled = true;
            nextBtn.innerHTML = '<i class="fa fa-spinner fa-spin mr-2"></i> 提交中...';
            
            try {
                // 发送到服务器
                if (API_CONFIG.enableServer) {
                    await sendDataToServer(fullData);
                }
                
                // 保存到本地存储（作为备份）
                saveDataToLocal(fullData);
                
                // 显示结果
                showResult(scores, personalityType);
            } catch (error) {
                console.error('提交失败:', error);
                showToast("提交失败，请检查网络连接");
                
                // 即使服务器提交失败，也显示结果并保存到本地
                saveDataToLocal(fullData);
                showResult(scores, personalityType);
            } finally {
                nextBtn.disabled = false;
                nextBtn.innerHTML = '查看结果 <i class="fa fa-arrow-right ml-2"></i>';
            }
        }

        // 发送数据到服务器
        async function sendDataToServer(data) {
            const controller = new AbortController();
            const timeoutId = setTimeout(() => controller.abort(), API_CONFIG.timeout);
            
            try {
                const response = await fetch(API_CONFIG.submitUrl, {
                    method: 'POST',
                    headers: {
                        'Content-Type': 'application/json'
                    },
                    body: JSON.stringify(data),
                    signal: controller.signal
                });
                
                if (!response.ok) {
                    throw new Error(`服务器响应错误: ${response.status}`);
                }
                
                return await response.json();
            } finally {
                clearTimeout(timeoutId);
            }
        }

        // 保存数据到本地存储
        function saveDataToLocal(data) {
            const submissions = JSON.parse(localStorage.getItem('testSubmissions') || '[]');
            data.id = submissions.length + 1;
            submissions.push(data);
            localStorage.setItem('testSubmissions', JSON.stringify(submissions));
        }

        // 计算各维度得分
        function calculateScores() {
            const dimensions = {
                selfEsteem: { total: 0, count: 0 },
                lifeSatisfaction: { total: 0, count: 0 },
                emotionalState: { total: 0, count: 0 },
                selfConcept: { total: 0, count: 0 },
                resilience: { total: 0, count: 0 }
            };
            
            questions.forEach((question, index) => {
                const dimension = question.dimension;
                const value = question.values[answers[index]];
                dimensions[dimension].total += value;
                dimensions[dimension].count++;
            });
            
            // 计算平均分并归一化到0-100
            const normalizedScores = {};
            for (const [dimension, data] of Object.entries(dimensions)) {
                const avg = data.total / data.count;
                let maxValue;
                
                switch(dimension) {
                    case 'selfEsteem':
                        maxValue = 4;
                        break;
                    case 'lifeSatisfaction':
                        maxValue = 7;
                        break;
                    case 'emotionalState':
                        maxValue = 5;
                        break;
                    case 'selfConcept':
                        maxValue = 5;
                        break;
                    case 'resilience':
                        maxValue = 4;
                        break;
                    default:
                        maxValue = 5;
                }
                
                normalizedScores[dimension] = Math.round((avg / maxValue) * 100);
            }
            
            return normalizedScores;
        }

        // 获取人格类型
        function getPersonalityType(scores) {
            const threshold = 50;
            const typeKey = [
                scores.selfEsteem > threshold ? 'high' : 'low',
                scores.lifeSatisfaction > threshold ? 'high' : 'low',
                scores.emotionalState > threshold ? 'high' : 'low',
                scores.selfConcept > threshold ? 'high' : 'low',
                scores.resilience > threshold ? 'high' : 'low'
            ].join('-');
            
            return personalityTypes[typeKey] || personalityTypes["low-low-low-low-low"];
        }

        // 显示结果
        function showResult(scores, personalityType) {
            questionSection.classList.add('hidden');
            resultSection.classList.remove('hidden');
            
            // 设置称号
            resultBadge.textContent = personalityType.title;
            resultBadge.className = `bg-gradient-to-r ${personalityType.color} text-white font-bold py-3 px-8 rounded-full text-xl`;
            shareBadge.textContent = personalityType.title;
            shareBadge.className = `inline-block bg-gradient-to-r ${personalityType.color} text-white font-bold py-2 px-6 rounded-full mb-4`;
            
            // 设置标签
            tag1.textContent = personalityType.tags[0];
            tag2.textContent = personalityType.tags[1];
            tag3.textContent = personalityType.tags[2];
            
            // 绘制雷达图
            drawRadarChart(scores);
            
            // 生成核心特质
            generateCoreTraits(scores);
            
            // 生成成长建议
            generateGrowthTips(scores);
            
            // 推荐博主
            generateRecommendedBloggers(scores);
            
            // 推荐圈子
            generateRecommendedGroups(scores);
        }

        // 绘制雷达图
        function drawRadarChart(scores) {
            const ctx = document.getElementById('radarChart').getContext('2d');
            
            if (radarChart) {
                radarChart.destroy();
            }
            
            radarChart = new Chart(ctx, {
                type: 'radar',
                data: {
                    labels: ['自尊水平', '生活满意度', '情绪状态', '自我概念', '心理韧性'],
                    datasets: [{
                        label: '你的特质',
                        data: [
                            scores.selfEsteem,
                            scores.lifeSatisfaction,
                            scores.emotionalState,
                            scores.selfConcept,
                            scores.resilience
                        ],
                        backgroundColor: 'rgba(99, 102, 241, 0.2)',
                        borderColor: 'rgba(99, 102, 241, 1)',
                        borderWidth: 2,
                        pointBackgroundColor: 'rgba(99, 102, 241, 1)',
                        pointBorderColor: '#fff',
                        pointHoverBackgroundColor: '#fff',
                        pointHoverBorderColor: 'rgba(99, 102, 241, 1)'
                    }]
                },
                options: {
                    responsive: true,
                    maintainAspectRatio: false,
                    scales: {
                        r: {
                            angleLines: {
                                display: true
                            },
                            suggestedMin: 0,
                            suggestedMax: 100,
                            ticks: {
                                stepSize: 20
                            }
                        }
                    },
                    plugins: {
                        legend: {
                            display: false
                        }
                    }
                }
            });
        }

        // 生成核心特质
        function generateCoreTraits(scores) {
            coreTraits.innerHTML = '';
            
            const traits = [
                { dimension: 'selfEsteem', high: '你有着健康的自尊水平，对自己有清晰的认知和积极的评价。', low: '你对自己的评价偏低，容易产生自我怀疑和不安全感。' },
                { dimension: 'lifeSatisfaction', high: '你对目前的生活状态比较满意，能够感受到生活中的美好。', low: '你对目前的生活不太满意，渴望改变和成长。' },
                { dimension: 'emotionalState', high: '你的情绪状态比较积极，能够保持乐观开朗的心态。', low: '你的情绪波动较大，容易受到负面情绪的影响。' },
                { dimension: 'selfConcept', high: '你对自己有着清晰的认识，知道自己是谁，想要什么。', low: '你对自我的认知还不够清晰，正在探索自己的身份和价值。' },
                { dimension: 'resilience', high: '你有着较强的心理韧性，能够从挫折和困难中快速恢复。', low: '你的心理韧性有待提升，面对压力时容易感到疲惫和无助。' }
            ];
            
            traits.forEach(trait => {
                const score = scores[trait.dimension];
                const text = score > 50 ? trait.high : trait.low;
                const icon = score > 50 ? 'fa-check-circle text-green-500' : 'fa-circle-o text-gray-400';
                
                const traitElement = document.createElement('div');
                traitElement.className = 'flex items-start';
                traitElement.innerHTML = `
                    <i class="fa ${icon} mt-1 mr-3 flex-shrink-0"></i>
                    <span>${text}</span>
                `;
                coreTraits.appendChild(traitElement);
            });
        }

        // 生成成长建议
        function generateGrowthTips(scores) {
            growthTips.innerHTML = '';
            
            const tips = [
                { dimension: 'selfEsteem', low: '每天写下3件自己做得好的事情，学会肯定自己的价值。' },
                { dimension: 'lifeSatisfaction', low: '尝试培养一个新的爱好，为生活增添乐趣。' },
                { dimension: 'emotionalState', low: '学习情绪管理技巧，如深呼吸、冥想和正念练习。' },
                { dimension: 'selfConcept', low: '多尝试不同的事物，在实践中发现自己的兴趣和特长。' },
                { dimension: 'resilience', low: '建立支持系统，遇到困难时不要独自承受。' }
            ];
            
            let tipCount = 0;
            tips.forEach(tip => {
                if (scores[tip.dimension] <= 50 && tipCount < 4) {
                    const tipElement = document.createElement('div');
                    tipElement.className = 'flex items-start';
                    tipElement.innerHTML = `
                        <i class="fa fa-lightbulb-o text-yellow-500 mt-1 mr-3 flex-shrink-0"></i>
                        <span>${tip.low}</span>
                    `;
                    growthTips.appendChild(tipElement);
                    tipCount++;
                }
            });
            
            // 如果所有维度都很高
            if (tipCount === 0) {
                const tipElement = document.createElement('div');
                tipElement.className = 'flex items-start';
                tipElement.innerHTML = `
                    <i class="fa fa-star text-yellow-500 mt-1 mr-3 flex-shrink-0"></i>
                    <span>你在各个维度都表现出色！继续保持，同时也可以帮助身边的人一起成长。</span>
                `;
                growthTips.appendChild(tipElement);
            }
        }

        // 生成推荐博主
        function generateRecommendedBloggers(scores) {
            recommendedBloggers.innerHTML = '';
            
            // 找到得分最低的两个维度
            const sortedDimensions = Object.entries(scores)
                .sort((a, b) => a[1] - b[1])
                .slice(0, 2)
                .map(([dimension]) => dimension);
            
            // 添加推荐
            const addedBloggers = new Set();
            sortedDimensions.forEach(dimension => {
                const level = scores[dimension] > 50 ? 'high' : 'low';
                bloggers[dimension][level].forEach(blogger => {
                    if (!addedBloggers.has(blogger.name)) {
                        addedBloggers.add(blogger.name);
                        const bloggerElement = document.createElement('div');
                        bloggerElement.className = 'flex items-center justify-between p-3 bg-gray-50 rounded-lg';
                        bloggerElement.innerHTML = `
                            <div>
                                <div class="font-medium text-dark">${blogger.name}</div>
                                <div class="text-sm text-gray-500">${blogger.desc}</div>
                            </div>
                            <span class="text-xs bg-gray-200 text-gray-700 px-2 py-1 rounded">${blogger.platform}</span>
                        `;
                        recommendedBloggers.appendChild(bloggerElement);
                    }
                });
            });
        }

        // 生成推荐圈子
        function generateRecommendedGroups(scores) {
            recommendedGroups.innerHTML = '';
            
            // 找到得分最低的两个维度
            const sortedDimensions = Object.entries(scores)
                .sort((a, b) => a[1] - b[1])
                .slice(0, 2)
                .map(([dimension]) => dimension);
            
            // 添加推荐
            const addedGroups = new Set();
            sortedDimensions.forEach(dimension => {
                const level = scores[dimension] > 50 ? 'high' : 'low';
                groups[dimension][level].forEach(group => {
                    if (!addedGroups.has(group)) {
                        addedGroups.add(group);
                        const groupElement = document.createElement('div');
                        groupElement.className = 'flex items-center p-3 bg-gray-50 rounded-lg';
                        groupElement.innerHTML = `
                            <i class="fa fa-users text-blue-500 mr-3"></i>
                            <span>${group}</span>
                        `;
                        recommendedGroups.appendChild(groupElement);
                    }
                });
            });
        }

        // 复制分享链接
        function copyShareLink() {
            const link = window.location.href;
            navigator.clipboard.writeText(link).then(() => {
                showToast("链接已复制到剪贴板");
                
                // 更新分享状态
                updateShareStatus();
            }).catch(() => {
                showToast("复制失败，请手动复制链接");
            });
        }

        // 分享到微博
        function shareToWeibo() {
            const text = `我在大学生心理特质测试中获得了【${resultBadge.textContent}】的称号！快来测测你是什么类型吧~`;
            const url = window.location.href;
            const weiboUrl = `https://service.weibo.com/share/share.php?url=${encodeURIComponent(url)}&title=${encodeURIComponent(text)}`;
            window.open(weiboUrl, '_blank');
            
            // 更新分享状态
            updateShareStatus();
        }

        // 更新分享状态
        function updateShareStatus() {
            const submissions = JSON.parse(localStorage.getItem('testSubmissions') || '[]');
            if (submissions.length > 0) {
                submissions[submissions.length - 1].shared = true;
                localStorage.setItem('testSubmissions', JSON.stringify(submissions));
            }
        }

        // 重新测试
        function restartTest() {
            resultSection.classList.add('hidden');
            welcomeSection.classList.remove('hidden');
            
            // 重置表单
            document.getElementById('basicInfoForm').reset();
            basicInfo = {};
            answers = {};
        }

        // 显示管理员登录
        function showAdminLogin() {
            // 隐藏所有其他页面
            welcomeSection.classList.add('hidden');
            basicInfoSection.classList.add('hidden');
            questionSection.classList.add('hidden');
            resultSection.classList.add('hidden');
            adminDataSection.classList.add('hidden');
            
            adminLoginSection.classList.remove('hidden');
        }

        // 显示欢迎页面
        function showWelcome() {
            adminLoginSection.classList.add('hidden');
            adminDataSection.classList.add('hidden');
            welcomeSection.classList.remove('hidden');
        }

        // 处理管理员登录
        function handleAdminLogin(e) {
            e.preventDefault();
            const password = adminPassword.value;
            
            // 简单的密码验证（建议在生产环境中使用更安全的后端验证）
            if (password === 'admin123') {
                loginError.classList.add('hidden');
                showAdminData();
            } else {
                loginError.classList.remove('hidden');
            }
        }

        // 显示管理员数据
        function showAdminData() {
            adminLoginSection.classList.add('hidden');
            adminDataSection.classList.remove('hidden');
            
            loadAdminData();
        }

        // 加载管理员数据
        function loadAdminData() {
            const submissions = JSON.parse(localStorage.getItem('testSubmissions') || '[]');
            
            if (submissions.length === 0) {
                noDataMessage.classList.remove('hidden');
                dataTableBody.parentElement.classList.add('hidden');
                return;
            }
            
            noDataMessage.classList.add('hidden');
            dataTableBody.parentElement.classList.remove('hidden');
            
            // 更新统计数据
            totalSubmissions.textContent = submissions.length;
            
            const today = new Date().toDateString();
            const todayCount = submissions.filter(s => new Date(s.timestamp).toDateString() === today).length;
            todaySubmissions.textContent = todayCount;
            
            const avgTimeSeconds = Math.round(submissions.reduce((sum, s) => sum + s.completionTime, 0) / submissions.length);
            const minutes = Math.floor(avgTimeSeconds / 60);
            const seconds = avgTimeSeconds % 60;
            avgTime.textContent = `${minutes}:${seconds.toString().padStart(2, '0')}`;
            
            const sharedCount = submissions.filter(s => s.shared).length;
            const shareRateValue = Math.round((sharedCount / submissions.length) * 100);
            shareRate.textContent = `${shareRateValue}%`;
            
            // 填充表格
            dataTableBody.innerHTML = '';
            submissions.forEach(submission => {
                const row = document.createElement('tr');
                row.innerHTML = `
                    <td class="px-4 py-3 whitespace-nowrap text-sm text-gray-900">${submission.id}</td>
                    <td class="px-4 py-3 whitespace-nowrap text-sm text-gray-500">${new Date(submission.timestamp).toLocaleString()}</td>
                    <td class="px-4 py-3 whitespace-nowrap text-sm text-gray-500">${submission.gender === 'male' ? '男' : '女'}</td>
                    <td class="px-4 py-3 whitespace-nowrap text-sm text-gray-500">${submission.age}</td>
                    <td class="px-4 py-3 whitespace-nowrap text-sm text-gray-500">${submission.onlyChild === 'yes' ? '是' : '否'}</td>
                    <td class="px-4 py-3 whitespace-nowrap text-sm text-gray-500">${submission.hometown === 'urban' ? '城镇' : '农村'}</td>
                    <td class="px-4 py-3 whitespace-nowrap text-sm text-gray-500">${submission.familyType === 'singleParent' ? '单亲' : '非单亲'}</td>
                    <td class="px-4 py-3 whitespace-nowrap text-sm text-gray-900 font-medium">${submission.personalityTitle}</td>
                    <td class="px-4 py-3 whitespace-nowrap text-sm text-gray-500">${submission.scores.selfEsteem}</td>
                    <td class="px-4 py-3 whitespace-nowrap text-sm text-gray-500">${submission.scores.lifeSatisfaction}</td>
                    <td class="px-4 py-3 whitespace-nowrap text-sm text-gray-500">${submission.scores.emotionalState}</td>
                    <td class="px-4 py-3 whitespace-nowrap text-sm text-gray-500">${submission.scores.selfConcept}</td>
                    <td class="px-4 py-3 whitespace-nowrap text-sm text-gray-500">${submission.scores.resilience}</td>
                    <td class="px-4 py-3 whitespace-nowrap text-sm text-gray-500">
                        <button class="text-red-500 hover:text-red-700 delete-btn" data-id="${submission.id}">
                            <i class="fa fa-trash"></i>
                        </button>
                    </td>
                `;
                dataTableBody.appendChild(row);
            });
            
            // 添加删除事件
            document.querySelectorAll('.delete-btn').forEach(btn => {
                btn.addEventListener('click', (e) => {
                    const id = parseInt(e.currentTarget.dataset.id);
                    deleteSubmission(id);
                });
            });
        }

        // 删除提交记录
        function deleteSubmission(id) {
            if (confirm('确定要删除这条记录吗？')) {
                let submissions = JSON.parse(localStorage.getItem('testSubmissions') || '[]');
                submissions = submissions.filter(s => s.id !== id);
                localStorage.setItem('testSubmissions', JSON.stringify(submissions));
                loadAdminData();
                showToast("记录已删除");
            }
        }

        // 导出为CSV
        function exportToCsv() {
            const submissions = JSON.parse(localStorage.getItem('testSubmissions') || '[]');
            
            if (submissions.length === 0) {
                showToast("没有数据可导出");
                return;
            }
            
            // CSV头部
            let csv = "ID,提交时间,完成时间(秒),性别,年龄,独生子女,生源地,家庭类型,人格类型,自尊水平,生活满意度,情绪状态,自我概念,心理韧性,是否分享\n";
            
            // CSV数据
            submissions.forEach(s => {
                csv += `${s.id},"${new Date(s.timestamp).toLocaleString()}",${s.completionTime},${s.gender === 'male' ? '男' : '女'},${s.age},${s.onlyChild === 'yes' ? '是' : '否'},${s.hometown === 'urban' ? '城镇' : '农村'},${s.familyType === 'singleParent' ? '单亲' : '非单亲'},"${s.personalityTitle}",${s.scores.selfEsteem},${s.scores.lifeSatisfaction},${s.scores.emotionalState},${s.scores.selfConcept},${s.scores.resilience},${s.shared ? '是' : '否'}\n`;
            });
            
            // 创建下载链接
            const blob = new Blob(['\ufeff' + csv], { type: 'text/csv;charset=utf-8;' });
            const url = URL.createObjectURL(blob);
            const a = document.createElement('a');
            a.href = url;
            a.download = `大学生心理特质测试数据_${new Date().toLocaleDateString().replace(/\//g, '-')}.csv`;
            document.body.appendChild(a);
            a.click();
            document.body.removeChild(a);
            URL.revokeObjectURL(url);
            
            showToast("数据已导出");
        }

        // 退出登录
        function logout() {
            adminDataSection.classList.add('hidden');
            showWelcome();
        }

        // 显示提示框
        function showToast(message) {
            toastMessage.textContent = message;
            toast.classList.remove('translate-y-20', 'opacity-0');
            
            setTimeout(() => {
                toast.classList.add('translate-y-20', 'opacity-0');
            }, 3000);
        }

        // 页面加载完成后初始化
        document.addEventListener('DOMContentLoaded', init);
    </script>
</body>
</html>
用来储存我的网络问卷代码
