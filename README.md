# Realtime-Election-Voting-System

This repository contains the code for a realtime election voting system. The system is built using Python, Kafka, Spark Streaming, Postgres and Streamlit. The system is built using Docker Compose to easily spin up the required services in Docker containers.

architecture -
<img width="807" alt="image" src="https://github.com/kaesahu/Realtime-Election-Voting-System/assets/39849443/ea6681fb-16f9-4124-b056-248a594f1063">

system flow- 
<img width="800" alt="image" src="https://github.com/kaesahu/Realtime-Election-Voting-System/assets/39849443/dd6cb662-9414-4bc4-b5a3-de538c0e2616">

main.py: This is the main Python script that creates the required tables on postgres (candidates, voters and votes), it also creates the Kafka topic and creates a copy of the votes table in the Kafka topic. It also contains the logic to consume the votes from the Kafka topic and produce data to voters_topic on Kafka.
voting.py: This is the Python script that contains the logic to consume the votes from the Kafka topic (voters_topic), generate voting data and produce data to votes_topic on Kafka.
spark-streaming.py: This is the Python script that contains the logic to consume the votes from the Kafka topic (votes_topic), enrich the data from postgres and aggregate the votes and produce data to specific topics on Kafka.
streamlit-app.py: This is the Python script that contains the logic to consume the aggregated voting data from the Kafka topic as well as postgres and display the voting data in realtime using Streamlit.

