---
layout: workshop
carpentry: 'dc'
venue: "H3ABioNet presents: 16S downstream analyses in R"
humandate: '30 Sept - 7 October 2019'
startdate: 2019-09-30
enddate: 2019-10-07
instructor: ["Katie Lennard"]
email: ["katieviljoen@gmail.com"]

root: .  # Is the only page that don't follow the partner /:path/index.html
permalink: index.html  # Is the only page that don't follow the partner /:path/index.html
---

> ## Prerequisites
>
> You should have your access to R and RStudio via your own compute cluster.
{: .prereq}

{% include links.md %}

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
  <strong>Requirements:</strong> Participants must have access to R and RStudio via their own compute cluster provided by their system administrator. 
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
  SCHEDULE

  Show the workshop's schedule.  Edit the items and times in the table
  to match your plans.  You may also want to change 'Day 1' and 'Day
  2' to be actual dates or days of the week.
{% endcomment %}

{% comment %}
<h2 id="schedule">Schedule</h2>

{% if page.carpentry == "swc" %}
  {% include sc/schedule.html %}
{% elsif page.carpentry == "dc" %}
  {% include dc/schedule.html %}
{% elsif page.carpentry == "lc" %}
  {% include lc/schedule.html %}
{% endif %}
{% endcomment %}

{% comment %}
  Collaborative Notes

  If you want to use an Etherpad, go to:

      http://pad.software-carpentry.org/YYYY-MM-DD-site

  where 'YYYY-MM-DD-site' is the identifier for your workshop,
  e.g., '2015-06-10-esu'.
{% endcomment %}
{% comment %}
{% if page.collaborative_notes %}
<p id="collaborative_notes">
  We will use this <a href="{{page.collaborative_notes}}">collaborative document</a> for chatting, taking notes, and sharing URLs and bits of code.
</p>
{% endif %}
{% endcomment %}
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
<h2 id="syllabus">Syllabus</h2>

{% if page.carpentry == "swc" %}
  {% include sc/syllabus.html %}
{% elsif page.carpentry == "dc" %}
  {% include dc/syllabus.html %}
{% elsif page.carpentry == "lc" %}
  {% include lc/syllabus.html %}
{% endif %}

<hr/>

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
  To participate in this workshop,
  you will need to follow the instructions provided on the Vula website to a) ssh into the cluster where we will demonstrate the use of Nextflow to run dada2 in an automated fashion and b) to launch RStudio via your web browser for downstream analyses.
</p>
{% comment %}
<p>
  We maintain a list of common issues that occur during installation as a reference for instructors
  that may be useful on the
  <a href = "{{site.swc_github}}/workshop-template/wiki/Configuration-Problems-and-Solutions">Configuration Problems and Solutions wiki page</a>.
</p>
{% endcomment %}

<div id="r"> {% comment %} Start of 'R' section. {% endcomment %}
  <h3>Useful links</h3>

  <p>
      <ul>
      <li>
          <a href="https://www.nextflow.io/docs/latest/index.html">Nextflow documentation</a>
        </li>
       <li><a href="https://nf-co.re/pipelines">nf-core: A community effort for curated pipelines in Nextflow</a> </li>
       <li><a href="https://nf-co.re/developers/adding_pipelines">Building your own pipeline in Nextflow using a high quality nf-core template</a> </li>
        <li><a href="https://github.com/nextflow-io/awesome-nextflow">More Nextflow pipelines</a></li>
        <li><a href="https://github.com/kviljoen/H3ABioNet_16S/blob/gh-pages/data/Nextflow_report_example.pdf">Nextflow reports: an example</a></li>
        <li><a href="https://gist.github.com/kviljoen/97d36c689c5c9b9c39939c7a100720b9">Microbiome custom R functions gist</a></li>
        <li><a href="https://benjjneb.github.io/dada2/training.html">Taxonomic reference databases for use with dada2</a></li>
        <li><a href="https://joey711.github.io/phyloseq/"> phyloseq tutorials</a></li>
        <li><a href="https://www.davidzeleny.net/anadat-r/doku.php/en:overview"> Analysis of community ecology in R: methods theory explained</a></li>
        <li><a href="https://www.youtube.com/watch?v=5SKloz65eYY"> metagenomeSeq for differential abundance testing: a video presentation by the author</a></li>
        <li><a href="https://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1003531#ack"> On rarefaction and differential abundance testing methods compared</a></li>
        <li><a href="http://cc.oulu.fi/~jarioksa/opetus/metodi/vegantutor.pdf"> Identifying factors associated with changes in microbiota composition using PERMANOVA (R package vegan) </a></li>  

        
    </ul>
  </p>

{% comment %}

  <div class="row">
    <div class="col-md-4">
      <h4 id="r-windows">Windows</h4>
      <a href="https://www.youtube.com/watch?v=q0PjTAylwoU">Video Tutorial</a>
      <p>
        Install R by downloading and running
        <a href="https://cran.r-project.org/bin/windows/base/release.htm">this .exe file</a>
        from <a href="https://cran.r-project.org/index.html">CRAN</a>.
        Also, please install the
        <a href="https://www.rstudio.com/products/rstudio/download/#download">RStudio IDE</a>.
        Note that if you have separate user and admin accounts, you should run the 
        installers as administrator (right-click on .exe file and select "Run as 
        administrator" instead of double-clicking). Otherwise problems may occur later, 
        for example when installing R packages.
      </p>
    </div>
    <div class="col-md-4">
      <h4 id="r-macosx">macOS</h4>
      <a href="https://www.youtube.com/watch?v=5-ly3kyxwEg">Video Tutorial</a>
      <p>
        Install R by downloading and running
        <a href="https://cran.r-project.org/bin/macosx/R-latest.pkg">this .pkg file</a>
        from <a href="https://cran.r-project.org/index.html">CRAN</a>.
        Also, please install the
        <a href="https://www.rstudio.com/products/rstudio/download/#download">RStudio IDE</a>.
      </p>
    </div>
    <div class="col-md-4">
      <h4 id="r-linux">Linux</h4>
      <p>
        You can download the binary files for your distribution
        from <a href="https://cran.r-project.org/index.html">CRAN</a>. Or
        you can use your package manager (e.g. for Debian/Ubuntu
        run <code>sudo apt-get install r-base</code> and for Fedora run
        <code>sudo dnf install R</code>).  Also, please install the
        <a href="https://www.rstudio.com/products/rstudio/download/#download">RStudio IDE</a>.
      </p>
    </div>
  </div>
</div> {% comment %} End of 'R' section. {% endcomment %}

<div id="for-everyone"> {% comment %} Start of 'SQLite' section. {% endcomment %}
  <h4>For everyone</h4>
<p>  
For everyone
After installing R and RStudio, you need to install the tidyverse and RSQLite packages.
After starting RStudio, at the console type: install.packages("tidyverse")
</p>

{% endcomment %}
