# The-Outfit-Analyst-ElasticSearch-Hackathon
using elasticsearch and AWS Models to reccomend your own wardobe outfits based on an a celebrity image you pick.

This project won Most Innovative award during the Forge the Future Hackathon organised by Elastic — The Search AI Company and Amazon Web Services.  
[Forge The Future Cert.pdf](https://github.com/user-attachments/files/19066764/Forge.The.Future.Cert.pdf)  


Users are able to upload their wardobe outfits on Airtable easily along with a short description. Due to its user friendly-ness and identifiable UI, Airtable was chosen.
![airtable 2](https://github.com/user-attachments/assets/968c06b3-595b-4128-99cc-d700cd439cf3)

![Airtable 1](https://github.com/user-attachments/assets/532b8f21-490b-4055-8938-bc63339ca9e1)  

Using Airtable's python API library, we pull the entirety of Airtable's data and index it into ElasticSearch.  
We then set up a Bedrock Client using AWS Services. We used Anthropic's Claude 3.5 Sonnet Model to extract key phrases/ key words from the uploaded Celebrity image from the User.  
Claude Sonnet's response is converted from JSON String which is then inputted into ElasticSearch function.  
The elastic search function that takes in the JSON string and creates a custom a JSON query which then searches in the Elastic_Client to return wardrobe items (Currently in the form of a Python Dictionary with description and links to be cleaned up if the project mvoes forward)
