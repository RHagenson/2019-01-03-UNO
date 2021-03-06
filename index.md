---
layout: workshop      # DON'T CHANGE THIS.
carpentry: "dc"    # what kind of Carpentry (must be either "lc" or "dc" or "swc")
venue: "University of Nebraska at Omaha"        # brief name of host site without address (e.g., "Euphoric State University")
address: "Peter Kiewit Institute - Room 158, 1110 S 67th St, Omaha, NE 68182"      # full street address of workshop (e.g., "Room A, 123 Forth Street, Blimingen, Euphoria")
country: "us"      # lowercase two-letter ISO country code such as "fr" (see https://en.wikipedia.org/wiki/ISO_3166-1)
language: "en"     # lowercase two-letter ISO language code such as "fr" (see https://en.wikipedia.org/wiki/ISO_639-1)
latlng: "41.247015, -96.016604"       # decimal latitude and longitude of workshop venue (e.g., "41.7901128,-87.6007318" - use https://www.latlong.net/)
humandate: "Jan 3-4, 2019"    # human-readable dates for the workshop (e.g., "Feb 17-18, 2020")
humantime: "9:00 am - 4:30 pm"    # human-readable times for the workshop (e.g., "9:00 am - 4:30 pm")
startdate: 2019-01-03      # machine-readable start date for the workshop in YYYY-MM-DD format like 2015-01-01
enddate: 2019-01-04        # machine-readable end date for the workshop in YYYY-MM-DD format like 2015-01-02
instructor: ["Carrie Brown", "Kathryn Cooper", "Ryan Hagenson"] # boxed, comma-separated list of instructors' names as strings, like ["Kay McNulty", "Betty Jennings", "Betty Snyder"]
helper: ["Brian Moore", "Kimia Ameri"]     # boxed, comma-separated list of helpers' names, like ["Marlyn Wescoff", "Fran Bilas", "Ruth Lichterman"]
email: ["hcc-support@unl.edu"]    # boxed, comma-separated list of contact email addresses for the host, lead instructor, or whoever else is handling questions, like ["marlyn.wescoff@example.org", "fran.bilas@example.org", "ruth.lichterman@example.org"]
collaborative_notes: "https://pad.carpentries.org/2019-01-03-uno"            # optional: URL for the workshop collaborative notes, e.g. an Etherpad or Google Docs document
eventbrite:           # optional: alphanumeric key for Eventbrite registration, e.g., "1234567890AB" (if Eventbrite is being used)
---

{% comment %} See instructions in the comments below for how to edit specific sections of this workshop template. {% endcomment %}

{% comment %}
  HEADER

  Edit the values in the block above to be appropriate for your workshop.
  If the value is not 'true', 'false', 'null', or a number, please use
  double quotation marks around the value, unless specified otherwise.
  And run 'make workshop-check' *before* committing to make sure that changes are good.
{% endcomment %}

{% comment %}
  EVENTBRITE

  This block includes the Eventbrite registration widget if
  'eventbrite' has been set in the header.  You can delete it if you
  are not using Eventbrite, or leave it in, since it will not be
  displayed if the 'eventbrite' field in the header is not set.
{% endcomment %}
{% if page.eventbrite %}
<iframe
  src="https://www.eventbrite.com/tickets-external?eid={{page.eventbrite}}&ref=etckt"
  frameborder="0"
  width="100%"
  height="280px"
  scrolling="auto">
</iframe>
{% endif %}

<h2 id="general">General Information</h2>

{% comment %}
  INTRODUCTION

  Edit the general explanatory paragraph below if you want to change
  the pitch.
{% endcomment %}
{% if page.carpentry == "swc" %}
  {% include sc/intro.html %}
{% elsif page.carpentry == "dc" %}
  {% include dc/intro.html %}
{% elsif page.carpentry == "lc" %}
  {% include lc/intro.html %}
{% endif %}

