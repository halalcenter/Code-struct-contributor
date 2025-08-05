# Code-struct-contributor
```
code-struct/
├── README.md
├── next.config.js
├── package.json
├── tailwind.config.js
├── tsconfig.json
├── .env.local
├── .gitignore
├── docker-compose.yml              # For Judge0 setup
├── middleware.ts                   # Route protection (in root for Next.js)
│
├── src/                           # Source directory
│   ├── app/                       # Next.js 13+ App Router
│   │   ├── globals.css
│   │   ├── layout.tsx
│   │   ├── page.tsx               # Homepage
│   │   ├── loading.tsx
│   │   ├── not-found.tsx
│   │   │
│   │   ├── (auth)/                # Route groups for auth
│   │   │   ├── login/
│   │   │   │   └── page.tsx
│   │   │   ├── register/
│   │   │   │   └── page.tsx
│   │   │   ├── forgot-password/
│   │   │   │   └── page.tsx
│   │   │   ├── reset-password/
│   │   │   │   └── page.tsx
│   │   │   └── layout.tsx         # Auth layout (no header/footer)
│   │   │
│   │   ├── dashboard/
│   │   │   ├── page.tsx           # Main dashboard
│   │   │   ├── analytics/
│   │   │   │   └── page.tsx       # AI analytics page
│   │   │   ├── progress/
│   │   │   │   └── page.tsx       # Progress tracking
│   │   │   ├── submissions/
│   │   │   │   └── page.tsx       # User's submissions history
│   │   │   └── layout.tsx         # Dashboard layout
│   │   │
│   │   ├── problems/
│   │   │   ├── page.tsx           # Problems list/browse
│   │   │   ├── [id]/
│   │   │   │   ├── page.tsx       # Individual problem solving
│   │   │   │   ├── submissions/
│   │   │   │   │   └── page.tsx   # Problem submission history
│   │   │   │   └── discuss/
│   │   │   │       └── page.tsx   # Problem discussion
│   │   │   ├── categories/
│   │   │   │   ├── page.tsx       # All categories
│   │   │   │   └── [category]/
│   │   │   │       └── page.tsx   # Problems by category
│   │   │   ├── difficulty/
│   │   │   │   └── [level]/
│   │   │   │       └── page.tsx   # Problems by difficulty
│   │   │   ├── potd/              # Problem of the Day
│   │   │   │   ├── page.tsx       # Current POTD
│   │   │   │   ├── archive/
│   │   │   │   │   └── page.tsx   # POTD archive
│   │   │   │   └── [date]/
│   │   │   │       └── page.tsx   # Specific date POTD
│   │   │   └── submit/            # User problem submission
│   │   │       └── page.tsx
│   │   │
│   │   ├── contests/
│   │   │   ├── page.tsx           # Contests list
│   │   │   ├── [id]/
│   │   │   │   ├── page.tsx       # Contest details/lobby
│   │   │   │   ├── register/
│   │   │   │   │   └── page.tsx   # Contest registration
│   │   │   │   ├── problems/
│   │   │   │   │   ├── page.tsx   # Contest problems list
│   │   │   │   │   └── [problemId]/
│   │   │   │   │       └── page.tsx # Contest problem solving
│   │   │   │   ├── leaderboard/
│   │   │   │   │   └── page.tsx   # Contest leaderboard
│   │   │   │   └── submissions/
│   │   │   │       └── page.tsx   # Contest submissions
│   │   │   ├── rapid-fire/
│   │   │   │   ├── page.tsx       # Rapid fire sessions list
│   │   │   │   ├── [sessionId]/
│   │   │   │   │   ├── page.tsx   # Session lobby/details
│   │   │   │   │   ├── play/
│   │   │   │   │   │   └── page.tsx # Active rapid fire session
│   │   │   │   │   └── results/
│   │   │   │   │       └── page.tsx # Session results
│   │   │   │   └── leaderboard/
│   │   │   │       └── page.tsx   # Rapid fire leaderboard
│   │   │   └── create/            # Create contest (admin)
│   │   │       └── page.tsx
│   │   │
│   │   ├── profile/
│   │   │   ├── page.tsx           # Own profile redirect
│   │   │   ├── [username]/
│   │   │   │   ├── page.tsx       # Public profile view
│   │   │   │   ├── submissions/
│   │   │   │   │   └── page.tsx   # User's public submissions
│   │   │   │   ├── contests/
│   │   │   │   │   └── page.tsx   # User's contest history
│   │   │   │   └── statistics/
│   │   │   │       └── page.tsx   # User's public stats
│   │   │   ├── edit/
│   │   │   │   └── page.tsx       # Edit own profile
│   │   │   └── settings/
│   │   │       ├── page.tsx       # Account settings
│   │   │       ├── preferences/
│   │   │       │   └── page.tsx   # User preferences
│   │   │       └── security/
│   │   │           └── page.tsx   # Security settings
│   │   │
│   │   ├── leaderboard/
│   │   │   ├── page.tsx           # Global leaderboard
│   │   │   ├── contests/
│   │   │   │   ├── page.tsx       # Contest leaderboards
│   │   │   │   └── [contestId]/
│   │   │   │       └── page.tsx   # Specific contest leaderboard
│   │   │   ├── rapid-fire/
│   │   │   │   └── page.tsx       # Rapid fire leaderboards
│   │   │   ├── potd/
│   │   │   │   └── page.tsx       # POTD leaderboard
│   │   │   └── categories/
│   │   │       └── [category]/
│   │   │           └── page.tsx   # Category-wise leaderboard
│   │   │
│   │   ├── admin/
│   │   │   ├── layout.tsx         # Admin layout with sidebar
│   │   │   ├── page.tsx           # Admin dashboard
│   │   │   ├── problems/
│   │   │   │   ├── page.tsx       # Problems management
│   │   │   │   ├── create/
│   │   │   │   │   └── page.tsx   # Create new problem
│   │   │   │   ├── [id]/
│   │   │   │   │   ├── page.tsx   # Edit problem
│   │   │   │   │   ├── edit/
│   │   │   │   │   │   └── page.tsx # Edit problem details
│   │   │   │   │   ├── test-cases/
│   │   │   │   │   │   └── page.tsx # Manage test cases
│   │   │   │   │   └── preview/
│   │   │   │   │       └── page.tsx # Preview problem
│   │   │   │   ├── submissions/   # User submitted problems for review
│   │   │   │   │   ├── page.tsx   # Pending submissions list
│   │   │   │   │   └── [id]/
│   │   │   │   │       ├── page.tsx # Review submission
│   │   │   │   │       └── feedback/
│   │   │   │   │           └── page.tsx # Provide feedback
│   │   │   │   ├── categories/
│   │   │   │   │   └── page.tsx   # Manage categories
│   │   │   │   └── bulk/
│   │   │   │       └── page.tsx   # Bulk operations
│   │   │   ├── contests/
│   │   │   │   ├── page.tsx       # Contest management
│   │   │   │   ├── create/
│   │   │   │   │   └── page.tsx   # Create contest
│   │   │   │   ├── [id]/
│   │   │   │   │   ├── page.tsx   # Contest overview
│   │   │   │   │   ├── edit/
│   │   │   │   │   │   └── page.tsx # Edit contest
│   │   │   │   │   ├── participants/
│   │   │   │   │   │   └── page.tsx # Manage participants
│   │   │   │   │   ├── problems/
│   │   │   │   │   │   └── page.tsx # Manage contest problems
│   │   │   │   │   └── results/
│   │   │   │   │       └── page.tsx # Contest results
│   │   │   │   └── rapid-fire/
│   │   │   │       ├── page.tsx   # Rapid fire management
│   │   │   │       └── create/
│   │   │   │           └── page.tsx # Create rapid fire session
│   │   │   ├── users/
│   │   │   │   ├── page.tsx       # User management
│   │   │   │   ├── [id]/
│   │   │   │   │   ├── page.tsx   # User details
│   │   │   │   │   ├── edit/
│   │   │   │   │   │   └── page.tsx # Edit user
│   │   │   │   │   └── ban/
│   │   │   │   │       └── page.tsx # User moderation
│   │   │   │   ├── roles/
│   │   │   │   │   └── page.tsx   # Role management
│   │   │   │   └── bulk/
│   │   │   │       └── page.tsx   # Bulk user operations
│   │   │   ├── analytics/
│   │   │   │   ├── page.tsx       # Platform analytics overview
│   │   │   │   ├── users/
│   │   │   │   │   └── page.tsx   # User analytics
│   │   │   │   ├── problems/
│   │   │   │   │   └── page.tsx   # Problem analytics
│   │   │   │   ├── contests/
│   │   │   │   │   └── page.tsx   # Contest analytics
│   │   │   │   └── performance/
│   │   │   │       └── page.tsx   # System performance
│   │   │   ├── settings/
│   │   │   │   ├── page.tsx       # Platform settings
│   │   │   │   ├── email/
│   │   │   │   │   └── page.tsx   # Email settings
│   │   │   │   ├── security/
│   │   │   │   │   └── page.tsx   # Security settings
│   │   │   │   └── integrations/
│   │   │   │       └── page.tsx   # Third-party integrations
│   │   │   └── logs/
│   │   │       └── page.tsx       # System logs
│   │   │
│   │   └── api/                   # API Routes
│   │       ├── auth/
│   │       │   ├── register/
│   │       │   │   └── route.ts   # User registration
│   │       │   ├── login/
│   │       │   │   └── route.ts   # User login
│   │       │   ├── logout/
│   │       │   │   └── route.ts   # User logout
│   │       │   ├── forgot-password/
│   │       │   │   └── route.ts   # Password reset request
│   │       │   ├── reset-password/
│   │       │   │   └── route.ts   # Password reset
│   │       │   ├── verify-email/
│   │       │   │   └── route.ts   # Email verification
│   │       │   └── [...nextauth]/
│   │       │       └── route.ts   # NextAuth configuration
│   │       │
│   │       ├── problems/
│   │       │   ├── route.ts       # GET all problems, POST create
│   │       │   ├── [id]/
│   │       │   │   ├── route.ts   # GET, PUT, DELETE specific problem
│   │       │   │   ├── submit/
│   │       │   │   │   └── route.ts # Submit solution
│   │       │   │   ├── submissions/
│   │       │   │   │   └── route.ts # Get problem submissions
│   │       │   │   └── discuss/
│   │       │   │       └── route.ts # Problem discussions
│   │       │   ├── categories/
│   │       │   │   ├── route.ts   # Get all categories
│   │       │   │   └── [category]/
│   │       │   │       └── route.ts # Problems by category
│   │       │   ├── difficulty/
│   │       │   │   └── [level]/
│   │       │   │       └── route.ts # Problems by difficulty
│   │       │   ├── search/
│   │       │   │   └── route.ts   # Search problems
│   │       │   ├── potd/
│   │       │   │   ├── route.ts   # Get/Set problem of the day
│   │       │   │   └── archive/
│   │       │   │       └── route.ts # POTD archive
│   │       │   └── user-submissions/
│   │       │       ├── route.ts   # List user problem submissions
│   │       │       └── [id]/
│   │       │           ├── route.ts # Manage user submission
│   │       │           ├── approve/
│   │       │           │   └── route.ts # Approve submission
│   │       │           └── reject/
│   │       │               └── route.ts # Reject submission
│   │       │
│   │       ├── contests/
│   │       │   ├── route.ts       # GET all contests, POST create
│   │       │   ├── [id]/
│   │       │   │   ├── route.ts   # GET, PUT, DELETE contest
│   │       │   │   ├── register/
│   │       │   │   │   └── route.ts # Register for contest
│   │       │   │   ├── unregister/
│   │       │   │   │   └── route.ts # Unregister from contest
│   │       │   │   ├── leaderboard/
│   │       │   │   │   └── route.ts # Contest leaderboard
│   │       │   │   ├── submissions/
│   │       │   │   │   └── route.ts # Contest submissions
│   │       │   │   └── problems/
│   │       │   │       └── route.ts # Contest problems
│   │       │   ├── rapid-fire/
│   │       │   │   ├── route.ts   # Rapid fire sessions
│   │       │   │   └── [sessionId]/
│   │       │   │       ├── route.ts # Session details
│   │       │   │       ├── start/
│   │       │   │       │   └── route.ts # Start session
│   │       │   │       ├── submit/
│   │       │   │       │   └── route.ts # Submit rapid fire answer
│   │       │   │       └── end/
│   │       │   │           └── route.ts # End session
│   │       │   ├── upcoming/
│   │       │   │   └── route.ts   # Upcoming contests
│   │       │   └── past/
│   │       │       └── route.ts   # Past contests
│   │       │
│   │       ├── submissions/
│   │       │   ├── route.ts       # User submissions history
│   │       │   ├── [id]/
│   │       │   │   └── route.ts   # Specific submission details
│   │       │   ├── status/
│   │       │   │   └── [token]/
│   │       │   │       └── route.ts # Check Judge0 execution status
│   │       │   └── recent/
│   │       │       └── route.ts   # Recent submissions
│   │       │
│   │       ├── execute/
│   │       │   ├── route.ts       # Code execution via Judge0
│   │       │   ├── test/
│   │       │   │   └── route.ts   # Test code execution
│   │       │   └── batch/
│   │       │       └── route.ts   # Batch execution
│   │       │
│   │       ├── users/
│   │       │   ├── route.ts       # Users list/search
│   │       │   ├── profile/
│   │       │   │   └── route.ts   # Current user profile
│   │       │   ├── progress/
│   │       │   │   └── route.ts   # User progress and stats
│   │       │   ├── [username]/
│   │       │   │   ├── route.ts   # Public profile data
│   │       │   │   ├── submissions/
│   │       │   │   │   └── route.ts # User's public submissions
│   │       │   │   └── contests/
│   │       │   │       └── route.ts # User's contest history
│   │       │   ├── analytics/
│   │       │   │   └── route.ts   # AI analytics data
│   │       │   ├── preferences/
│   │       │   │   └── route.ts   # User preferences
│   │       │   └── streaks/
│   │       │       └── route.ts   # User streaks data
│   │       │
│   │       ├── leaderboard/
│   │       │   ├── global/
│   │       │   │   └── route.ts   # Global leaderboard
│   │       │   ├── contest/
│   │       │   │   └── [id]/
│   │       │   │       └── route.ts # Contest leaderboard
│   │       │   ├── rapid-fire/
│   │       │   │   └── route.ts   # Rapid fire leaderboard
│   │       │   ├── potd/
│   │       │   │   └── route.ts   # POTD leaderboard
│   │       │   └── categories/
│   │       │       └── [category]/
│   │       │           └── route.ts # Category leaderboard
│   │       │
│   │       ├── analytics/
│   │       │   ├── user/
│   │       │   │   └── route.ts   # User analytics
│   │       │   ├── platform/
│   │       │   │   └── route.ts   # Platform analytics
│   │       │   ├── problems/
│   │       │   │   └── route.ts   # Problem analytics
│   │       │   └── ai-insights/
│   │       │       └── route.ts   # AI-powered insights
│   │       │
│   │       ├── notifications/
│   │       │   ├── route.ts       # Get notifications
│   │       │   ├── mark-read/
│   │       │   │   └── route.ts   # Mark as read
│   │       │   └── preferences/
│   │       │       └── route.ts   # Notification preferences
│   │       │
│   │       ├── search/
│   │       │   ├── route.ts       # Global search
│   │       │   ├── problems/
│   │       │   │   └── route.ts   # Search problems
│   │       │   ├── users/
│   │       │   │   └── route.ts   # Search users
│   │       │   └── contests/
│   │       │       └── route.ts   # Search contests
│   │       │
│   │       ├── admin/
│   │       │   ├── problems/
│   │       │   │   ├── route.ts   # Admin problem operations
│   │       │   │   ├── [id]/
│   │       │   │   │   └── route.ts # Admin single problem ops
│   │       │   │   ├── bulk/
│   │       │   │   │   └── route.ts # Bulk problem operations
│   │       │   │   └── submissions/
│   │       │   │       └── route.ts # Review user submissions
│   │       │   ├── contests/
│   │       │   │   ├── route.ts   # Admin contest operations
│   │       │   │   └── [id]/
│   │       │   │       └── route.ts # Admin single contest ops
│   │       │   ├── users/
│   │       │   │   ├── route.ts   # Admin user operations
│   │       │   │   ├── [id]/
│   │       │   │   │   └── route.ts # Admin single user ops
│   │       │   │   └── bulk/
│   │       │   │       └── route.ts # Bulk user operations
│   │       │   ├── analytics/
│   │       │   │   └── route.ts   # Admin analytics
│   │       │   ├── settings/
│   │       │   │   └── route.ts   # Platform settings
│   │       │   └── logs/
│   │       │       └── route.ts   # System logs
│   │       │
│   │       ├── judge0/
│   │       │   ├── languages/
│   │       │   │   └── route.ts   # Get supported languages
│   │       │   ├── status/
│   │       │   │   └── route.ts   # Judge0 system status
│   │       │   └── config/
│   │       │       └── route.ts   # Judge0 configuration
│   │       │
│   │       └── webhooks/
│   │           ├── judge0/
│   │           │   └── route.ts   # Judge0 webhook endpoint
│   │           ├── email/
│   │           │   └── route.ts   # Email service webhooks
│   │           └── payments/       # Future payment integration
│   │               └── route.ts
│   │
│   ├── components/                # Reusable UI Components
│   │   ├── ui/                   # Base UI components (shadcn/ui style)
│   │   │   ├── button.tsx
│   │   │   ├── input.tsx
│   │   │   ├── textarea.tsx
│   │   │   ├── select.tsx
│   │   │   ├── checkbox.tsx
│   │   │   ├── radio-group.tsx
│   │   │   ├── switch.tsx
│   │   │   ├── slider.tsx
│   │   │   ├── card.tsx
│   │   │   ├── dialog.tsx
│   │   │   ├── sheet.tsx
│   │   │   ├── popover.tsx
│   │   │   ├── dropdown-menu.tsx
│   │   │   ├── navigation-menu.tsx
│   │   │   ├── table.tsx
│   │   │   ├── tabs.tsx
│   │   │   ├── accordion.tsx
│   │   │   ├── alert.tsx
│   │   │   ├── badge.tsx
│   │   │   ├── avatar.tsx
│   │   │   ├── progress.tsx
│   │   │   ├── separator.tsx
│   │   │   ├── toast.tsx
│   │   │   ├── tooltip.tsx
│   │   │   ├── skeleton.tsx
│   │   │   ├── calendar.tsx
│   │   │   ├── command.tsx
│   │   │   ├── context-menu.tsx
│   │   │   ├── hover-card.tsx
│   │   │   ├── label.tsx
│   │   │   ├── menubar.tsx
│   │   │   ├── scroll-area.tsx
│   │   │   └── index.ts          # Export all UI components
│   │   │
│   │   ├── layout/               # Layout components
│   │   │   ├── Header.tsx
│   │   │   ├── Footer.tsx
│   │   │   ├── Sidebar.tsx
│   │   │   ├── Navigation.tsx
│   │   │   ├── AdminSidebar.tsx
│   │   │   ├── MobileNav.tsx
│   │   │   ├── UserMenu.tsx
│   │   │   ├── ThemeToggle.tsx
│   │   │   └── Breadcrumbs.tsx
│   │   │
│   │   ├── auth/                 # Authentication components
│   │   │   ├── LoginForm.tsx
│   │   │   ├── RegisterForm.tsx
│   │   │   ├── ForgotPasswordForm.tsx
│   │   │   ├── ResetPasswordForm.tsx
│   │   │   ├── EmailVerification.tsx
│   │   │   ├── AuthGuard.tsx
│   │   │   ├── AdminGuard.tsx
│   │   │   ├── RoleGuard.tsx
│   │   │   └── SocialLogin.tsx
│   │   │
│   │   ├── editor/               # Code editor components
│   │   │   ├── CodeEditor.tsx    # Monaco editor wrapper
│   │   │   ├── LanguageSelector.tsx
│   │   │   ├── ThemeSelector.tsx
│   │   │   ├── EditorSettings.tsx
│   │   │   ├── EditorToolbar.tsx
│   │   │   ├── CodeTemplate.tsx
│   │   │   ├── SyntaxHighlighter.tsx
│   │   │   └── EditorShortcuts.tsx
│   │   │
│   │   ├── problems/             # Problem related components
│   │   │   ├── ProblemCard.tsx
│   │   │   ├── ProblemList.tsx
│   │   │   ├── ProblemGrid.tsx
│   │   │   ├── ProblemDetails.tsx
│   │   │   ├── ProblemStatement.tsx
│   │   │   ├── ProblemConstraints.tsx
│   │   │   ├── ProblemExamples.tsx
│   │   │   ├── TestCases.tsx
│   │   │   ├── TestCaseEditor.tsx
│   │   │   ├── SubmissionResult.tsx
│   │   │   ├── SubmissionHistory.tsx
│   │   │   ├── DifficultyBadge.tsx
│   │   │   ├── CategoryBadge.tsx
│   │   │   ├── CategoryFilter.tsx
│   │   │   ├── DifficultyFilter.tsx
│   │   │   ├── ProblemSearch.tsx
│   │   │   ├── ProblemSort.tsx
│   │   │   ├── ProblemTags.tsx
│   │   │   ├── SolutionViewer.tsx
│   │   │   ├── HintsPanel.tsx
│   │   │   ├── DiscussionPanel.tsx
│   │   │   └── RelatedProblems.tsx
│   │   │
│   │   ├── contests/             # Contest components
│   │   │   ├── ContestCard.tsx
│   │   │   ├── ContestList.tsx
│   │   │   ├── ContestGrid.tsx
│   │   │   ├── ContestDetails.tsx
│   │   │   ├── ContestTimer.tsx
│   │   │   ├── ContestCountdown.tsx
│   │   │   ├── ContestStatus.tsx
│   │   │   ├── Leaderboard.tsx
│   │   │   ├── LeaderboardRow.tsx
│   │   │   ├── RankingChart.tsx
│   │   │   ├── ContestRegistration.tsx
│   │   │   ├── ContestRules.tsx
│   │   │   ├── RapidFireSession.tsx
│   │   │   ├── RapidFireTimer.tsx
│   │   │   ├── RapidFireProgress.tsx
│   │   │   ├── RapidFireResults.tsx
│   │   │   ├── QuickSubmit.tsx
│   │   │   └── ContestHistory.tsx
│   │   │
│   │   ├── dashboard/            # Dashboard components
│   │   │   ├── DashboardGrid.tsx
│   │   │   ├── StatsCard.tsx
│   │   │   ├── MetricCard.tsx
│   │   │   ├── ProgressChart.tsx
│   │   │   ├── PerformanceChart.tsx
│   │   │   ├── StreakDisplay.tsx
│   │   │   ├── StreakCalendar.tsx
│   │   │   ├── RecentActivity.tsx
│   │   │   ├── ActivityFeed.tsx
│   │   │   ├── POTD.tsx          # Problem of the day widget
│   │   │   ├── QuickActions.tsx
│   │   │   ├── ActionButton.tsx
│   │   │   ├── UpcomingContests.tsx
│   │   │   ├── RecentSubmissions.tsx
│   │   │   ├── SkillProgress.tsx
│   │   │   ├── AchievementsBadges.tsx
│   │   │   └── AIInsights.tsx    # AI analytics widget
│   │   │
│   │   ├── admin/                # Admin panel components
│   │   │   ├── AdminDashboard.tsx
│   │   │   ├── AdminStats.tsx
│   │   │   ├── ProblemEditor.tsx
│   │   │   ├── ProblemManager.tsx
│   │   │   ├── ContestEditor.tsx
│   │   │   ├── ContestManager.tsx
│   │   │   ├── UserManagement.tsx
│   │   │   ├── UserTable.tsx
│   │   │   ├── SubmissionReview.tsx
│   │   │   ├── ReviewQueue.tsx
│   │   │   ├── AnalyticsDashboard.tsx
│   │   │   ├── PlatformMetrics.tsx
│   │   │   ├── BulkOperations.tsx
│   │   │   ├── DataExport.tsx
│   │   │   ├── SystemLogs.tsx
│   │   │   ├── SettingsPanel.tsx
│   │   │   ├── RoleManager.tsx
│   │   │   └── ModerationTools.tsx
│   │   │
│   │   ├── analytics/            # AI Analytics components
│   │   │   ├── AnalyticsGrid.tsx
│   │   │   ├── SkillRadar.tsx
│   │   │   ├── SkillChart.tsx
│   │   │   ├── PerformanceTrends.tsx
│   │   │   ├── TrendChart.tsx
│   │   │   ├── Recommendations.tsx
│   │   │   ├── RecommendationCard.tsx
│   │   │   ├── LearningPath.tsx
│   │   │   ├── PathProgress.tsx
│   │   │   ├── CodeQualityScore.tsx
│   │   │   ├── QualityMetrics.tsx
│   │   │   ├── PredictiveInsights.tsx
│   │   │   ├── InsightCard.tsx
│   │   │   ├── WeaknessAnalysis.tsx
│   │   │   ├── StrengthAnalysis.tsx
│   │   │   ├── CompetitivePrediction.tsx
│   │   │   └── AICoach.tsx
│   │   │
│   │   ├── notifications/        # Notification components
│   │   │   ├── NotificationBell.tsx
│   │   │   ├── NotificationList.tsx
│   │   │   ├── NotificationItem.tsx
│   │   │   ├── NotificationCenter.tsx
│   │   │   └── NotificationSettings.tsx
│   │   │
│   │   ├── search/               # Search components
│   │   │   ├── GlobalSearch.tsx
│   │   │   ├── SearchResults.tsx
│   │   │   ├── SearchFilters.tsx
│   │   │   ├── SearchSuggestions.tsx
│   │   │   └── AdvancedSearch.tsx
│   │   │
│   │   └── common/               # Common utility components
│   │       ├── LoadingSpinner.tsx
│   │       ├── LoadingButton.tsx
│   │       ├── LoadingSkeleton.tsx
│   │       ├── ErrorBoundary.tsx
│   │       ├── ErrorMessage.tsx
│   │       ├── EmptyState.tsx
│   │       ├── ConfirmDialog.tsx
│   │       ├── DeleteDialog.tsx
│   │       ├── SearchBar.tsx
│   │       ├── FilterBar.tsx
│   │       ├── SortSelect.tsx
│   │       ├── Pagination.tsx
│   │       ├── DataTable.tsx
│   │       ├── VirtualizedList.tsx
│   │       ├── FileUpload.tsx
│   │       ├── ImageUpload.tsx
│   │       ├── CopyButton.tsx
│   │       ├── ShareButton.tsx
│   │       ├── BackButton.tsx
│   │       ├── ScrollToTop.tsx
│   │       ├── Timer.tsx
│   │       ├── CountdownTimer.tsx
│   │       ├── ProgressBar.tsx
│   │       ├── StatusIndicator.tsx
│   │       ├── Tooltip.tsx
│   │       ├── Modal.tsx
│   │       ├── Drawer.tsx
│   │       ├── Tabs.tsx
│   │       ├── Accordion.tsx
│   │       └── FormField.tsx
│   │
│   ├── lib/                      # Utility libraries and configurations
│   │   ├── auth.ts               # NextAuth configuration
│   │   ├── db.ts                 # Database connection (Prisma)
│   │   ├── judge0.ts             # Judge0 API wrapper
│   │   ├── validations.ts        # Zod schemas for validation
│   │   ├── utils.ts              # General utility functions
│   │   ├── constants.ts          # App constants
│   │   ├── analytics.ts          # AI analytics functions
│   │   ├── ai-engine.ts          # AI analysis engine
│   │   ├── email.ts              # Email service
│   │   ├── storage.ts            # File storage utilities
│   │   ├── websocket.ts          # WebSocket handling
│   │   ├── cache.ts              # Caching utilities
│   │   ├── encryption.ts         # Encryption utilities
│   │   ├── rate-limit.ts         # Rate limiting
│   │   ├── middleware.ts         # Custom middleware functions
│   │   ├── logger.ts             # Logging utilities
│   │   ├── monitoring.ts         # Performance monitoring
│   │   ├── queue.ts              # Background job queue
│   │   ├── notifications.ts      # Notification service
│   │   ├── search.ts             # Search functionality
│   │   └── testing.ts            # Testing utilities
│   │
│   ├── types/                    # TypeScript type definitions
│   │   ├── auth.ts               # Authentication types
│   │   ├── user.ts               # User related types
│   │   ├── problem.ts            # Problem related types
│   │   ├── contest.ts            # Contest related types
│   │   ├── submission.ts         # Submission related types
│   │   ├── analytics.ts          # Analytics types
│   │   ├── judge0.ts             # Judge0 API types
│   │   ├── api.ts                # API response types
│   │   ├── database.ts           # Database types
│   │   ├── ui.ts                 # UI component types
│   │   ├── notification.ts       # Notification types
│   │   ├── search.ts             # Search types
│   │   ├── admin.ts              # Admin types
│   │   ├── global.ts             # Global types
│   │   └── index.ts              # Export all types
│   │
│   ├── hooks/                    # Custom React hooks
│   │   ├── useAuth.ts            # Authentication hook
│   │   ├── useUser.ts            # User data hook
│   │   ├── useLocalStorage.ts    # Local storage hook
│   │   ├── useSessionStorage.ts  # Session storage hook
│   │   ├── useDebounce.ts        # Debounce hook
│   │   ├── useThrottle.ts        # Throttle hook
│   │   ├── useProblem.ts         # Problem data hook
│   │   ├── useProblems.ts        # Problems list hook
│   │   ├── useContest.ts         # Contest data hook
│   │   ├── useContests.ts        # Contests list hook
│   │   ├── useSubmission.ts      # Submission hook
│   │   ├── useSubmissions.ts     # Submissions list hook
│   │   ├── useWebSocket.ts       # WebSocket hook
│   │   ├── useAnalytics.ts       # Analytics hook
│   │   ├── useSearch.ts          # Search hook
│   │   ├── useNotifications.ts   # Notifications hook
│   │   ├── useTimer.ts           # Timer hook
│   │   ├── useCountdown.ts       # Countdown hook
│   │   ├── useProgress.ts        # Progress tracking hook
│   │   ├── useLeaderboard.ts     # Leaderboard hook
│   │   ├── useInfiniteScroll.ts  # Infinite scroll hook
│   │   ├── useVirtualization.ts  # List virtualization hook
│   │   ├── usePagination.ts      # Pagination hook
│   │   ├── useForm.ts            # Form handling hook
│   │   ├── useValidation.ts      # Validation hook
│   │   ├── useAsync.ts           # Async operations hook
│   │   ├── useApi.ts             # API calls hook
│   │   ├── useUpload.ts          # File upload hook
│   │   ├── useClipboard.ts       # Clipboard hook
│   │   ├── useKeyboard.ts        # Keyboard shortcuts hook
│   │   ├── useMediaQuery.ts      # Media query hook
│   │   ├── useTheme.ts           # Theme hook
│   │   └── usePermissions.ts     # Permissions hook
│   │
│   ├── context/                  # React Context providers
│   │   ├── AuthContext.tsx       # Authentication context
│   │   ├── UserContext.tsx       # User data context
│   │   ├── ThemeContext.tsx      # Theme context
│   │   ├── ContestContext.tsx    # Contest context
│   │   ├── AnalyticsContext.tsx  # Analytics context
│   │   ├── NotificationContext.tsx # Notification context
│   │   ├── SocketContext.tsx     # WebSocket context
│   │   ├── SearchContext.tsx     # Search context
│   │   └── GlobalContext.tsx     # Global app context
│   │
│   ├── styles/                   # Additional styling
│   │   ├── globals.css           # Global styles
│   │   ├── components.css        # Component-specific styles
│   │   ├── editor.css            # Code editor styles
│   │   ├── animations.css        # Animation definitions
│   │   ├── utilities.css         # Utility classes
│   │   └── themes/               # Theme definitions
│   │       ├── light.css
│   │       ├── dark.css
│   │       └── high-contrast.css
│   │
│   └── data/                     # Static data and configurations
│       ├── languages.ts          # Programming languages config
│       ├── categories.ts         # Problem categories
│       ├── difficulties.ts       # Difficulty levels
│       ├── countries.ts          # Countries list
│       ├── templates.ts          # Code templates
│       ├── examples.ts           # Example problems
│       └── seeds/                # Database seed data
│           ├── problems.json
│           ├── contests.json
│           ├── users.json
│           └── categories.json
│
├── prisma/                       # Database schema and migrations
│   ├── schema.prisma             # Database schema
│   ├── seed.ts                   # Database seeding script
│   ├── migrations/               # Database migrations
│   │   └── [timestamp]_[name]/
│   │       └── migration.sql
│   ├── seeds/                    # Seed data files
│   │   ├── users.ts
│   │   ├── problems.ts
│   │   ├── contests.ts
│   │   └── categories.ts
│   └── backup/                   # Database backups
│       └── [timestamp].sql
│
├── public/                       # Static assets
│   ├── images/
│   │   ├── logo.svg
│   │   ├── logo-dark.svg
│   │   ├── hero.jpg
│   │   ├── hero-dark.jpg
│   │   ├── placeholders/
│   │   │   ├── avatar.png
│   │   │   ├── problem.png
│   │   │   └── contest.png
│   │   └── avatars/
│   │       ├── default.png
│   │       └── generated/
│   ├── icons/
│   │   ├── languages/            # Programming language icons
│   │   │   ├── python.svg
│   │   │   ├── javascript.svg
│   │   │   ├── typescript.svg
│   │   │   ├── cpp.svg
│   │   │   ├── c.svg
│   │   │   ├── java.svg
│   │   │   ├── csharp.svg
│   │   │   ├── go.svg
│   │   │   ├── rust.svg
│   │   │   ├── kotlin.svg
│   │   │   ├── swift.svg
│   │   │   ├── php.svg
│   │   │   ├── ruby.svg
│   │   │   └── scala.svg
│   │   ├── difficulty/           # Difficulty level icons
│   │   │   ├── easy.svg
│   │   │   ├── medium.svg
│   │   │   ├── hard.svg
│   │   │   └── expert.svg
│   │   ├── categories/           # Category icons
│   │   │   ├── arrays.svg
│   │   │   ├── strings.svg
│   │   │   ├── trees.svg
│   │   │   ├── graphs.svg
│   │   │   ├── dynamic-programming.svg
│   │   │   ├── sorting.svg
│   │   │   ├── searching.svg
│   │   │   └── math.svg
│   │   ├── status/               # Status icons
│   │   │   ├── accepted.svg
│   │   │   ├── wrong-answer.svg
│   │   │   ├── time-limit.svg
│   │   │   ├── memory-limit.svg
│   │   │   ├── runtime-error.svg
│   │   │   └── compilation-error.svg
│   │   └── ui/                   # UI icons
│   │       ├── arrow-left.svg
│   │       ├── arrow-right.svg
│   │       ├── chevron-down.svg
│   │       ├── search.svg
│   │       ├── filter.svg
│   │       ├── sort.svg
│   │       ├── settings.svg
│   │       ├── bell.svg
│   │       ├── user.svg
│   │       ├── home.svg
│   │       ├── dashboard.svg
│   │       ├── trophy.svg
│   │       ├── fire.svg
│   │       ├── star.svg
│   │       ├── heart.svg
│   │       ├── share.svg
│   │       ├── copy.svg
│   │       ├── download.svg
│   │       ├── upload.svg
│   │       ├── edit.svg
│   │       ├── delete.svg
│   │       ├── close.svg
│   │       ├── check.svg
│   │       ├── plus.svg
│   │       ├── minus.svg
│   │       ├── refresh.svg
│   │       ├── loading.svg
│   │       ├── error.svg
│   │       ├── warning.svg
│   │       ├── info.svg
│   │       ├── success.svg
│   │       ├── moon.svg
│   │       ├── sun.svg
│   │       ├── menu.svg
│   │       ├── dots.svg
│   │       ├── eye.svg
│   │       ├── eye-off.svg
│   │       ├── lock.svg
│   │       ├── unlock.svg
│   │       ├── key.svg
│   │       ├── mail.svg
│   │       ├── phone.svg
│   │       ├── link.svg
│   │       ├── external-link.svg
│   │       ├── calendar.svg
│   │       ├── clock.svg
│   │       ├── timer.svg
│   │       ├── stopwatch.svg
│   │       ├── play.svg
│   │       ├── pause.svg
│   │       ├── stop.svg
│   │       ├── skip.svg
│   │       ├── volume.svg
│   │       ├── mute.svg
│   │       ├── fullscreen.svg
│   │       ├── minimize.svg
│   │       ├── maximize.svg
│   │       ├── code.svg
│   │       ├── terminal.svg
│   │       ├── database.svg
│   │       ├── server.svg
│   │       ├── cloud.svg
│   │       ├── shield.svg
│   │       ├── zap.svg
│   │       ├── activity.svg
│   │       ├── trending-up.svg
│   │       ├── trending-down.svg
│   │       ├── bar-chart.svg
│   │       ├── pie-chart.svg
│   │       ├── line-chart.svg
│   │       ├── target.svg
│   │       ├── flag.svg
│   │       ├── bookmark.svg
│   │       ├── tag.svg
│   │       ├── folder.svg
│   │       ├── file.svg
│   │       ├── image.svg
│   │       ├── video.svg
│   │       ├── audio.svg
│   │       ├── document.svg
│   │       ├── pdf.svg
│   │       ├── zip.svg
│   │       ├── github.svg
│   │       ├── google.svg
│   │       ├── facebook.svg
│   │       ├── twitter.svg
│   │       ├── linkedin.svg
│   │       ├── discord.svg
│   │       ├── slack.svg
│   │       └── teams.svg
│   ├── fonts/                    # Custom fonts
│   │   ├── inter/
│   │   ├── jetbrains-mono/       # Code editor font
│   │   └── roboto/
│   ├── sounds/                   # Audio files
│   │   ├── notification.mp3
│   │   ├── success.mp3
│   │   ├── error.mp3
│   │   ├── timer.mp3
│   │   └── click.mp3
│   ├── favicon.ico
│   ├── favicon-16x16.png
│   ├── favicon-32x32.png
│   ├── apple-touch-icon.png
│   ├── android-chrome-192x192.png
│   ├── android-chrome-512x512.png
│   ├── site.webmanifest
│   ├── robots.txt
│   └── sitemap.xml
│
├── tests/                        # Test files
│   ├── __mocks__/               # Mock files
│   │   ├── judge0.ts
│   │   ├── prisma.ts
│   │   ├── next-auth.ts
│   │   └── websocket.ts
│   ├── setup/                   # Test setup
│   │   ├── jest.config.js
│   │   ├── test-utils.tsx
│   │   ├── db-setup.ts
│   │   └── auth-setup.ts
│   ├── unit/                    # Unit tests
│   │   ├── components/
│   │   │   ├── ui/
│   │   │   ├── auth/
│   │   │   ├── problems/
│   │   │   ├── contests/
│   │   │   └── dashboard/
│   │   ├── lib/
│   │   │   ├── utils.test.ts
│   │   │   ├── validations.test.ts
│   │   │   ├── judge0.test.ts
│   │   │   └── analytics.test.ts
│   │   ├── hooks/
│   │   │   ├── useAuth.test.ts
│   │   │   ├── useProblem.test.ts
│   │   │   └── useContest.test.ts
│   │   └── types/
│   │       └── validation.test.ts
│   ├── integration/             # Integration tests
│   │   ├── api/
│   │   │   ├── auth.test.ts
│   │   │   ├── problems.test.ts
│   │   │   ├── contests.test.ts
│   │   │   └── submissions.test.ts
│   │   ├── database/
│   │   │   ├── models.test.ts
│   │   │   ├── queries.test.ts
│   │   │   └── migrations.test.ts
│   │   └── external/
│   │       ├── judge0.test.ts
│   │       └── email.test.ts
│   ├── e2e/                     # End-to-end tests
│   │   ├── auth.spec.ts
│   │   ├── problems.spec.ts
│   │   ├── contests.spec.ts
│   │   ├── submissions.spec.ts
│   │   ├── dashboard.spec.ts
│   │   ├── admin.spec.ts
│   │   └── mobile.spec.ts
│   ├── performance/             # Performance tests
│   │   ├── load-testing.ts
│   │   ├── stress-testing.ts
│   │   └── benchmark.ts
│   └── fixtures/                # Test data
│       ├── users.json
│       ├── problems.json
│       ├── contests.json
│       ├── submissions.json
│       └── test-cases.json
│
├── docs/                         # Documentation
│   ├── README.md
│   ├── DIRECTORY.md
│   ├── SETUP.md                  # Setup instructions
│   ├── DEPLOYMENT.md             # Deployment guide
│   ├── CONTRIBUTING.md           # Contribution guidelines
│   ├── CHANGELOG.md              # Change log
│   ├── LICENSE.md                # License information
│   ├── api/                      # API documentation
│   │   ├── README.md
│   │   ├── authentication.md
│   │   ├── problems.md
│   │   ├── contests.md
│   │   ├── submissions.md
│   │   ├── users.md
│   │   ├── analytics.md
│   │   └── webhooks.md
│   ├── architecture/             # Architecture documentation
│   │   ├── overview.md
│   │   ├── database-design.md
│   │   ├── api-design.md
│   │   ├── security.md
│   │   ├── performance.md
│   │   └── scalability.md
│   ├── user-guide/              # User documentation
│   │   ├── getting-started.md
│   │   ├── solving-problems.md
│   │   ├── contests.md
│   │   ├── rapid-fire.md
│   │   ├── analytics.md
│   │   └── faq.md
│   ├── admin-guide/             # Admin documentation
│   │   ├── overview.md
│   │   ├── problem-management.md
│   │   ├── contest-management.md
│   │   ├── user-management.md
│   │   ├── analytics.md
│   │   └── troubleshooting.md
│   └── developer-guide/         # Developer documentation
│       ├── overview.md
│       ├── local-setup.md
│       ├── coding-standards.md
│       ├── testing.md
│       ├── debugging.md
│       └── best-practices.md
│
├── scripts/                      # Utility scripts
│   ├── setup/                   # Setup scripts
│   │   ├── install-dependencies.sh
│   │   ├── setup-database.sh
│   │   ├── setup-judge0.sh
│   │   ├── generate-keys.sh
│   │   └── initial-setup.sh
│   ├── database/                # Database scripts
│   │   ├── seed-database.ts
│   │   ├── migrate-data.ts
│   │   ├── backup-database.ts
│   │   ├── restore-database.ts
│   │   ├── clean-database.ts
│   │   └── optimize-database.ts
│   ├── deployment/              # Deployment scripts
│   │   ├── build.sh
│   │   ├── deploy-staging.sh
│   │   ├── deploy-production.sh
│   │   ├── rollback.sh
│   │   └── health-check.sh
│   ├── maintenance/             # Maintenance scripts
│   │   ├── cleanup-old-data.ts
│   │   ├── optimize-images.ts
│   │   ├── update-statistics.ts
│   │   ├── generate-reports.ts
│   │   └── system-health.ts
│   ├── development/             # Development scripts
│   │   ├── generate-types.ts
│   │   ├── lint-fix.sh
│   │   ├── test-coverage.sh
│   │   ├── build-docs.sh
│   │   └── generate-changelog.ts
│   └── data/                    # Data management scripts
│       ├── import-problems.ts
│       ├── export-problems.ts
│       ├── validate-data.ts
│       ├── transform-data.ts
│       └── generate-test-data.ts
│
├── config/                       # Configuration files
│   ├── database.ts              # Database configuration
│   ├── auth.ts                  # Authentication configuration
│   ├── email.ts                 # Email service configuration
│   ├── storage.ts               # Storage configuration
│   ├── redis.ts                 # Redis configuration
│   ├── websocket.ts             # WebSocket configuration
│   ├── judge0.ts                # Judge0 configuration
│   ├── analytics.ts             # Analytics configuration
│   ├── logging.ts               # Logging configuration
│   ├── monitoring.ts            # Monitoring configuration
│   ├── rate-limiting.ts         # Rate limiting configuration
│   ├── security.ts              # Security configuration
│   ├── features.ts              # Feature flags
│   └── environments/            # Environment-specific configs
│       ├── development.ts
│       ├── staging.ts
│       ├── production.ts
│       └── test.ts
│
└── .github/                      # GitHub specific files
    ├── workflows/               # GitHub Actions
    │   ├── ci.yml              # Continuous Integration
    │   ├── cd.yml              # Continuous Deployment
    │   ├── test.yml            # Testing workflow
    │   ├── security.yml        # Security scanning
    │   ├── dependency-update.yml # Dependency updates
    │   └── release.yml         # Release workflow
    ├── ISSUE_TEMPLATE/          # Issue templates
    │   ├── bug_report.md
    │   ├── feature_request.md
    │   └── custom.md
    ├── PULL_REQUEST_TEMPLATE.md # PR template
    ├── CODEOWNERS              # Code owners
    ├── SECURITY.md             # Security policy
    └── FUNDING.yml             # Funding information
```
