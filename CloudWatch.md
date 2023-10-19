# AWS CloudWatch Project - EC2 Instance Monitoring

![AWS CloudWatch Logo](https://i.imgur.com/Rm5OKQQ.png)

This project demonstrates how to set up AWS CloudWatch dashboards and alarms to monitor an Amazon EC2 instance. Monitoring your EC2 instances is crucial to ensure their health and performance.

## Prerequisites

Before you begin, make sure you have the following prerequisites in place:

- An AWS account with an Amazon EC2 instance that you want to monitor.
- AWS IAM (Identity and Access Management) permissions to create and manage CloudWatch resources.
- AWS CLI installed and configured with necessary credentials.

For this project I will be monitoring a EC2 instance that I created in a different repository. For reference, the EC2 instance can be found [HERE](AWS-EC2-WordPress-E-commerce.md)

## Configuration

Follow these steps to configure CloudWatch dashboards and alarms for your EC2 instance:

1. **Create a CloudWatch Dashboard**:
   - Log in to the AWS Management Console.
   - Navigate to the CloudWatch service.
   - Click on "Dashboards" in the left menu.
   - Click "Create Dashboard" and give it a name.
   - Add widgets to your dashboard to display relevant metrics for your EC2 instance.

2. **Set Up CloudWatch Alarms**:
   - In the CloudWatch console, click on "Alarms" in the left menu.
   - Click "Create Alarm."
   - Select the metric you want to monitor (e.g., CPU utilization).
   - Configure the alarm threshold and actions (e.g., sending an SNS notification).
   - Complete the alarm creation process.

3. **Attach Alarms to Your EC2 Instance**:
   - In the EC2 console, select your instance.
   - In the "Monitoring" tab, click on "Create a CloudWatch alarm."
   - Choose the alarm you created in step 2 and confirm.

4. **Monitor Your EC2 Instance**:
   - Your CloudWatch dashboard will now display real-time metrics, and alarms will trigger when thresholds are breached.

## Usage

Explain how to use your CloudWatch dashboard and alarms to monitor your EC2 instance effectively. Provide examples of common actions, such as responding to alarm notifications.

## Contributing

If you'd like to contribute to this project or report issues, please check the [CONTRIBUTING.md](CONTRIBUTING.md) file for guidelines.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Acknowledgments

Mention any tools, libraries, or resources you used or were inspired by during the project.

## Contact

For questions or feedback, feel free to contact the project owner:

- [Your Name](mailto:youremail@example.com)

