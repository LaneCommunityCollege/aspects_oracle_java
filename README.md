#aspects_oracle_java

Install or upgrade to the java version of your choice. Just use the correct tar.gz file.

##Requirements

Set ```hash_behaviour=merge``` in your ansible.cfg file.

You need to download the correct java jre from Oracle, then save it into the files/downloads directory.

##Role Variables
###aspects_oracle_java_unarchive
Whether or not to decompress the tar.gz file.
Values: true|false
Default: false

You must set this to true for your initial run with this role. Try the ```--extra-vars="aspects_oracle_java_unarchive=true"``` flag on the command line. If you leave it set as true in your playbooks, you will end up uploading and unarchiving the tar file every time you run the playbook.

###aspects_oracle_java_set_as_default
Run alternative commands to set the default java to what you have configured. 
Values: true|false
Default: true

Change this if you are uploading a java version that you don't want to be used by default, or you just don't want to run the commands every time this role gets called.

###aspects_oracle_java_bin_filename
The filename of the java download. Used in the unarchive task.
Values: Any file name that points to the tar file downloaded from logstash.
Default: server-jre-7u60-linux-x64.tar.gz

###aspects_oracle_java_bin_dirname
The directory name that the unarchive task creates.
Values: Whatever the logstash unarchive task creates. Uncompress the file locally to find out.
Default: jdk1.7.0_60

###aspects_oracle_java_bin_list
A list of binary files in {{ aspects_oracle_java_bin_dirname }}/bin. See defaults/main.yml for default values. Compare that list with what is extract from whatever tar you choose to use. If it's different, override it.

##License

MIT
