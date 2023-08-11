# 3CX To Pipedrive Integration
3CX-Pipedrive Integration

This is an integration of your 3CX PBX with Pipedrive.
Here are the supported features

- Find contact for incoming call from Pipedrive
- Add contacts to 3cx from Pipedrive based on incoming calls
- Call journaling ( Includes adding an activity to pipedrive )
- Call journaling looks for both leads and deals and adds calls to either when found.
- Call journaling adds details to multiple contacts if the numbers belong to multiple people

 # How to install
 1. Go to 3CX console > Settings > CRM
 2. Server Side > +Add > Upload the pipedrive.xml file from this repository.
 3. Add the API key ( Found in Pipedrive > User > Pesonal Preferences > API ) & the domain part (Usually the domain once you log into pipedrive - https://example.pipedrive.com).
 4. Check if you need contact creation & Call journaling.
 5. Go to Pipedrive and create a contract for each of your user that will use the system. Make sure their email on pipedrive matches the email on 3CX. In the phone number field enter AgentExtension-XX where XX represents the users extension in 3cx.

# Logic for call journaling
 <img width="140" alt="image" src="https://github.com/modestcrab/3CX-Pipedrive-Integration/assets/32093963/e82b6c86-adbb-43ac-8c90-963d62274906">

The call journaling works based on the following scenarios
- When a call comes in 3cx, the integration sends pipedrive a request based on the agents extension. It looks for AgentExtension-XX where XX represents the users extension in 3cx. It finds the user based on the match.
- We then retreive the users ID.
- Next we search the phone number that called into the 3CX and find the relevant person ID in pipedrive.
- Once we have both the caller and the user who answered, we search all deals && leads to find all relevant records
- We finally add the activity based on those scenarios
    
 
