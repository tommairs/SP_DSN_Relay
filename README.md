# SP_DSN_Relay
A bounce forwarding engine for SparkPost

# Why
Several people have asked for a bounce relay function similar to the sync bounce, or bounce forward function in Momentum.
While we cannot tuen that on for a number of reasons, we can roughly replicate the functionality.
SparkPost collects all of the in and out of bacd bounces and Spam complaints, logs them and drops them, but the key here is the logging part.  After they are logged, they are pushed in webhooks.  So if we collect the webhook data, we can extract all teh important bounce details and relay them back to the injection system as simulated DSNs.  

The net is that SparkPost still reports the bounce data as it needs to, but we can forward the DSN data to the injection system for whatever downstream processing is needed there.

