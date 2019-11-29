# FastLane Tips:

##### Return Lane Values


###### Using return lane values


##### Lane Variables


##### Exiting a lane early with "next"


##### Lane Flow Control



##### Call additional lanes from another lane

lane :sync_all_development do
  sync_device_info
  
  match type: "development"
end

##### Jenkins Pipeline Sample Jenkins Script

This GitHub repository contains one single Jenkinsfile that is used to demonstrate a simple Jenkins pipeline concept.

The repository was created to support the article written for [Opensource.com](https://opensource.com)

