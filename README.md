## Setup
All experiments are implemented on a PC with AMD Ryzen 5, CPU 2.38GHZ, and 16G RAM, running on Windows 10 x64 with Python 3.9.

## Methods
- GA, PSO and TLBO use the original candidate set as the data input, while these algorithms+Skyline select the Skyline service in the candidate service set as the latest candidate set.
- The entire process of SQMSC-MH is to find Skyline services.
- The input data of the above code are all data in the qws2resetIndex dataset. The qws2resetIndex dataset is roughly the same as the real dataset QWS2. The difference is that we have disturbed its row index.
- Qws2 reset Index records eight QoS attributes, including response time, availability, throughput, successability, reliability, compliance, best practices and latency.
- When two QoS attributes are set in the experiment, response time and availability are selected; response time, availability and throughput, is selected for three; and response time, availability, throughput and successability are selected for four.

##Dataset
- The data set we use is the first web service data set introduced in 2007 to measure the quality of service (QoS) of real web services. The main goal of this data set is to provide a foundation for web services researchers. Web services are collected using the Web Services Crawler Engine (WSCE). Most of these services are obtained from public sources on the web, including the Universal Description, Discovery and Integration (UDDI) registry, search engines, and service portals.[Click here to go directly to the official website of the dataset](https://qwsdata.github.io/)

## Parameters
### GA、GA+Skyline
- candidate_number: Number of services in candidate set of each subtask,
- crossover_probability
- mutation_probability
- task_number
- population_size
### PSO、PSO+Skylie：
- w: Inertia weight
- c1 and c2: Learning factor
- Vmax: speed limit
- task_number
- population_size
### TLBO、TLBO+Skyline
- task_number
- population_size
### SQWSC
- n: Number of QoS attributes
- candidate_number: Number of services in candidate set of each subtask
- crossover_probability
- mutation_probability
- task_number
- population_size

## Note：
- If you have any question about my code or want to share your idea, you can send email to me. Welcome at any time!
- Email: jiayanxiang02@gmail.com
