# Flask-TaskQueue Plugin
A simple reusable Flask extension that allows you to enqueue background tasks using Redis Queue (RQ).

## Features
- Turn any function into a background task using a decorator
- Check task status via a built-in blueprint
- Works as a global plugin service shared among apps

## Setup


### Option 1: Docker Compose

Ensure you have Docker and Docker Compose installed. 
In your terminal, run the following command in the root directory:

```bash
docker-compose up --build
```

### Option 2: Manual Setup
If you prefer not to use Docker, follow these steps:

1. **Set up Python Environment & Install Dependencies**:
   ```bash
   python -m venv venv

   # On Windows:
   venv\Scripts\activate
   
   # On macOS/Linux:
   source venv/bin/activate
   
   pip install -r requirements.txt

2. **Start Redis**:
   ```bash
   redis-server

   ```

3. **Start the RQ Worker**:
   Open a new terminal session, activate your virtual environment, and start the worker:
   ```bash
   rq worker
   
   ```

4. **Run the Flask App**:
   Open another terminal session, activate the virtual environment, and run the example app:
   ```bash
   cd example_app
   python app.py
   
   ```

## Testing
- Submit a task: http://127.0.0.1:5000/
- Check status: http://127.0.0.1:5000/task_status/<job_id>
