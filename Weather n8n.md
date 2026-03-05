# Weather Update Workflow in n8n

This is a simple weather automation I made in n8n.
It fetches weather data using a free API key and sends regular updates.


## Step 1: Create the trigger

Add a trigger node (like Schedule Trigger) to decide when the workflow should run.

Example: run every morning at 7:00 AM.

<img width="1363" height="571" alt="Step 1 - trigger setup" src="https://github.com/user-attachments/assets/1ee8ab20-324a-450f-9cee-db79848e9062" />

## Step 2: Get weather data from API
-- a sidenote, the weather API key usually takes a lot of time to activate for 20 min to 20 hours, so keep that in mind while trying this out. 
Add an HTTP Request node and call your weather API endpoint.

- Method: `GET`
- Add your city/location in query params.
- Add your API key in query params or headers (based on provider docs).

<img width="1363" height="644" alt="Step 2 - API request node" src="https://github.com/user-attachments/assets/2b53b6ce-7ce5-402b-85e4-9669c535849a" />

Get your free API key by signing up and logging in to the weather API provider:

<img width="1365" height="729" alt="Get free API key" src="https://github.com/user-attachments/assets/cc1d4c65-a365-4437-b952-3745c65ce8f1" />

## Step 3: Format and send the result

Use a Set/Code node (or equivalent) to format the weather message in a clean way.

Then connect it to your output channel (Email, Telegram, Slack, etc.).

<img width="1344" height="570" alt="Step 3 - formatting and send" src="https://github.com/user-attachments/assets/0e6a91ee-f007-4c4b-90fd-fea4df57e369" />

## Final workflow

After connecting all nodes, test once and activate the workflow.

<img width="1165" height="578" alt="Final weather workflow" src="https://github.com/user-attachments/assets/231f7174-017d-4be3-b302-a3644f72e136" />

## Quick tips

- If API fails, first check API key and city name.
- Keep retry/error handling in workflow for reliability.
- Start with manual test, then activate schedule.
