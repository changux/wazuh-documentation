.. _connect_wazuh_app:

Connect the Wazuh App with the API
==================================

In this section, we'll register the Wazuh API (installed on the Wazuh server) into the Wazuh App in Kibana:

1. Open a web browser and go to the Elastic Stack server's IP address on port 5601 (default Kibana port). Then, from the left menu, go to the Wazuh App.

  .. image:: ../../images/installation/wazuhapp/kibana_app.png
    :align: center
    :width: 100%

2. Click on ``Add new API``.

  .. image:: ../../images/installation/wazuhapp/connect_api.png
    :align: center
    :width: 100%

3. Before filling out the fields, go to your Wazuh server and using the command prompt as root set a non-default credentials to protect your Wazuh API:

  .. code-block:: bash

    # Replace your desired username for myUserName.
    $ cd /var/ossec/api/configuration/auth
    $ sudo node htpasswd -c user myUserName

    # Do not forget to restart the API to apply the changes:
    $ systemctl restart wazuh-api
    $ service wazuh-api restart

4. Fill Username and Password with appropriate credentials you created in previous step.  Enter ``http://MANAGER_IP`` for the URL, where ``MANAGER_IP`` is the real IP address of the Wazuh qserver. Enter "55000" for the Port.

  .. image:: ../../images/installation/wazuhapp/fields_api.png
    :align: center
    :width: 100%

.. note:: If you have followed the Wazuh Documentation for Nginx, the URL must be ``https://localhost``.

6. Click on ``Save``.

  .. image:: ../../images/installation/wazuhapp/app_running.png
    :align: center
    :width: 100%

Next steps
----------

Once the Wazuh and Elastic Stack servers are installed and connected, you can install and connect Wazuh agents. How to do it:

- :ref:`Debian/Ubuntu <wazuh_agent_deb>`
- :ref:`RedHat/CentOS <wazuh_agent_rpm>`
- :ref:`Windows <wazuh_agent_windows>`
