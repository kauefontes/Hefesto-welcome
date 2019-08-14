let upSeconds="$(/usr/bin/cut -d. -f1 /proc/uptime)"
let secs=$((${upSeconds}%60))
let mins=$((${upSeconds}/60%60))
let hours=$((${upSeconds}/3600%24))
let days=$((${upSeconds}/86400))
UPTIME=`printf "%d days, %02dh%02dm%02ds" "$days" "$hours" "$mins" "$secs"`

# get the load averages
read one five fifteen rest < /proc/loadavg

echo "$(tput setaf 2)
					WELCOME TO HEFESBIAN!!!



                                                     `-:--.                          `date +"%A, %e %B %Y, %r"`
                                                     -:-+:--..`.``..`                `uname -srmo`$(tput setaf 1)               
                                                     -o+:``..---/+/-::                              
                                                               ./:+///-                             
                                                                -++:o-               Uptime.............: ${UPTIME}               
                                                               ./:::s                Memory.............: `cat /proc/meminfo | grep MemFree | awk {'print $2'}`kB (Free) / `cat /proc/meminfo | grep MemTotal | awk {'print $2'}`kB (Total)
                                              `..`           .:/:.-+:                Load Averages......: ${one}, ${five}, ${fifteen} (1, 5, 15 min)
                                            -////:/.       `./:o-.++`                Running Processes..: `ps ax | wc -l | tr -d " "`
                                            /+//:/o+     .-:.::+/oy.                 IP Addresses.......: `/sbin/ifconfig eth0 | /bin/grep "inet addr" | /usr/bin/cut -d ":" -f 2 | /usr/bin/cut -d " " -f 1` and `wget -q -O - http://icanhazip.com/ | tail`
                                           `o//::/oo---.//.::/:so/.                  
                                            :o+///sss-`:o::so///`                                   
                                         `.--+syooo:.``:sos:.::                                     
                                      .-/--:-:/++o:.``-so/o:-`                                      
                                     -:::.`-.``../s:-:+o../.                                        
                                     //:./+--.`--+o+++/+:-+                                         
                                   `::////+oo+///:/:-//:/+-                                         
                                   ://++.-oo++++.`:/./+/+.                                          
                                  .s:/:/-:-/+++y-./+.:+++                                           
                                 :+//-/o.`  s++s-./+-o+h`                                           
                                `+o//-:o   -o++s+-+++oso                                            
                                `o+::/+-  .:-.-:::/::://.                                           
                                .o:-/o- .::`-..`...`.-`.-....--`                                    
                               `:/.-/:`:-..-:..`.`:..`-``.../+:+`                                   
                              `//:-:-oo+-`..-.- .-:`` :..:::oo/-                                    
                               `+/::-hyo+/-.``/..``.`../o-::-+/                                     
                                `..-o/+////:::/-`....-/::::-/-::                                    
                                  .o-::./://----.-:::/+//+o++/./-`                                  
                                 .//./-:o///:-::/+oo++++sso/:-/-:/                                  
                                 +:/::/:+//osssyyyhhysys-`-/:-/-:/.                                 
                               `-o++++ooooossosyyyyssoo+    -:/:-/+-`                               
                              ./+/./s:-::/ss/oosossoo+//.`   `/o:.:+:.                              
                             .:o.-+-/  -:+ho+oo++ddhs:::-::``  :-:-.++`                             
                             //+.o+:.`.++o+++////+/::-:::-:-/` -:/+.+:/                             
                             /+/++--/+//+oo//:/+++.:-::-.-+-:-- .:++//o                             
                            `+o++-`++++:/::-:++-..-:/:.-./:-../-` -o+++.                            
                            :ooo:`+o:/::+.-:-//. ``-/:--:o-.`.:/-.`.o+:s`                          
                           .:.:o`+/+:-..-/-.::/:` `-/--.:/.-.`./.::`o/.:+`                        
                          :+-.:s/+::/-`.-:/:::-/:.:/:.`.--``::-+::/.s+//+s.                    
                        `+ysoo:o--:`:``-:--/:::/-:/::---:.. -:-:+---++o+ss+`                   


$(tput sgr0)"
