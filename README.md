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
### 3. Evalution
- Optimality with different number of QoS properties.

|  | 2 | 3 | 4 |
| :----: | :----: | :----: | :----: |
| SQMSC_MH | 97.83849075818293 | 91.84538563779238 | 90.64903784735586 |
| SQMSC | 87.4897763826431 | 82.32303283641438 | 80.26780550090027 |
| GA | 68.73259440154652 | 67.55399216342042 | 63.903419043016584 |
| GA+Skyline | 76.40572766805778 | 73.10892655823812 | 73.27862993013107 |
| PSO | 60.51195854721643 | 55.17907841495449 | 51.487213804391594 |
| PSO+Skyline | 69.58074795236917 | 66.57342985648108 | 63.90600935676791 |
| TLBO | 69.68441389201915 | 56.56176677600886 | 50.416221131933625 |
| TLBO+Skyline | 74.60445890990269 | 65.0304569811683 | 51.270468647746725 |
- Optimality with different number of service candidates.
- Scalability with different number of QoS properties.
- Scalability with different number of service candidates.



- The input data of the above code are all data in the [qws2resetIndex](https://github.com/IntelligentServiceLab/SQMSC/blob/main/qws2resetIndex.csv) dataset. The qws2resetIndex dataset is roughly the same as the real dataset QWS2. The difference is that we have disturbed its row index.
- Qws2 reset Index records eight QoS attributes, including response time, availability, throughput, successability, reliability, compliance, best practices and latency.


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
