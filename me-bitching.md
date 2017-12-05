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



## Dates on articles

The older I get, the older the internet gets, the more I miss dates on articles.
I need a date to put information into context.
As we all learn on a time axis our learnings derive from knowledge of the past.
When searching and evaluating new knowledge in the internet aka self educating I want a fast idea of what is "the state of art" right now. 



## Angular2 on Ubuntu

_...and the whole node universe sucks!_

- there is a difference bwtween node and nodes terminal commands.

- they could both yield to a nodejs but have different versions wehen trying ````node -v```` or ````nodejs -v````

  there could be different version when executing as root, as sudo, or as user.

- npm install fails to access, download, read some artefacts but on e.g. macos it just works.

  ​