

   <title>3-Tier Resilient Architecture on AWS</title>


  <h1>3-Tier Resilient Architecture on AWS</h1>
    <p>This repository demonstrates a <strong>3-tier resilient architecture</strong> deployed on AWS using Terraform. It showcases a scalable and fault-tolerant design for hosting applications in a production-grade environment.</p>

  <h2>Architecture Overview</h2>
    <p>The 3-tier architecture includes:</p>

  <h3>Web Tier:</h3>
     <ul>
        <li>Public-facing layer.</li>
        <li>Auto Scaling Group with an Application Load Balancer (ALB).</li>
        <li>Security Group to allow HTTP/HTTPS traffic.</li>
    </ul>

  <h3>Application Tier:</h3>
    <ul>
        <li>Internal-facing layer for business logic.</li>
        <li>Auto Scaling Group for high availability.</li>
        <li>Communication restricted to the Web Tier.</li>
    </ul>

  <h3>Database Tier:</h3>
    <ul>
        <li>Managed MySQL RDS instance in a private subnet.</li>
        <li>Multi-AZ deployment for resilience.</li>
        <li>Secured with a Security Group allowing access only from the Application Tier.</li>
    </ul>

  <h2>Features</h2>
    <ul>
        <li><strong>Resilience:</strong> Leverages AWS Multi-AZ for RDS and Auto Scaling Groups across multiple Availability Zones.</li>
        <li><strong>Scalability:</strong> Elastic scaling of Web and Application tiers.</li>
        <li><strong>Security:</strong> Fine-grained Security Groups to control traffic between layers.</li>
        <li><strong>Automation:</strong> Modularized Terraform code for reusable and organized configurations.</li>
    </ul>

  <h2>Modules and Resources</h2>

  <h3>VPC:</h3>
    <ul>
        <li>Deployed using the <code>terraform-aws-modules/vpc</code> module.</li>
        <li>Public, Private, and Database subnets.</li>
        <li>NAT Gateways for outbound access from private subnets.</li>
    </ul>

  <h3>Compute:</h3>
    <ul>
        <li>Launch templates for both Web and Application tiers.</li>
        <li>Auto Scaling Groups for high availability.</li>
    </ul>

  <h3>Networking:</h3>
    <ul>
        <li>Application Load Balancer for the Web tier.</li>
        <li>ALB Target Groups and Listeners for traffic routing.</li>
    </ul>

  <h3>Database:</h3>
    <ul>
        <li>MySQL RDS with Multi-AZ for fault tolerance.</li>
        <li>Secrets managed via Terraform variables (for simplicity).</li>
    </ul>

