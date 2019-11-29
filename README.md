## FastLane Tips:

### Lane Flow Control

lane :my_lane do
  ...
  
  if some_variable == true
    -do some stuff
    else
      next -do something else
    end
  do more stuff
  
  ...

end

### Call additional lanes from another lane

lane :sync_all_development do
  sync_device_info
  
  match type: "development"
end

### Jenkins Pipeline Sample Jenkins Script

This GitHub repository contains one single Jenkinsfile that is used to demonstrate a simple Jenkins pipeline concept.

The repository was created to support the article written for [Opensource.com](https://opensource.com)

