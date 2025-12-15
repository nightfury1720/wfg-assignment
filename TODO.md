# Fullstack Engineer Assessment - Todo Tracker

## Backend Development Assignment

### Phase 1: Project Setup
- [ ] Initialize Python project with virtual environment
- [ ] Choose and set up Python framework (FastAPI/Flask/Django)
- [ ] Set up project structure and dependencies
- [ ] Configure environment variables
- [ ] Set up cloud database (PostgreSQL/MongoDB/Cloud SQL)
- [ ] Initialize database connection and models

### Phase 2: API Endpoints Implementation
- [ ] **POST /v1/webhooks/transactions**
  - [ ] Accept webhook payload with transaction_id, source_account, destination_account, amount, currency
  - [ ] Validate request body structure
  - [ ] Return 202 Accepted status code
  - [ ] Ensure response within 500ms
  - [ ] Implement idempotency check (check if transaction_id already exists)
  - [ ] Queue transaction for background processing
  - [ ] Return acknowledgment response

- [ ] **GET /** (Health Check)
  - [ ] Return status: "HEALTHY"
  - [ ] Return current_time in ISO format
  - [ ] Ensure fast response time

- [ ] **GET /v1/transactions/{transaction_id}**
  - [ ] Accept transaction_id as path parameter
  - [ ] Query database for transaction
  - [ ] Return transaction details with status, created_at, processed_at
  - [ ] Handle case when transaction not found

### Phase 3: Background Processing
- [ ] Set up background job queue (Celery/Redis Queue/Background Tasks)
- [ ] Implement transaction processing worker
  - [ ] Add 30-second delay (simulate external API calls)
  - [ ] Update transaction status to "PROCESSING" initially
  - [ ] Process transaction logic
  - [ ] Update transaction status to "PROCESSED" after completion
  - [ ] Store processed_at timestamp
  - [ ] Handle processing errors gracefully

### Phase 4: Data Storage & Models
- [ ] Design database schema for transactions
  - [ ] transaction_id (unique, indexed for idempotency)
  - [ ] source_account
  - [ ] destination_account
  - [ ] amount
  - [ ] currency
  - [ ] status (PROCESSING/PROCESSED)
  - [ ] created_at
  - [ ] processed_at (nullable)
- [ ] Create database models/ORM schemas
- [ ] Set up database migrations
- [ ] Implement transaction storage logic

### Phase 5: Idempotency Implementation
- [ ] Check for existing transaction_id before processing
- [ ] Return success response for duplicate webhooks without reprocessing
- [ ] Ensure no duplicate transactions in database
- [ ] Test duplicate webhook scenarios

### Phase 6: Error Handling & Reliability
- [ ] Implement error handling for webhook endpoint
- [ ] Implement retry logic for failed transactions
- [ ] Add logging for debugging
- [ ] Handle database connection errors
- [ ] Handle background job failures
- [ ] Ensure transactions are not lost on errors

### Phase 7: Testing
- [ ] Test single transaction webhook
- [ ] Test duplicate webhook prevention
- [ ] Test performance (response time < 500ms)
- [ ] Test reliability (error scenarios)
- [ ] Test health check endpoint
- [ ] Test transaction query endpoint
- [ ] Load testing (optional but recommended)

### Phase 8: Deployment & Documentation
- [ ] Deploy service to cloud (AWS/GCP/Azure/Railway/Render)
- [ ] Set up environment variables in production
- [ ] Configure database in production
- [ ] Test deployed endpoint
- [ ] Create README.md with:
  - [ ] Project description
  - [ ] Setup instructions
  - [ ] Running instructions
  - [ ] Testing instructions
  - [ ] API endpoint documentation
  - [ ] Brief explanation of technical choices
- [ ] Make repository public on GitHub
- [ ] Add .gitignore file
- [ ] Add requirements.txt or poetry/pipenv files

---

## Frontend Development Assignment

### Phase 1: Project Setup
- [ ] Initialize React + TypeScript project (Vite/CRA)
- [ ] Set up Tailwind CSS or similar styling solution
- [ ] Analyze superbryn.com design and theme
- [ ] Set up project structure
- [ ] Install necessary dependencies (charting library, Supabase client)

### Phase 2: Design & Styling
- [ ] Replicate superbryn.com color scheme and theme
- [ ] Create responsive layout
- [ ] Design header/navigation (if needed)
- [ ] Design main dashboard layout
- [ ] Style chart containers
- [ ] Ensure modern and clean UI/UX

### Phase 3: Chart Implementation
- [ ] Choose charting library (Recharts/Chart.js/React-Chartjs-2)
- [ ] Create call analytics charts with dummy/imaginary data:
  - [ ] Chart 1: (e.g., Call volume over time)
  - [ ] Chart 2: (e.g., Call duration distribution)
  - [ ] Chart 3: (e.g., Agent performance metrics)
  - [ ] Chart 4: (e.g., Call success rate)
  - [ ] Add more charts as needed
- [ ] Style charts to match theme
- [ ] Make charts responsive

### Phase 4: Supabase Integration
- [ ] Set up Supabase project
- [ ] Create database table for user custom values
  - [ ] email (primary key or unique)
  - [ ] chart_id or chart_name
  - [ ] custom_values (JSON or structured columns)
  - [ ] updated_at timestamp
- [ ] Install and configure Supabase client
- [ ] Set up environment variables for Supabase keys
- [ ] Create API functions for:
  - [ ] Saving custom values
  - [ ] Retrieving custom values by email

### Phase 5: Email Collection & Authentication Flow
- [ ] Create email input modal/form component
- [ ] Validate email format
- [ ] Show email collection before allowing chart edits
- [ ] Store email in state/localStorage (optional)

### Phase 6: Chart Editing Functionality
- [ ] Identify at least one chart for editing capability
- [ ] Create edit interface (inline editing or modal)
- [ ] Allow users to input custom values
- [ ] Validate custom values
- [ ] Update chart with new values
- [ ] Save custom values to Supabase with email

### Phase 7: Previous Values Handling
- [ ] On email entry, check Supabase for existing values
- [ ] If previous values exist:
  - [ ] Display previous values to user
  - [ ] Ask for confirmation to overwrite
  - [ ] Show comparison (old vs new)
- [ ] If no previous values, proceed with saving
- [ ] Update Supabase on confirmation

### Phase 8: State Management
- [ ] Manage chart data state
- [ ] Manage user email state
- [ ] Manage custom values state
- [ ] Handle loading states
- [ ] Handle error states

### Phase 9: Testing & Refinement
- [ ] Test email collection flow
- [ ] Test saving custom values
- [ ] Test retrieving previous values
- [ ] Test overwrite confirmation flow
- [ ] Test chart updates with custom values
- [ ] Test responsive design
- [ ] Cross-browser testing
- [ ] Fix any UI/UX issues

### Phase 10: Deployment & Documentation
- [ ] Build production-ready app
- [ ] Deploy to cloud (Vercel/Netlify/AWS Amplify)
- [ ] Configure environment variables in production
- [ ] Test deployed application
- [ ] Create README.md with:
  - [ ] Project description
  - [ ] Setup instructions
  - [ ] Running instructions
  - [ ] Features overview
  - [ ] Technical choices explanation
- [ ] Make repository public on GitHub
- [ ] Add .gitignore file
- [ ] Add package.json with all dependencies

---

## Overall Project Management
- [ ] Create separate directories for backend and frontend
- [ ] Set up version control (Git)
- [ ] Commit progress regularly
- [ ] Ensure both projects are production-ready
- [ ] Test end-to-end functionality
- [ ] Prepare for submission

---

## Notes
- Backend estimated time: 3-6 hours
- Frontend estimated time: 3-6 hours
- Total deadline: 24-48 hours
- Use AI tools for faster development (as mentioned in frontend requirements)

