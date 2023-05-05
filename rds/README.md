# AWS RDS

* You cannot disable automated backups


## Multi AZ Maintenance

RDS applies OS updates by performing maintenance on the standby, then promoting the standby to primary and finnaly performing maintenance on the old primary which becomes the new standby.

When you modify the database engine for your DB instance in a Multi-AZ deployment, then Amazon RDS upgrades both the primary and secondary DB instances at the same time. In this case, the database engine for the entire Multi-AZ deployment is shut down during the upgrade.
