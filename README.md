# NAME

ftrestd - server communicating with client using HTTP

ftrest - client communicating with server using HTTP


# SYNOPSIS

ftrestd [-r ROOT-FOLDER] [-p PORT]

ftrest COMMAND REMOTE-PATH [LOCAL-PATH]


# DESCRIPTION

**ftrest/ftrestd** is a client/server application for transferring files using RESTful API and HTTP. Communication is implemented using BSD sockets.  
REST interface is implemented for methods PUT, GET and DELETE.
The HTTP codes implemented for server response are:  
	* 200 OK - request was carried out successfully  
	* 400 Not Found - file/folder requested does not exist on the server  
	* 404 Bad Request - requested resource is of different type than specified  
	* 409 Conflict - requested modification conflicts with current state of resource  
For full request/response headers see **EXAMPLES**.

The server, **ftrestd**, uses its current working directory as root folder, unless specified with option **-r**. Server implicitly runs on port 6677. To change the port, the **-p** option can be used. 

The command required for client, **ftrest** can be one of following:  
	* **put** - uploads file specified with LOCAL-PATH to the server
	* **mkd** - creates new directory on the server
	* **get** - downloads a file from the server
	* **lst** - lists contents of a folder on the server
	* **del** - removes file on the server
	* **rmd** - removes directory on the server
**REMOTE-PATH** must include specification of protocol used, name or address of the server, port number and path relative to the root folder on the server (see EXAMPLES).
**LOCAL-PATH** must be specified for **put** and is optional for **get**, it is not used with other commands.

# OPTIONS
