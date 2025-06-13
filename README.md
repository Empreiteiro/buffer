# Buffer

Buffer is an advanced platform to receive, store, forward, and schedule messages with highly configurable rules. It features a modern web interface for managing buffers, schedules, and forwarding configurations.

## Main Features

- **Receive messages via Webhook**
- **Configurable buffers**: define key field, max size, max time, and reset timer on each message (debounce)
- **Advanced forwarding**: multiple destinations, HTTP methods, custom headers, templates, and custom fields
- **Schedules**: schedule HTTP requests with cron, custom methods, headers, and body
- **Detailed history**: track received and forwarded messages, including status
- **Modern web interface**: visual management of buffers, schedules, and logs

## Installation

1. Clone the repository:
```bash
git clone https://github.com/Empreiteiro/buffer.git
cd buffer
```

2. Create and activate a virtual environment:
```bash
python -m venv .venv
# Linux/Mac:
source .venv/bin/activate
# Windows:
.venv\Scripts\activate
```

3. Install dependencies:
```bash
pip install -e .
```

## Usage

1. Start the backend:
```bash
buffer run
```

2. Start the frontend:
```bash
cd buffer/frontend
npm install
npm start
```

3. Access the web interface at `http://localhost:3000`

## Webhook

Send messages to the webhook endpoint:
```bash
curl -X POST http://localhost:5000/api/webhook \
  -H "Content-Type: application/json" \
  -d '{"message": "Hello, World!", "phone_number": "+5511999999999"}'
```

## Buffer Configuration
- **Name**: buffer identification
- **Key field**: field to group messages (e.g., phone_number)
- **Max size**: maximum number of messages in the buffer
- **Max time**: maximum time (in seconds) to keep messages in the buffer
- **Reset timer on each message**: restarts the timer with every new message (debounce)

## Forwarding Configuration
- **Name**: identification
- **Associated buffer**: select the source buffer
- **URL**: destination
- **Method**: POST, PUT, PATCH, DELETE, GET
- **Headers**: custom headers (JSON)
- **Custom fields**: select which fields to send
- **Template**: customize the request body

## Schedules
- **Name and description**
- **Destination URL**
- **Cron expression**: set the periodicity
- **Method**: GET, POST, PUT, DELETE
- **Headers and Body**: customizable (JSON)

## History and Logs
- View received and forwarded messages, status, and errors
- Filter by buffer, forwarding, and period

## Technologies

### Backend
- Flask
- SQLite
- APScheduler

### Frontend
- React
- React Router
- Modern CSS

## License

MIT License. See the LICENSE file for details.
