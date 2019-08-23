# Normalized difference moisture index

<a href="#" id='togglescript'>Show</a> script or [download](script.js){:target="_blank"} it.
<div id='script_view' style="display:none">
{% highlight javascript %}
      {% include_relative script.js %}
{% endhighlight %}
</div>

## Evaluate and visualize
 - [Sentinel Playground](https://apps.sentinel-hub.com/sentinel-playground/?source=S2&lat=43.514198796857976&lng=16.601028442382812&zoom=11&preset=CUSTOM&layers=B01,B02,B03&maxcc=20&gain=1.0&gamma=1.0&time=2019-02-01%7C2019-08-23&atmFilter=&showDates=false&evalscript=Ly8KLy8gTm9ybWFsaXplZCBEaWZmZXJlbmNlIDgyMC8xNjAwIE5vcm1hbGl6ZWQgRGlmZmVyZW5jZSBNb2lzdHVyZSBJbmRleCAoYWJicnYuIE5ETUkpCi8vCi8vIEdlbmVyYWwgZm9ybXVsYTogKDgyMG5tIC0gMTYwMG5tKSAvICg4MjBubSArIDE2MDBubSkKLy8KLy8gVVJMIGh0dHBzOi8vd3d3LmluZGV4ZGF0YWJhc2UuZGUvZGIvc2ktc2luZ2xlLnBocD9zZW5zb3JfaWQ9OTYmcnNpbmRleF9pZD01NgovLwoKbGV0IGluZGV4ID0gKEIwOCAtIEIxMSkgLyAoQjA4ICsgQjExKTsKbGV0IG1pbiA9IC0wLjg5OwpsZXQgbWF4ID0gMC44OTsKbGV0IHplcm8gPSAwLjA7CgovLyBjb2xvckJsZW5kIHdpbGwgcmV0dXJuIGEgY29sb3Igd2hlbiB0aGUgaW5kZXggaXMgYmV0d2VlbiBtaW4gYW5kIG1heCBhbmQgd2hpdGUgd2hlbiBpdCBpcyBsZXNzIHRoYW4gbWluLgovLyBUbyBzZWUgYmxhY2sgd2hlbiBpdCBpcyBtb3JlIHRoYW4gbWF4LCB1bmNvbW1lbnQgdGhlIGxhc3QgbGluZSBvZiBjb2xvckJsZW5kLgovLyBUaGUgbWluL21heCB2YWx1ZXMgd2VyZSBjb21wdXRlZCBhdXRvbWF0aWNhbGx5IGFuZCBtYXkgYmUgcG9vcmx5IHNwZWNpZmllZCwgZmVlbCBmcmVlIHRvIGNoYW5nZSB0aGVtIHRvIHR3ZWFrIHRoZSBkaXNwbGF5ZWQgcmFuZ2UuCi8vIFRoaXMgaW5kZXggY3Jvc3NlcyB6ZXJvLCBzbyBhIGRpdmVyZ2luZyBjb2xvciBtYXAgaXMgdXNlZC4gVG8gdHdlYWsgdGhlIHZhbHVlIG9mIHRoZSBicmVhayBpbiB0aGUgY29sb3IgbWFwLCBjaGFuZ2UgdGhlIHZhcmlhYmxlICd6ZXJvJy4KCmxldCB1bmRlcmZsb3dfY29sb3IgPSBbMSwgMSwgMV07CmxldCBsb3dfY29sb3IgPSBbMjA4LzI1NSwgODgvMjU1LCAxMjYvMjU1XTsKbGV0IGhpZ2hfY29sb3IgPSBbMjQxLzI1NSwgMjM0LzI1NSwgMjAwLzI1NV07CmxldCB6ZXJvX2NvbG9yID0gWzAsIDE0Ny8yNTUsIDE0Ni8yNTVdOwpsZXQgb3ZlcmZsb3dfY29sb3IgPSBbMCwgMCwgMF07CgpyZXR1cm4gY29sb3JCbGVuZChpbmRleCwgW21pbiwgbWluLCB6ZXJvLCBtYXhdLApbCgl1bmRlcmZsb3dfY29sb3IsCglsb3dfY29sb3IsCgl6ZXJvX2NvbG9yLCAvLyBkaXZlcmdlbnQgc3RlcCBhdCB6ZXJvCgloaWdoX2NvbG9yLAoJLy9vdmVyZmxvd19jb2xvciAvLyB1bmNvbW1lbnQgdG8gc2VlIG92ZXJmbG93cwpdKTsNCg%3D%3D&evalscripturl=https://raw.githubusercontent.com/sentinel-hub/custom-scripts/master/sentinel-2/indexdb/id_56.js){:target="_blank"}
 

## General description

Normalized Differenced Moisture Index used top determine if irrigation has taken place in areas where there has been no recent rain events. If NDMI is above 0, depending on the land and canopy cover, it is possible to determine if irrigation has taken place. Using this Index with Sentinel-2 bands 08 and 11 it is possible to identify this with 10 m. resolution. The logic used for this was taken from this article from [This article.](https://www.agricolus.com/en/indici-vegetazione-ndvi-ndmi-istruzioni-luso/)

By following that logic, and knowing land uses within an area as well as climatic conditions, it was possible to difference between productive and non-productive areas first, and then see how this Index is reflected in different agricultural parcels. Some of them showed high levels of NDMI in summer moths after several weeks without rain. The only source of irrigation water was from an aquifer below. Some of the parcels do have water concessions and others not, so it was possible to identify illegal water use. On the other hand, it was possible to identify if a parcel in which the crop is known (e.g. citrus crops) irrigation is being effective or not during the crucial growing season in summer, as it is possible to find if some parts of the farm are being under or over irrigated. 


## Color legend
<table>
  <tr>
    <th>NDMI range</th>
    <th>Interpretation</th>
    <th>Color</th>
  </tr>
  <tr>
    <td>NDMI &lt; -1 to -0.8</td>
    <td>Bare soil</td>
    <td style="background-color: #000000;"></td>
  </tr>
  <tr>
    <td>NDMI &lt; -0.8 to -0.6</td>
    <td>Almost absent canopy cover</td>
    <td style="background-color: #000000;"></td>
  </tr>
  <tr>
    <td>NDMI &lt; -0.6 to -0.4</td>
    <td>Very low canopy cover</td>
    <td style="background-color: #000000;"></td>
  </tr>
  <tr>
    <td>NDMI &lt; -0.4 to -0.2</td>
    <td>Low canopy cover, dry or very low canopy cover, wet</td>
    <td style="background-color: #000000;"></td>
  </tr>
  <tr>
    <td>NDMI &lt; -0.2 to 0</td>
    <td>Mid-low canopy cover, high water stress or low canopy cover, low water stress</td>
    <td style="background-color: #000000;"></td>
  </tr>
  <tr>
    <td>NDMI &lt; 0 to 0.2</td>
    <td>Average canopy cover, high water stress or mid-low canopy cover, low water stress</td>
    <td style="background-color: #000000;"></td>
  </tr>
  <tr>
    <td>NDMI &lt; 0.2 to 0.4</td>
    <td>Mid-high canopy cover, high water stress or average canopy cover, low water stress</td>
    <td style="background-color: #000000;"></td>
  </tr>
  <tr>
    <td>NDMI &lt; 0.4 to 0.6</td>
    <td>High canopy cover, no water stress</td>
    <td style="background-color: #000000;"></td>
  </tr>
  <tr>
    <td>NDMI &lt; 0.6 to 0.8</td>
    <td>Very high canopy cover, no water stress</td>
    <td style="background-color: #000000;"></td>
  </tr>
  <tr>
    <td>NDMI &lt; 0.8 to 1</td>
    <td>Total canopy cover, no water stress/ waterlogging</td>
    <td style="background-color: #000000;"></td>
  </tr>
 
</table>

## References
 [1] Agricolus, [NDVI and NDMI - Instructions for use
](https://www.agricolus.com/en/indici-vegetazione-ndvi-ndmi-istruzioni-luso/). Accessed on June 1st, 2019.
