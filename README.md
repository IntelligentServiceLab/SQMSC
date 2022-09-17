## Setup
All experiments are implemented on a PC with AMD Ryzen 5, CPU 2.38GHZ, and 16G RAM, running on Windows 10 x64 with Python 3.9.

## Dataset
- The data set we use is the first web service data set introduced in 2007 to measure the quality of service (QoS) of real web services. The main goal of this data set is to provide a foundation for web services researchers. Web services are collected using the Web Services Crawler Engine (WSCE). Most of these services are obtained from public sources on the web, including the Universal Description, Discovery and Integration (UDDI) registry, search engines, and service portals.[Click here to go directly to the official website of the dataset](https://qwsdata.github.io/)

## Characteristics of the database
|  Item   | Value  |
|  ----  | ----  |
| Number of the service  | 2507 |
| Number of the QoS properties  | 8 |
| The maxinmum of response time | 4989.67 |
| The minimun of response time | 37.00 |
| The maximun of availability | 1.00 |
| The minimun of availability | 0.07 |
| The maximun of throughput | 43.10 |
| The minimun of throughput | 0.10 |
| The maximun of reliability | 0.89 |
| The minimun of reliability | 0.33 |

## SQMSC: Scalable QoS-aware Manufacturing Service Composition optimization approach via business process decomposition
### 1. Motivation
With the development of service-oriented manufacturing model, more and more manufacturing services are released through manufacturing service platform. It is well known that the QoS-aware manufacturing service composition problem is NP-hard. Therefore, optimization remains a challenging research problem, especially in the case of large-scale manufacturing service data, which also raises scalability issues. In order to improve the optimization performance and scalability of QoS-aware manufacturing service composition, we think of a scalable QoS-aware manufacturing service composition optimization method based on business process decomposition to solve the problem step by step.[SQMSC code](https://github.com/IntelligentServiceLab/SQMSC/blob/main/SQMSC.py)
### 2. Baseline
| Baselines | Description | Code |
| :-----: | :----: | :----: |
| GA | This approach uses genetic algorithm. | [GA code](https://github.com/IntelligentServiceLab/SQMSC/blob/main/GA.py) |
| PSO | This approach uses particle swarm optimization algorithm. | [PSO code](https://github.com/IntelligentServiceLab/SQMSC/blob/main/PSO.py) |
| TLBO | This approach uses teaching learning based optimization algorithm. | [TLBO code](https://github.com/IntelligentServiceLab/SQMSC/blob/main/TLBO.py) |
| GA+Skyline | This approach uses genetic algorithm with initial Skyline services for each tasks. | [GA+Skyline](https://github.com/IntelligentServiceLab/SQMSC/blob/main/GA%2BSkyline.py) |
| PSO+Skyline | This approach uses particle swarm optimization algorithm with initial Skyline services for each tasks. | [PSO+Skyline](https://github.com/IntelligentServiceLab/SQMSC/blob/main/PSO%2BSkyline.py) |
| TLBO+Skyline | This approach uses teaching learning based optimization algorithm with initial Skyline services for each tasks. | [TLBO+Skyline](https://github.com/IntelligentServiceLab/SQMSC/blob/main/TLBO%2BSkyline.py) |
| SQMSC-MH | This approach is a variant of SQWSC by not using a meta-heuristic algorithm, i.e., select the Skyline(compound) services. | [SQMSC-MH](https://github.com/IntelligentServiceLab/SQMSC/blob/main/SQMSC-MH.py) |

### Evalution


- [GA](https://github.com/IntelligentServiceLab/SQMSC/blob/main/GA.py), [PSO](https://github.com/IntelligentServiceLab/SQMSC/blob/main/PSO.py) and [TLBO](https://github.com/IntelligentServiceLab/SQMSC/blob/main/TLBO.py) use the original candidate set as the data input, while [GA+Skyline](https://github.com/IntelligentServiceLab/SQMSC/blob/main/GA%2BSkyline.py), [PSO+Skyline](https://github.com/IntelligentServiceLab/SQMSC/blob/main/PSO%2BSkyline.py) and [TLBO+Skyline](https://github.com/IntelligentServiceLab/SQMSC/blob/main/TLBO%2BSkyline.py) select the Skyline service in the candidate service set as the latest candidate set.
- The entire process of SQMSC-MH is to find Skyline services.
- The input data of the above code are all data in the [qws2resetIndex](https://github.com/IntelligentServiceLab/SQMSC/blob/main/qws2resetIndex.csv) dataset. The qws2resetIndex dataset is roughly the same as the real dataset QWS2. The difference is that we have disturbed its row index.
- Qws2 reset Index records eight QoS attributes, including response time, availability, throughput, successability, reliability, compliance, best practices and latency.
- When two QoS attributes are set in the experiment, response time and availability are selected; response time, availability and throughput, is selected for three; and response time, availability, throughput and successability are selected for four.

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
