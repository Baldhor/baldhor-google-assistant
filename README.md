<p align="center">
  <a href="https://github.com/Baldhor/baldhor-google-assistant">
    <img src="https://brands.home-assistant.io/google_home/icon.png" alt="Logo" height="200">
  </a>
</p>

<h3 align="center">Home Assistant Google Assistant community integration</h3>

<p align="center">
  This custom integration aims to add language support of alarm_control_panel from configuration to enhance the standard integration for Home Assitant.
  It uses 'ha-google-home' as a project code base (because I have no idea how it works :) ).
  However the custom component code itself is a copy-paste from google assistant standard integration.

  For standard configuration, refer to: https://www.home-assistant.io/integrations/google_assistant/
  For installation as a custom component from HACS, refer to: https://github.com/leikoilja/ha-google-home
    -> Just search for Baldhor Google Assistant in HACS

  The chapter below only details the additional configuration I implemented to handle language of alarm_control_panel's arming levels.
</p>

<p align="left">
  <p>
    Standard config file looks like this:
    <code>
      google_assistant:
        project_id: xxx
        service_account: !include SERVICE_ACCOUNT.JSON
        secure_devices_pin: 'xxx'
        report_state: true
        exposed_domains:
          - camera
        entity_config:
          alarm_control_panel.alarmo:
            name: Surveillance
            room: Maison
    </code>
  </p>

  <p>
    With this custom component, you can do this instead:
    <code>
      baldhor_google_assistant:
        project_id: xxx
        service_account: !include SERVICE_ACCOUNT.JSON
        secure_devices_pin: 'xxx'
        report_state: true
        exposed_domains:
          - camera
        entity_config:
          alarm_control_panel.alarmo:
            name: Surveillance
            room: Maison
            lang: fr
            armed_away: Absent
            armed_night: Nuit
            armed_vacancy: Vacances
            triggered: Déclenché
    </code>
  </p>
</p>