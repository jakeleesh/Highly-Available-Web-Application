## OPS 4: How do you implement observability in your workload?
1. OPS04-BP01
    1. **Start with business outcomes:**
        - Move operations to cloud to save money and transform business with a cloud-first approach.
    2. **Correlate technical metrics with business objectives:** 
        - RDS database instead of on-premises data center
        - Multiple AZ for availability and redundency
        - Load Balancer for scalability
    3. **Use Amazon CloudWatch**:
        - Enabled group metrics collection within CloudWatch in Auto Scaling Group
2. OPS04-BP-2
    1. Used Amazon CloudWatch

## OPS 6: How do you mitigate deployment risks?
1. OPS06-BP01
    1. **Document policy for unsuccesful changes**
        - Policy should be documented in the event unsuccessful changes occur.
2. OPS06-BP02
    1. **Testing deployment process**
        - Have 2 AZ. Use one and mirror as pre-production environment. Test in that environment.
3. OPS06-BP03
    1. **Implement safety controls in the end-to-end release process**
        - Use blue/green deployment
4. OPS06-BP04
    1. **Automate testing**
        - Used AWS Fault Injection Simulator to terminate EC2 Instance.
        - Auto Scaling Group has desired capacity.

## SEC 3: How do you manage permissions for people and machines?
1. SEC03-BP01
    1. Choose the appropriate identity type and method of authentication and authorization
        - IAM roles
2. SEC03-BP02
    1. Principle of least privilege
        - IAM roles used

## SEC 4: How do you detect and investigate security events?
1. SEC04-BP01
    1. Set up querying and retrieval mechanisms and alerting
        - AWS CloudTrail can be used
2. SEC04-BP02
    1. Implement automated alerting with GuardDuty
        - Use GuardDuty
3. SEC04-BP04
    1. Discover metrics
        - CloudWatch is enabled and alerts can be created to notify team.

## REL 7: How do you design your workload to adapt to changes in demand?
1. REL07-BP01
    1. **Configure and use AWS Auto Scaling**
        - Auto Scaling Group created
    2. **Use Elastic Load Balancing**
        - Application Load Balancer created
    3. **Use a highly available DNS provider**
        - Route 53 could have been used to manage load balancer
    4. Configure and use Amazon CloudFront or a trusted content delivery network (CDN)
        - CDN created using CloudFormation
2. REL07-BP02
    1. Implement observability
        - Scaling used in Auto Scaling Group to increase EC2 Instance to desired/maximum capacity
3. REL07-BP03
    1. Obtain resources upon detection that more resources are needed for a workload
        - Scaling used in Auto Scaling Group to increase EC2 Instance to desired/maximum capacity
4. REL07-BP04
    1. Perform load testing
        - Can test load by increasing utilization of CPU and test if more EC2 Instances are spun up.

## REL 13: How do you plan for disaster recovery (DR)?
1. REL13-BP01
    1. Set RTO and RPO for your workload
        - Recovery Time Objective (RTO) and Recovery Point Objective (RPO) should be defined for workload and tested.
2. REL13-BP02
    1. Use a DR strategy
        - Multiple AZ
        - DR Strategy that uses multiple Regions can be adopted.
3. REL13-BP03
    1. Establish recovery patterns and regularly test them
        - Used AWS Fault Injection Simulator to terminate EC2 Instance.
        - Test often
4. REL13-BP04
    1. Permit AWS Config to track potential drift locations
        - Can be used
    2. Use AWS CloudFormation to deploy your infrastructure
        - CloudFormation used to configure network, launch template and CDN.
5. REL13-BP05 Automate recovery
    1. Automate recovery paths
        - Can use Elastic Disaster Recovery

## PERF 1: How do you select appropriate cloud resources and architecture patterns for your workload?
1. PERF01-BP01
    1. Stay up-to-date with these new services
        - Go for AWS Training and follow AWS blogs for new services and features
2. PERF01-BP02
    1. Leverage resources
        - Use guides and whitepapers
        - Get certified
3. PERF01-BP03
    1. Optimizing workloads
        - Use Well-Architected cost optimization to optimize cost.
4. PERF01-BP06
    1. Use benchmarking to assess how workload’s components perform
        - CloudWatch is enabled. Can be used to see baseline performance to determine if need to adjust.

## PERF 5: What process do you use to support more performance efficiency for your workload?
1. PERF05-BP01
    1. KPIs
        - Use CloudWatch to collect metrics.
        - Identify metrics that can be used for KPIs to gauge goals.
2. PERF05-BP02
    1. Set tracing to identify traffic patterns, latency, and critical performance areas
        - CloudWatch enabled.
        - Can use RDS Enhanched Monitoring since we are using RDS database.

## COST 3: How do you monitor usage and cost?
1. COST03-BP01
    1. Configure your CUR
        - Configure the cost and usage report using billing console

## COST 9: How do you manage demand, and supply resources?
1. COST09-BP01
    1. Analyze workload demand
        - Use Amazon CloudWatch and monitor data to gain insight on past workload.
2. COST09-BP02
    1. Implement throttle
        - Analyze requests to see overrall demand
        - Implement throttle in workload to reduce components
3. COST09-BP03
    1. AWS Auto Scaling
        - Auto Scaling Group created
        - Adjusts capacity to ensure performance
    2. Elastic Load Balancing
        - Application Load Balancer created

## SUS 3: How do you take advantage of software and architecture patterns to support your sustainability goals?
1. SUS03-BP02
    1. Review workload to identify idle or unused components
        Monitor utlization using CloudWatch
        - Retire components no longer needed

## SUS 5: How do you select and use cloud hardware and services in your architecture to support your sustainability goals?
1. SUS05-BP01
    1. Optimally select number of hardware required
        - Auto Scaling Group with desired/minimum capacity defined
2. SUS05-BP03
    1. Managed services
        - Using RDS database instead of provisioning own database on EC2 Instance