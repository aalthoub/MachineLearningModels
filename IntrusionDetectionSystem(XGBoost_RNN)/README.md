# Intrusion Detection System (IDS)
With the rapid growth of cloud computing, securing cloud data centers against potential security threats has become a critical concern. This project is to build a hybrid intrusion detection system that combines the power of the gradient boosting algorithm, specifically XGBoost, with the capabilities of Recurrent Neural Networks (RNNs). 

# Objective
The objective of the proposed IDS is to effectively predict and detect temporal patterns in network traffic, thereby enhancing the security posture of cloud data centers. By fusing XGBoost and Sequecial RNN techniques, the IDS aims to achieve a holistic view of network behavior, enabling the identification of subtle anomalies that may indicate intrusion attempts.

# Dataset
The model uses the NSL-KDD dataset. Comprising a diverse array of network traffic scenarios, the NSL-KDD dataset encapsulates both normal and anomalous activities, encompassing various types of attacks and intrusions.  

The NSL-KDD dataset comprises approximately 126,000 records and encompasses 43 features. The following is a comprehensive overview of the features present in the NSL-KDD dataset: 

| Feature                  | Description                                                                                          |
|--------------------------|------------------------------------------------------------------------------------------------------|
| Duration                 | The duration of the connection.                                                                      |
| Protocol_Type            | The protocol used in the connection (e.g., TCP, UDP, ICMP).                                          |
| Service                  | The type of service being accessed (e.g., http, ftp, smtp).                                          |
| Flag                     | Flags used in the connection establishment, termination, and data transfer.                          |
| Src_bytes                | The number of data bytes sent from the source to the destination.                                    |
| Dst_bytes                | The number of data bytes sent from the destination to the source.                                    |
| Land                     | A binary column indicating whether the connection is from/to the same host/port (land attack).       |
| Wrong_fragment           | The number of wrong fragments in the connection.                                                     |
| Urgent                   | The number of urgent packets in the connection.                                                      |
| Hot                      | A binary column indicating whether the connection has a "hot" indicator.                             |
| Num_failed_logins        | The number of failed login attempts.                                                                 |
| Logged_in                | A binary column indicating whether the user is logged in.                                            |
| Num_compromised          | The number of compromised conditions.                                                                |
| Root_shell               | A binary column indicating whether a root shell was obtained.                                        |
| Su_attempted             | A binary column indicating whether there was an attempt to escalate privileges using the su command. |
| Num_root                 | The number of root accesses.                                                                         |
| Num_file_creations       | The number of file creation operations.                                                              |
| Num_shells               | The number of shell prompts.                                                                         |
| Num_access_files         | The number of operations on access control files.                                                    |
| Num_outbound_cmds        | The number of outbound commands in an ftp session.                                                   |
| Is_host_login            | A binary column indicating whether the login belongs to a host login session.                        |
| Is_guest_login           | A binary column indicating whether the login is a guest login.                                       |
| Count                    | The number of connections to the same host as the current connection in the past two seconds.        |
| Srv_count                | The number of connections to the same service as the current connection in the past two seconds.     |
| Serror_rate              | The percentage of connections that have "SYN" errors.                                                |
| Srv_serror_rate          | The percentage of connections to the same service that have "SYN" errors.                            |
| Rerror_rate              | The percentage of connections that have "REJ" errors.                                                |
| Srv_rerror_rate          | The percentage of connections to the same service that have "REJ" errors.                            |
| Same_srv_rate            | The percentage of connections to the same service.                                                   |
| Diff_srv_rate            | The percentage of connections to different services.                                                 |
| Srv_diff_host_rate       | The percentage of connections to different hosts for the same service.                               |
| Dst_host_count           | The number of connections to the same destination host in the past two seconds.                      |
| Dst_host_srv_count       | The number of connections to the same destination service in the past two seconds.                   |
| Dst_host_same_srv_rate   | The percentage of connections to the same destination service.                                       |
| Dst_host_diff_srv_rate   | The percentage of connections to different destination services.                                     |
| dst_host_serror_rate     | The percentage of SYN errors among the connections to the same destination host.                     |
| dst_host_srv_serror_rate | The percentage of SYN errors among the connections to the same destination service                   |
| dst_host_rerror_rate     | The percentage of REJ (reject) errors among the connections to the same destination host.            |
| dst_host_srv_rerror_rate | The percentage of REJ (reject) errors among the connections to the same destination service.         |
| outcome                  | It represents the classification of the connection as either normal or attack.                       |

The objective of the model is to predict whether a packet is `attack` or 'normal'. Thus, the target variable would be the column 'outcome'. 

# Modeling and Evaluation 
- The confusion matrix visualizes the comparision between predicted and test values.
![confusion matrix](/IntrusionDetectionSystem(XGBoost_RNN)/images/1.png)

- The ROC curve visualizes the trade-off between the true positive rate (sensitivity) and false positive rate as the classification threshold varies.
![roc plot](/IntrusionDetectionSystem(XGBoost_RNN)/images/2.png)
