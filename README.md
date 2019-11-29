# FastLane Tips:

##### Return Lane Values
Upload image

###### Using return lane values
Upload image

##### Lane Variables
Upload image

##### Exiting a lane early with "next"
upload image

##### Lane Flow Control
Upload image


##### Call additional lanes from another lane

lane :sync_all_development do
  sync_device_info
  
  match type: "development"
end

##### Jenkins Pipeline Sample Jenkins Script

This GitHub repository contains one single Jenkinsfile that is used to demonstrate a simple Jenkins pipeline concept.

The repository was created to support the article written for [Opensource.com](https://opensource.com)

