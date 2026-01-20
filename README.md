# Ansible-EC2-Monitor
Ansible VM Monitor is a lightweight, agentless monitoring solution built using Ansible to collect and report system metrics from AWS EC2 instances. It leverages AWS dynamic inventory to automatically discover virtual machines and generate a consolidated HTML email report with key health metrics such as CPU, memory, and disk usage.

This project is ideal for teams looking for a simple, scheduled monitoring mechanism without deploying heavy monitoring stacks like Prometheus or CloudWatch dashboards. The solution is designed to be run from a control node (local VM or bastion host) and can be scheduled using cron for periodic execution (e.g., hourly reports).

How It Works :

AWS inventory plugin discovers EC2 instances dynamically.
Metrics playbook collects system data from target hosts.
Metrics are aggregated on the control node.
An HTML email report is generated using Jinja2 templates.
The report is sent to one or more recipients via SMTP.
(Optional) Cron schedules the process to run hourly.

Project Structure:
Ansible-VM-Monitor/
├── ansible.cfg
├── inventory/
│   └── aws_ec2.yaml
├── group_vars/
│   └── all.yaml
├── playbook.yaml
├── collect_metrics.yaml
├── send_report.yaml
└── templates/
    └── report_email_animated.html.j2
