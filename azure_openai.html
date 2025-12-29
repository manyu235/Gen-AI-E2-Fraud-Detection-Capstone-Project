import os
from dotenv import load_dotenv
import msal
import httpx
import requests
import urllib3
urllib3.disable_warnings(urllib3.exceptions.InsecureRequestWarning)



# Load environment variables from .env file
load_dotenv()

ACCESS_TOKEN_URL = os.getenv("ACCESS_TOKEN_URL")
CLIENT_ID = os.getenv("CLIENT_ID")
CLIENT_SECRET = os.getenv("CLIENT_SECRET")
SCOPE = os.getenv("SCOPE")
GRANT_TYPE = os.getenv("GRANT_TYPE")
AZURE_OPENAI_ENDPOINT=os.getenv("AZURE_OPENAI_ENDPOINT")

def get_azure_access_token():
    print("in the get_azure_access_token")
    # === Required inputs ===
    access_token_url = ACCESS_TOKEN_URL.strip() if ACCESS_TOKEN_URL else None
    client_id = CLIENT_ID.strip() if CLIENT_ID else None
    client_secret = CLIENT_SECRET.strip() if CLIENT_SECRET else None
    scope = SCOPE.strip() if SCOPE else None
    grant_type = GRANT_TYPE.strip() if GRANT_TYPE else None
    print("grant_type",grant_type)
    data = {
        'grant_type': grant_type,
        'client_id': client_id,
        'client_secret': client_secret,
        'scope': scope
    }
    headers = {
        'Content-Type': 'application/x-www-form-urlencoded'
    }
    response = requests.post(access_token_url, data=data, headers=headers, verify=False)

    if response.status_code == 200:
        token_data = response.json()
        #print("Access Token:", token_data['access_token'])
        return token_data['access_token']
    else:
        print("Failed to get token")
        print("Status code:", response.status_code)
        print("Response:", response.text)

async def azure_chat(prompt: str) -> str:
    print("In the azure_openai `azure_chat` method")

    token = get_azure_access_token()  # Make sure this is sync or async accordingly

    url = AZURE_OPENAI_ENDPOINT
    headers = {
        "Authorization": f"Bearer {token}",
        "Content-Type": "application/json"
    }

    print("Prompt is:", prompt)

    body = {
        "messages": [
            {"role": "system", "content": "You are a helpful assistant."},
            {"role": "user", "content": prompt}
        ],
        "max_tokens": 1000,
        "temperature": 0.3
    }

    async with httpx.AsyncClient(verify=False) as client:
        try:
            response = await client.post(url, headers=headers, json=body)
            response.raise_for_status()
            result = response.json()
            print(result.get("choices", [{}])[0].get("message", {}).get("content", ""))
            return result.get("choices", [{}])[0].get("message", {}).get("content", "")
        except httpx.HTTPError as e:
            print("Error calling Azure OpenAI:", e)
            return "An error occurred while contacting Azure OpenAI."
