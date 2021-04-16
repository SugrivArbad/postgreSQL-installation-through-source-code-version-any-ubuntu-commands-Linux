# postgreSQL-installation-through-source-code-version-any-ubuntu-commands-Linux

TITLE :
	postgreSQL installation | through source code | version any | ubuntu commands | Linux

DESCRIPTION :

Install postgreSQL through source code
It's applicable for any version of postgreSQL
Here I have given all commands for LINUX users
I have used UBUNTU 18.04 but still applicable for all versions
Also given solution for resolving errors
For any queries mail me  arbadsugriv@gmail.com

youtube video
https://youtu.be/W-n7RGZHAOE

postgres installation :
        cd postgres_source_code
        ./configure
        make
        su
        make install
        adduser user_name         /* for installing for new user
        mkdir  /home/user_name/user_cluster/
        chown user_name  /home/user_name/user_cluster/
        su  user_name
        cd ~
        vim .bashrc               /* if you are not familiar with vim editor you also can use your editor to make changes */
                #add below 3 lines at end of the file
                        export LD_LIBRARY_PATH=/usr/local/pgsql/lib
                        export PATH=/usr/local/pgsql/bin:$PATH
                        export PGDATA=$HOME/sugriv_cluster/
        source .bashrc
        initdb -D user_cluster/
        postgres -D user_cluster/ > logout 2>&1 &
        pg_ctl status
        createdb db_name
        psql  -d  db_name             /* you are inside database db_name

	/* Solution for resolving errors if occurs */
        ERROR : psql 5432 port not available
        SOLVE : pg_ctl restart

        ERROR : postmaster.id not availble
        SOLVE : 1] remove all lock files mentioned in errors
                            rm file_path
                        2] pg_ctl restart
