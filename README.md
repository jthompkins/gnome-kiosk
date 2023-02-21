GNOME Kiosk Playbook
====================

This role configures a RHEL system to be able to use kiosk mode.

Documentation for configuring kiosk mode: https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/8/html/using_the_desktop_environment_in_rhel_8/assembly_restricting-the-session-to-a-single-application_using-the-desktop-environment-in-rhel-8

An inventory file needs to be supplied for the playbook.sh script (either create the inventory file or change the script to point to a valid inventory).

When the system is rebooted the user needs to be changed to kiosk mode from the log in page. There is a small cog wheel present after selecting the configured user; select kiosk mode from the list after clicking on the wheel.

Currently the playbook launches firefox at the page time.gov. To change what application is being kiosked modify the play that populates the .local/bin/redhat-kiosk shell script that is executed. The while loop ensures the application is relaunched if closed since it is the only application available for the kiosk user.
