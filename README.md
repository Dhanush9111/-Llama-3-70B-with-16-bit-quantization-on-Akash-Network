# Deploying Llama-3-70B-with-16-bit-quantization-on-Akash-Network

  **This guide provides detailed steps to deploy the Llama 3 70B model with 16-bit quantization on the Akash Network.**
  #
  - Need Access to the models on hugging face by applying for the authorizationn
  - Create an access token after getting the access for meta-Llama model
  - You need a wallet with AKT tokens in the wallet 
  - Use keplr wallet
  - Go to https://console.akash.network/ and login with the wallet
  - Click on "Deploy"
  - Select "Build Your Template" and click YAML tab and paste the deployment file [from](https://github.com/Dhanush9111/Llama-3-70B-with-16-bit-quantization-on-Akash-Network/blob/main/this.yaml)
  -  In the deployment file, replace "HF_TOKEN=hf_yourtoken" with your Hugghing face token , This will allow you to access the Llama 3 models
  -  Click "Create Deployment" and wait for bids from providers and choose a provider that meets your requirements and create a lease
  -  Then, wait for the deployment to boot up - this may take some time because the model is 130GB
  -  Once the deployment is up and running, check the logs for a  throughput message every 10 seconds. This indicates that the deployment  has successfully started
  -  You can now access your Llama 3 70B endpoint  by clicking on "Forwarded Port" on the "Leases" tab.
  -  You need to use the URL provided by provider after deployment to access the model
  -  Use the api code below in shell

 ```
      curl http://<your-service-url>/v1/chat/completions \
      -H "Content-Type: application/json" \
      -d '{
       "model": "meta-llama/Meta-Llama-3-70B-Instruct",
      "messages": [
    {"role": "system", "content": "You are better than siri."},
    {"role": "user", "content": "Tell me a fun fact about ancient martians."}
  ]
}'
```
- Replace **<your-service-url>** with the URL from leases tab.
- Chat with the Llama and change the user prompt to your liking.


    