{% comment %}
  AUDIENCE

  Explain who your audience is.  (In particular, tell readers if the
  workshop is only open to people from a particular institution.
{% endcomment %}
{% if page.carpentry == "swc" %}
  {% include sc/who.html %}
{% elsif page.carpentry == "dc" %}
  {% include dc/who.html %}
{% elsif page.carpentry == "lc" %}
  {% include lc/who.html %}
{% endif %}

{% comment %}
  LOCATION

  This block displays the address and links to maps showing directions
  if the latitude and longitude of the workshop have been set.  You
  can use https://itouchmap.com/latlong.html to find the lat/long of an
  address.
{% endcomment %}
{% if page.latlng %}
<p id="where">
  <strong>Where:</strong>
  {{page.address}}.
  Get directions with
  <a href="//www.openstreetmap.org/?mlat={{page.latlng | replace:',','&mlon='}}&zoom=16">OpenStreetMap</a>
  or
  <a href="//maps.google.com/maps?q={{page.latlng}}">Google Maps</a>.
</p>
{% endif %}

<center><form><button name="button" style="background-color: D71920; padding: 15px 32px" formaction="https://marketplace.unl.edu/hcc/hcc-software-carpentry-workshop-january-uno-2019.html">Register to Attend</button></form></center>

{% comment %}
  DATE

  This block displays the date and links to Google Calendar.
{% endcomment %}
{% if page.humandate %}
<p id="when">
  <strong>When:</strong>
  {{page.humandate}}.
  {% include workshop_calendar.html %}
</p>
{% endif %}

{% comment %}
  SPECIAL REQUIREMENTS

  Modify the block below if there are any special requirements.
{% endcomment %}
<p id="requirements">
  <strong>Requirements:</strong> Participants must bring a laptop with a
  Mac, Linux, or Windows operating system (not a tablet, Chromebook, etc.) that they have administrative privileges
  on. They should have a few specific software packages installed (listed
  <a href="#setup">below</a>). They are also required to abide by
  {% if page.carpentry == "swc" %}
  Software Carpentry's
  {% elsif page.carpentry == "dc" %}
  Data Carpentry's
  {% elsif page.carpentry == "lc" %}
  Library Carpentry's
  {% endif %}
  <a href="{{site.swc_site}}/conduct.html">Code of Conduct</a>.
</p>

<p id="parking">
<strong>Parking:</strong> Parking is available in the lots adjacent to the Peter Kiewit Insitute. Attendees with UNMC passes can park either in the student lot to the northwest of the building or in the Pacific Street garage located across 67th street once they register their passes with UNO Parking Services. Please contact <a href="mailto:unoparking@unomaha.edu">Parking Services</a> to register your pass prior to attending.<br>
			Daily visitor passes are also available to purchase at the kiosk in the Pacific Street garage. Additional information on the parking policy can be found on the <a href="https://www.unomaha.edu/business-and-finance/support-services/parking-services/permits.php#w">UNO Parking Services website</a>
</p>

{% comment %}
  ACCESSIBILITY

  Modify the block below if there are any barriers to accessibility or
  special instructions.
{% endcomment %}
<p id="accessibility">
  <strong>Accessibility:</strong> We are committed to making this workshop
  accessible to everybody.
  The workshop organizers have checked that:
</p>
<ul>
  <li>The room is wheelchair / scooter accessible.</li>
  <li>Accessible restrooms are available.</li>
</ul>
<p>
  Materials will be provided in advance of the workshop and
  large-print handouts are available if needed by notifying the
  organizers in advance.  If we can help making learning easier for
  you (e.g. sign-language interpreters, lactation facilities) please
  get in touch (using contact details below) and we will
  attempt to provide them.
</p>

{% comment %}
  CONTACT EMAIL ADDRESS

  Display the contact email address set in the configuration file.
{% endcomment %}
<p id="contact">
  <strong>Contact</strong>:
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

<hr/>

{% comment %} 
 SURVEYS - DO NOT EDIT SURVEY LINKS 
{% endcomment %}
<h2 id="surveys">Surveys</h2>
<p>Please be sure to complete these surveys before and after the workshop.</p>
{% if site.carpentry == "swc" %} 
<p><a href="{{ site.swc_pre_survey }}{{ site.github.project_title }}">Pre-workshop Survey</a></p>
<p><a href="{{ site.swc_post_survey }}{{ site.github.project_title }}">Post-workshop Survey</a></p>
{% elsif site.carpentry == "dc" %}
<p><a href="{{ site.dc_pre_survey }}{{ site.github.project_title }}">Pre-workshop Survey</a></p>
<p><a href="{{ site.dc_post_survey }}{{ site.github.project_title }}">Post-workshop Survey</a></p>
{% elsif site.carpentry == "lc" %}
<p><a href="{{ site.lc_pre_survey }}{{ site.github.project_title }}">Pre-workshop Survey</a></p>
<p><a href="{{ site.lc_post_survey }}{{ site.github.project_title }}">Post-workshop Survey</a></p>
{% endif %}

<hr/>


{% comment %}
  SCHEDULE

  Show the workshop's schedule.  Edit the items and times in the table
  to match your plans.  You may also want to change 'Day 1' and 'Day
  2' to be actual dates or days of the week.
{% endcomment %}
<h2 id="schedule">Schedule</h2>

{% if page.carpentry == "swc" %}
  {% include sc/schedule.html %}
{% elsif page.carpentry == "dc" %}
  {% include dc/schedule.html %}
{% elsif page.carpentry == "lc" %}
  {% include lc/schedule.html %}
{% endif %}

{% comment %}
  Collaborative Notes

  If you want to use an Etherpad, go to

      http://pad.software-carpentry.org/YYYY-MM-DD-site

  where 'YYYY-MM-DD-site' is the identifier for your workshop,
  e.g., '2015-06-10-esu'.
{% endcomment %}
{% if page.collaborative_notes %}
<p id="collaborative_notes">
  We will use this <a href="{{page.collaborative_notes}}">collaborative document</a> for chatting, taking notes, and sharing URLs and bits of code.
</p>
{% endif %}

<p><a href="{{ site.baseurl }}{% link lessons_index.md %}">Workshop Lessons Index</a></p>

<hr/>

{% comment %}
  SYLLABUS

  Show what topics will be covered.

  1. If your workshop is R rather than Python, remove the comment
     around that section and put a comment around the Python section.
  2. Some workshops will delete SQL.
  3. Please make sure the list of topics is synchronized with what you
     intend to teach.
  4. You may need to move the div's with class="col-md-6" around inside
     the div's with class="row" to balance the multi-column layout.

  This is one of the places where people frequently make mistakes, so
  please preview your site before committing, and make sure to run
  'tools/check' as well.
{% endcomment %}
<!--<h2 id="syllabus">Syllabus</h2>

{% if page.carpentry == "swc" %}
  {% include sc/syllabus.html %}
{% elsif page.carpentry == "dc" %}
  {% include dc/syllabus.html %}
{% elsif page.carpentry == "lc" %}
  {% include lc/syllabus.html %}
{% endif %}

<hr/> -->

{% comment %}
  SETUP

  Delete irrelevant sections from the setup instructions.  Each
  section is inside a 'div' without any classes to make the beginning
  and end easier to find.

  This is the other place where people frequently make mistakes, so
  please preview your site before committing, and make sure to run
  'tools/check' as well.
{% endcomment %}


<h2 id="setup">Setup</h2>

<p>
To participate in a Data Carpentry workshop, you will need working copies of the 
described software. Additionally, all participants will need an active account with the <a href="http://hcc.unl.edu">Holland Computing Center</a>. If you do not currently have an account, you can request one by completing a <a href="http://hcc.unl.edu/new-user-request">new user request form</a>.</p>

<p>Please note that all new accounts must be associated with an established HCC group. If your research group is not currently established with HCC, the group PI must first complete a <a href="https://hcc.unl.edu/new-group-request">new group request form</a>. Once a group has been established, a new user account can then be requested. </p>

<p><strong>For those who do not have a group to request an account under and are unable to create a group, demo accounts will be provided for use during the workshop.</strong> </p>

<p>Please make sure to install everything (or at least to download the installers) before the start of your workshop. Participants will need to bring a laptop with the following software installed.</p>
<p>
<strong>Mac users</strong>
</p><ul>
	<li> A spreadsheet program such as Microsoft Excel or <a href="http://www.datacarpentry.org/organization-genomics/setup/">LibreOffice</a></li>
	<!-- <li><a href="https://filezilla-project.org/download.php?show_all=1">Filezilla</a></li>  -->
	<li><a href="https://www.java.com/en/download/">Java</a></li> 
	<li><a href="http://software.broadinstitute.org/software/igv/download">Integrative Genomics Viewer (IGV)</a></li> 
        <!-- <li><a href="https://www.rstudio.com/products/rstudio/download/#download"> RStudio</a></li> -->
	<li><a href="setup/R-Rstudio-install.pdf">R and RStudio</a></li>

</ul>
<p></p>
<p>
<strong>Windows users</strong>
</p><ul>
	<li>Install <a href="https://the.earth.li/~sgtatham/putty/latest/w32/putty-0.70-installer.msi">PuTTY</a></li>
	<!-- <li><a href="http://www.putty.org/">Putty</a> Download putty.exe.</li> -->
	<li> A spreadsheet program such as Microsoft Excel or <a href="http://www.datacarpentry.org/organization-genomics/setup/">LibreOffice</a></li>
	<!-- <li><a href="https://filezilla-project.org/download.php?show_all=1">Filezilla</a></li> -->
	<li><a href="https://www.java.com/en/download/">Java</a></li> 
	<li><a href="http://software.broadinstitute.org/software/igv/download">Integrative Genomics Viewer (IGV)</a></li> 
        <!-- <li><a href="https://www.rstudio.com/products/rstudio/download/#download"> RStudio </a></li> -->
        <li><a href="setup/R-Rstudio-install.pdf">R and RStudio</a></li>
</ul>
<p></p>

<p>
If you encounter any issues with the setup instructions, please plan to arrive at the workshop at 8:30 AM to receive assistance.</p>
<hr>
<p></p>

