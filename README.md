## SQMSC: Scalable QoS-aware Manufacturing Service Composition Optimization Approach via Business Process Decomposition
### 1. Motivation
With the development of service-oriented manufacturing model, more and more manufacturing services are released through manufacturing service platform. It is well known that the QoS-aware manufacturing service composition problem is NP-hard. Therefore, optimization remains a challenging research problem, especially in the case of large-scale manufacturing service data, which also raises scalability issues. In order to improve the optimization performance and scalability of QoS-aware manufacturing service composition, we think of a scalable QoS-aware manufacturing service composition optimization method based on business process decomposition to solve the problem step by step.[SQMSC code](https://github.com/IntelligentServiceLab/SQMSC/blob/main/SQMSC.py)

### 2. SQMSC architecture
<div align=center><img width="600" height="400" src="SQMSC_Framework.png"/></div>

### 3. Setup and Dataset
- Setup

All experiments are implemented on a PC with AMD Ryzen 5, CPU 2.38GHZ, and 16G RAM, running on Windows 10 x64 with Python 3.9.
- Dataset

The data set we use is the first web service data set introduced in 2007 to measure the quality of service (QoS) of real web services. The main goal of this data set is to provide a foundation for web services researchers. Web services are collected using the Web Services Crawler Engine (WSCE). Most of these services are obtained from public sources on the web, including the Universal Description, Discovery and Integration (UDDI) registry, search engines, and service portals.[Click here to go directly to the official website of the dataset](https://qwsdata.github.io/)
- Characteristics of the database

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

### 4. Baseline
| Baselines | Description | Code |
| :-----: | :---- | :----: |
| GA | This approach uses genetic algorithm. | [GA code](https://github.com/IntelligentServiceLab/SQMSC/blob/main/GA.py) |
| PSO | This approach uses particle swarm optimization algorithm. | [PSO code](https://github.com/IntelligentServiceLab/SQMSC/blob/main/PSO.py) |
| TLBO | This approach uses teaching learning based optimization algorithm. | [TLBO code](https://github.com/IntelligentServiceLab/SQMSC/blob/main/TLBO.py) |
| Skyline+GA | This approach uses genetic algorithm with initial Skyline services for each tasks. | [Skyline+GA code](https://github.com/IntelligentServiceLab/SQMSC/blob/main/GA%2BSkyline.py) |
| Skyline+PSO | This approach uses particle swarm optimization algorithm with initial Skyline services for each tasks. | [Skyline+PSO code](https://github.com/IntelligentServiceLab/SQMSC/blob/main/PSO%2BSkyline.py) |
| Skyline+TLBO | This approach uses teaching learning based optimization algorithm with initial Skyline services for each tasks. | [Skyline+TLBO code](https://github.com/IntelligentServiceLab/SQMSC/blob/main/TLBO%2BSkyline.py) |
| SQMSC-MH | This approach is a variant of SQWSC by not using a meta-heuristic algorithm, i.e., select the Skyline(compound) services. | [SQMSC-MH code](https://github.com/IntelligentServiceLab/SQMSC/blob/main/SQMSC-MH.py) |

### 5. Parameters
#### GA、Skyline+GA：
- candidate_number: Number of services in candidate set of each subtask,
- crossover_probability
- mutation_probability
- task_number
- population_size
#### PSO、Skyline+PSO：
- w: Inertia weight
- c1 and c2: Learning factor
- Vmax: speed limit
- task_number
- population_size
#### TLBO、Skyline+TLBO
- task_number
- population_size
#### SQWSC
- n: Number of QoS attributes
- candidate_number: Number of services in candidate set of each subtask
- crossover_probability
- mutation_probability
- task_number
- population_size

### 6. Evalution
- Optimality with different number of QoS properties.

|  | 2 | 3 | 4 |
| :----: | :----: | :----: | :----: |
| SQMSC-MH | 97.8385 | 91.8454 | 90.6490 |
| SQMSC | 87.4898 | 82.3230 | 80.2678 |
| GA | 68.7326 | 67.5540 | 63.9034 |
| Skyline+GA | 76.4057 | 73.1089 | 73.2786 |
| PSO | 60.5120 | 55.1791 | 51.4872 |
| Skyline+PSO | 69.5807 | 66.5734 | 63.9060 |
| TLBO | 69.6844 | 56.5618 | 50.4162 |
| Skyline+TLBO | 74.6045 | 65.0305 | 51.2705 |
- Optimality with different number of service candidates.

|  | 20 | 40 | 60 | 80 | 100 |
| :----: | :----: | :----: | :----: | :----: | :----: |
| SQMSC-MH | 92.0860 | 91.7786 | 88.2668 | 92.3652 | 92.4901 |
| SQMSC | 83.3570 | 85.7311 | 87.4752 | 87.7056 | 88.5439 |
| GA | 57.7794 | 58.6891 | 59.3579 | 61.8693 | 70.6284 |
| Skyline+GA | 58.5899 | 58.8638 | 63.4255 | 64.9969 | 71.4467 |
| PSO | 47.4239 | 49.3324 | 49.0590 | 50.0277 | 48.0088 |
| Skyline+PSO | 54.9274 | 59.1225 | 60.3356 | 58.3696 | 59.8917 |
| TLBO | 49.7458 | 54.6718 | 54.3177 | 52.9886 | 55.0391 |
| Skyline+TLBO | 53.7462 | 62.4483 | 67.3125 | 71.6387 | 70.8014 |
- Scalability with different number of QoS properties.

|  | 2 | 3 | 4 |
| :----: | :----: | :----: | :----: |
| SQMSC-MH | 1.8742 | 44.2981 | 67.1026 |
| SQMSC | 6.4383 | 10.2967 | 12.1537 |
| GA | 31.3528 | 42.1678 | 49.8742 |
| Skyline+GA | 16.5237 | 22.7194 | 27.1542 |
| PSO | 55.3634 | 63.7341 | 66.3038 |
| Skyline+PSO | 44.5544 | 50.0404 | 53.5290 |
| TLBO | 36.6394 | 44.0374 | 52.7721 |
| Skyline+TLBO | 31.0637 | 26.7600 | 30.4317 |
- Scalability with different number of service candidates.

|  | 20 | 40 | 60 | 80 | 100 |
| :----: | :----: | :----: | :----: | :----: | :----: |
| SQMSC-MH | 0.6002 | 35.6901 | 41.6337 | 53.0130 | 72.1134 |
| SQMSC | 8.7623 | 11.9560 | 13.0734 | 14.2059 | 15.0659 |
| GA | 39.2844 | 41.1659 | 44.5955 |46.3848| 42.3831 |
| Skyline+GA | 20.2149 | 18.4588 | 21.6778 | 23.3793 | 24.8068 |
| PSO | 58.4865 | 60.6950 | 61.4482 | 64.6943 | 65.4754 |
| Skyline+PSO | 44.8885 | 49.7468 | 52.0475 | 55.1355 | 56.4389 |
| TLBO | 33.8722 | 47.9587 | 48.4563 | 51.2441 | 57.3289 |
| Skyline+TLBO | 22.4987 | 25.4216 | 26.5534 | 29.7678 | 32.1033 |

- Running time of each component in Alg. 1 with different number of QoS properties

|  | 2 | 3 | 4 |
| :----: | :----: | :----: | :----: |
| Select Subtask Service | 0.0092 | 0.0098 | 0.0110 |
| Select Composite Task Service | 0.0788 | 1.3439 | 1.3239 |
| Genetic Algorithm | 9.1889 | 12.7778 | 15.4186 |
- Running time of each component in Alg. 1 with different number of service candidates

|  | 20 | 40 | 60 | 80 | 100 |
| :----: | :----: | :----: | :----: | :----: | :----: |
| Select Subtask Service | 0.0060 | 0.0093 | 0.0133 | 0.0171 | 0.0250 |
| Select Composite Task Service | 0.3280 | 1.6510 | 2.6587 | 5.3516318 | 5.7596 |
| Genetic Algorithm | 7.9854 | 10.0133 | 11.3622 | 13.4245 | 15.0115 |

### 6. Supplemental instruction
- The input data of the above code are all data in the [qws2resetIndex](https://github.com/IntelligentServiceLab/SQMSC/blob/main/qws2resetIndex.csv) dataset. The qws2resetIndex dataset is roughly the same as the real dataset QWS2. The difference is that we have disturbed its row index.
- Qws2 reset Index records eight QoS attributes, including response time, availability, throughput, successability, reliability, compliance, best practices and latency.

### 7. Note：
- If you have any question about my code or want to share your idea, you can send email to me. Welcome at any time!
- Email: jiayanxiang02@gmail.com
