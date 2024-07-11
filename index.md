---
layout: workshop      # DON'T CHANGE THIS.
# More detailed instructions (including how to fill these variables for an
# online workshop) are available at
# https://carpentries.github.io/workshop-template/customization/index.html
venue: "ASDAF Workshop Curtin"        # brief name of the institution that hosts the workshop without address (e.g., "Euphoric State University")
address: "Curtin University, Kent St Bentley, Building 501, Room 117"     # full street address of workshop (e.g., "Room A, 123 Forth Street, Blimingen, Euphoria"), videoconferencing URL, or 'online'
country: "au"      # lowercase two-letter ISO country code such as "fr" (see https://en.wikipedia.org/wiki/ISO_3166-1#Current_codes) for the institution that hosts the workshop
language: "en"     # lowercase two-letter ISO language code such as "fr" (see https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes) for the workshop
latitude: "-32.008444444"        # decimal latitude of workshop venue (use https://www.latlong.net/)
longitude: "115.893027778"       # decimal longitude of the workshop venue (use https://www.latlong.net)
humandate: "June 14th 2024"    # human-readable dates for the workshop (e.g., "Feb 17-18, 2020")
humantime: "9:00 am - 5:00pm"    # human-readable times for the workshop e.g., "9:00 am - 4:30 pm CEST (7:00 am - 2:30 pm UTC)"
startdate: 2024-06-14      # machine-readable start date for the workshop in YYYY-MM-DD format like 2015-01-01
enddate: 2024-06-14        # machine-readable end date for the workshop in YYYY-MM-DD format like 2015-01-02
instructor: ["Leigh Tyers"] # boxed, comma-separated list of instructors' names as strings, like ["Kay McNulty", "Betty Jennings", "Betty Snyder"]
helper: ["Calvin Pang"]     # boxed, comma-separated list of helpers' names, like ["Marlyn Wescoff", "Fran Bilas", "Ruth Lichterman"]
email: ["leigh.tyers@curtin.edu.au",]    # boxed, comma-separated list of contact email addresses for the host, lead instructor, or whoever else is handling questions, like ["marlyn.wescoff@example.org", "fran.bilas@example.org", "ruth.lichterman@example.org"]
collaborative_notes:  # optional: URL for the workshop collaborative notes, e.g. an Etherpad or Google Docs document (e.g., https://pad.carpentries.org/2015-01-01-euphoria)
eventbrite:           # optional: alphanumeric key for Eventbrite registration, e.g., "1234567890AB" (if Eventbrite is being used)
---









<h2 id="general">General Information</h2>

{% comment %}
INTRODUCTION

Edit the general explanatory paragraph below if you want to change
the pitch.
{% endcomment %}

      
<p>
<b>Note:</b> This workshop is historical, and the website is left up as useful information for the attendees.
</p>

<p>
This workshop, provided by <strong><a href="https://asdaf.space/">The Australian Space Data Analysis Facility (ASDAF)</a></strong>
      in partnership with <strong><a href="https://www.landgate.wa.gov.au/">Landgate</a></strong>,
      is intended to be a hands-on, foundational lesson in the acquistion, use, and interrogation of remote sensing data
      products using python.
    <p>
      After this workshop, you will be able to:
    </p>
    <p align="center">
      <em>
        <ul>
          <li> Query and download satellite data from a web-server programmatically using python </li>
          <li> Read and visualise satellite data using python</li>
          <li> Load and create vector data in python </li>
          <li> Use Vector data to mask satellite data in python </li>
          <li> Create derivative products (NDVI, etc) using python </li>
          <li> Create a data pipeline for processing satellite data automatically </li>
          <li> (Time-permitting) Create efficient custom raster caclulations using numba</li>
          <li> (Time-permitting) Parallelise satellite data calculations using python</li>
        </ul>
      </em>
    </p>



<p id="who"><br>
  <strong>Who:</strong><br>
  This workshop assumes you have at least basic knowledge of Python and some experience with GIS data/software (e.g.
  QGIS) <br>
  <strong>
    You don't need to have any previous knowledge of the tools
    that will be presented at the workshop.
  </strong>
</p>





{% assign begin_address = page.address | slice: 0, 4 | downcase  %}
{% if page.address == "online" %}
{% assign online = "true_private" %}
{% elsif begin_address contains "http" %}
{% assign online = "true_public" %}
{% else %}
{% assign online = "false" %}
{% endif %}
{% if page.latitude and page.longitude and online == "false" %}
<p id="where">  <br>
  <strong>Where:</strong> <br>
  {{page.address}}. 
  <br>
  Get directions with
  <a href="https://link.mazemap.com/jhhZJe45">the Curtin Campus Map</a>
  or
  <a href="https://maps.google.com/maps?q={{page.latitude}},{{page.longitude}}">Google Maps</a>.
  <br>
