A parser to parse URL string representation into components and re-create the URL string back from components. Modeled after the python urlparse library. A URL can be of the form:
````
scheme://netloc/path;parameters?query#fragment
````

URLComponents
-------------
The parsed URL components are stored in an instance of URLComponents. 

Component fields and accessor methods:
*   **scheme** : Member variable
*   **netloc** : Member variable
*   **url** : Member variable
*   **params** : Member variable
*   **query** : Member variable
*   **fragment** : Member variable
*   **username(u::URLComponents)** : Extracts username from the netloc field. Returns a string if present or nothing otherwise.
*   **password(u::URLComponents)** : Extracts password from the netloc field. Returns a string if present or nothing otherwise.
*   **hostname(u::URLComponents)** : Extracts hostname from the netloc field. Returns a string if present or nothing otherwise.
*   **port(u::URLComponents)** : Extracts port from the netloc field. Returns an int if present or nothing otherwise.


APIs
----
<dl>
    <dt>urlparse(url::String)</dt>
    <dd>Parse a URL into 6 components: <scheme>://<netloc>/<path>;<params>?<query>#<fragment>. Returns an instance of URLComponents.</dd>
    <dt>urlunparse(u::URLComponents)</dt>
    <dd>Join back 6 components of the URL back to recreate a URL string.</dd>
    <dt>urldefrag(url::String)</dt>
    <dd>Removes any existing fragment from URL. Returns a tuple of the defragmented URL and the fragment (empty string if none were there).</dd>
</dl>


TODO
----
*   parse\_query\_string: to create a list/dict of name-value pairs
*   urljoin: to overlay a relative url on a base url 
*   is\_valid: validate URL string to be conforming to scheme rules

