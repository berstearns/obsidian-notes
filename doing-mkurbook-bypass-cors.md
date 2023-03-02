# bypassing cors of the dla-api

## why books-api is not having cors problem ?
	didn't find why
## added flask-cors to the dla-api
	## an empty body post request is being received
	## the async request in the react app is not
	## i got stuck because i didn't pass the event handler func down the components hole
	## communication with post request is working but image_b64 format is not working properly
	## the problem was not hte format i was testing with a dummy function that was not returning a proper json	
	## need to print the input / output of the dla-api endpoint

## docker stack is dying
	is it related to the printing changes in the dla-api ? i dont think so