</p>
{% endif %}






{% if page.humandate %}
<p id="when">  <br>
  <strong>When:</strong> <br>
  {{page.humandate}}.
  {% include workshop_calendar.html %}
</p>
{% endif %}




<p id="requirements"> <br>
  <strong>Requirements:</strong> <br>
    It is preferable that participants bring a laptop with a
    Mac, Linux, or Windows operating system (not a tablet, Chromebook, etc.) that they have administrative privileges on.
  They should have a few specific software packages installed (listed on the <a href="setup">setup page</a>).  <br/> <br>

  We do however understand some people do not have administrative privileges. <br>
  <b>If you cannot get the listed software installed or don't have adminstrative privileges please follow the instructions for using an online colab instance (listed on the  <a href="setup/#online-setup">setup page</a>)</b>. <br/> <br>

  There will be an optional half hour before the workshop where we can check your installation and help you with any issues.
</p>

<p id="parking"> <br>
  <strong>Parking and Public Transport:</strong> <br>
    Parking is available throughout Curtin. We recommend you park in <a href="https://properties.curtin.edu.au/parking/zones-and-rates/">green or yellow bays</a>.  There is a car park close to building 501 that is easily accessible. You will need the <a href="https://properties.curtin.edu.au/parking/cellopark/">CellOPark</a> App to pay for parking. <b> It's recommended to install this and register on the app in advance to avoid issues on the day </b> .
    <br>
    Alternatively, Curtin is easily accessible via public transport. Please plan your journey ahead of time with google maps or transperth.
</p>


<p id="accessibility">  <br>
  <strong>Accessibility:</strong> <br>
{% if online == "false" %}
  We are committed to making this workshop 
  accessible to everybody:
</p>
<ul>
  <li>The room is wheelchair accessible.</li>
  <li>Accessible restrooms should be available.</li>
</ul>
<p>
  Materials will be provided in advance of the workshop and
  large-print handouts are available if needed by notifying the
  organizers in advance.  If there is anything we can provide to help in make learning easier for you, please get in touch (using contact details below) and we will attempt to provide it.
</p>
{% else %}
  We are dedicated to providing a positive and accessible learning environment for all. 
  We do not require participants to provide documentation of disabilities or disclose any unnecessary personal information. 
  However, we do want to help create an inclusive, accessible experience for all participants. 
  We encourage you to share any information that would be helpful to make the workshop accessible.
  To request an accommodation for this workshop, please fill out the 
  <a href="https://carpentries.typeform.com/to/B2OSYaD0">accommodation request form</a>.
  If you have questions or need assistance with the accommodation form please <a href="mailto:team@carpentries.org">email us</a>.
</p>
{% endif %}

{% comment %}
CONTACT EMAIL ADDRESS

Display the contact email address set in the configuration file.
{% endcomment %}
<p id="contact"><br>
  <strong>Contact:</strong><br>
  Please email
  {% if page.email %}
  {% for email in page.email %}
  {% if forloop.last and page.email.size > 1 %}
  or
  {% else %}
  {% unless forloop.first %}
  ,
  {% endunless %}
  {% endif %}
  <a href='mailto:{{email}}'>{{email}}</a>
  {% endfor %}
  {% else %}
  to-be-announced
  {% endif %}
  for more information.
</p>


<p id="who-can-attend"><br>
    <strong>Who can attend?:</strong><br>
    This workshop is currently invitation only.
</p>

<hr/>


<h2 id="code-of-conduct">Code of Conduct</h2>

<p>
Everyone who participates in this workshop is required to conform to the <a href="CODE_OF_CONDUCT.html">Code of Conduct</a>.
</p>





<h2 id="surveys">Surveys</h2>
<p>Please be sure to complete these surveys before and after the workshop. These surveys help us both tailor the material to the current skillsets and abilities of those present, while also giving us feedback on what we did well and where we can improve.</p>
<p>Pre-workshop Survey (sent out via email)</p>
Post-workshop Survey (to be sent out after workshop)</p>


<hr/>



<h2 id="schedule">Schedule</h2>
 {% include dc/schedule.html %}
<br>


<hr/>



<h2 id="setup">Setup</h2>
<p>
  The setup instructions for this workshop
  can be found at <a href="setup">
    the setup page on this website</a>.
</p>

<p>
  To participate in a this
  workshop,
  you will need access to software as described above.
  In addition, you will need an up-to-date web browser.
</p>
<p>
  The carpentries maintain a list of common issues that occur during installation as a reference for instructors
  that may be useful on the
  <a href = "{{site.swc_github}}/workshop-template/wiki/Configuration-Problems-and-Solutions">Configuration Problems and Solutions wiki page</a>.
</p>


