=====================
Robmongodb Documentation
=====================

=====================
Mongodb Documentation Compilation on Ubuntu
=====================

I assume that python already installed on machine and added to PATH. 

1. Install ``easy_install``:

   * Download the appropriate egg for your version of Python (e.g. setuptools-0.6c9-py2.4.egg). Do NOT rename it.
   * Run it as if it were a shell script, e.g. sh setuptools-0.6c9-py2.4.egg. Setuptools will install itself using the matching version of Python (e.g. python2.4), and will place the easy_install executable in the default location for installing Python scripts (as determined by the standard distutils configuration files, or by the Python installation).

2. Install sphinx documentation:

	 sudo easy_install -U Sphinx

3. Clone mongodb documentation source from github:

	 git clone git://github.com/mongodb/docs

4. Adjust layout here. -> /themes/mongodb/layout.html

* Remove Left Sidebar - Set ``render_sidebar`` variable to false at the top and remove:
     
     {%- block sidebar2 %}{{ sidebar() }}{% endblock %}


* Remove Header -- remove following parts:

	 {%- block header %} .. {%- endblock %}

	 {%- block analytics %}
	 {%- include "analytics.html" %}
	 {%- endblock %}

5. Navigate to the ``docs`` folder and create folder with name ``build``:

	 cd docs/

	 md build

	 make html

6. After build done go to the ``/build/master/html`` and copy content to the robomongo docs repository.

-- Paralect