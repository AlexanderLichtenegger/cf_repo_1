#print("linkCounter python")

import re
import urllib.request as URL
from urllib.error import URLError
'''
Reads from a valid URL and returns the response body
'''
def readFromURL(validURL):
    f = URL.urlopen(validURL)
    html = f.read()
    try:
        return html.decode('utf-8')
    except UnicodeDecodeError:
        return html.decode('iso-8859-1')

def extractLinks(content):
    regex = r"""<a\s+(?:\S+\s+)*?href\s*?=\s*?(["'])(\S+?)\1"""
#    return [m[1] for m in re.findall(regex, content)]
    return [m[1] for m in re.findall(regex, content)]

url="http://www.segof.org"

#try:    
content = readFromURL(url)
print(content)
links = extractLinks(content)
for link in links: print(link)
print("There are {} links on {}".format(len(links),url))
#except ...
