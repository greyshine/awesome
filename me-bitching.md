# Me bitching

_Well, there are things that are just annoying when working with computers._  
_Do not feel offended but feel free if you have a handsome nice hunt to make my life better._  
_Do not contact if you just wanna tell how cool and perfect you are and that I just did not understand the issue due to my dumbness._  
_TQ_



## Writing multiline unix commands sucks

_2017-10-27_

The occuring errors just do not tell the issue whats going wrong.

E.g.

````shell
docker run --name somename \ 
	-e PGDATA="/Users/johndoe/docker/postgres-local/psql-data" \ 
	-e POSTGRES_USER=postgres \
	-e POSTGRES_PASSWORD=postgres \ 
	-v "/Users/johndoe/docker/postgres-local/psql-data:/var/lib/postgresql/data" \ 
	-p 5500:5432 \ 
	-d some/image
````

You need/must/ought/have to have a space after the **\\**, don't you?

And there is other issues, isn't there?