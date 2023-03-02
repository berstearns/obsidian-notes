# implement automatic regions extraction using DiT 
## 23/01/2022 09:44
now I want to be able to send a rpost request from the react ui and validate that i', reatrieving the bounding boxes
	1. [V]fetch to 'makeurbook.com/dla-api/ping/' is working
	2. [] fetch post to 'makeurbook.com/dla-api/boundboxes/' 
		is the api receiving the request ?
			how do i check if the api is receiving it ? LOOOGS
			checking in nginx logs nginx is not getting the post request, it probably is a cors problem 
			check flask cors config
		is the UI receiving the result ?
## 23/01/2022 09:28
[V]I manage with celso help to setup nginx redirecting books-api uri requests to books-api and dla-api uri requests do the dla-api
[V]the immediate step is to rebuild the image to fix the ports accordingly and to set the docker image to run the gunicorn on start as CMD
then just rerun the docker stack to test it
