# Time-Series-Anomaly-Detection-In-Industry-and-Quality-Assurance
This Time Series Anomaly detection project mainly focuses on Energy sector datasets. 

The project is done under the guidance of Professor Ye Zhu, Senior Lecturer of Computer Science - School of Information Technology, Deakin University, Australia.

We used the models TadGAN (Time Series Anomaly Detection) and AER (Auto Encoder with Regression) for this task. Both the models are from ["Orion Library" of Data to AI Lab, of MIT](https://github.com/sintel-dev/Orion). In the project, at first we reproduced the model results on the datasets given in research papers, then we benchmarked them on various labelled energy sector datasets and also did extensive Hyper-parameter Sensitivity analysis. You can find our paper here: https://zenodo.org/records/19339214.

We explored the following datasets for our experiments:

1. **NASA Space Telemetry Dataset**
   - A dataset consisting of telemetry data from NASA's spacecraft, useful for anomaly detection and predictive maintenance.
   - Dataset: Directly available in orion library. Can see their repo and notebook for usage.

2. **SCADA 2015 Wind Turbine Dataset**
   - Data collected from wind turbines, including measurements of temperature, power output, and other variables, aimed at detecting anomalies and predicting failures.
   - Dataset: https://github.com/lkev/wtphm/blob/master/examples/scada_data.csv

3. **Power Laws: Anomaly Detection Dataset**
   - A dataset designed for evaluating anomaly detection algorithms, featuring data with known power-law distributions.
   - Dataset: https://github.com/drivendataorg/power-laws-anomalies
   - (available in schneider electric website, create account to get). Did not evaluate the model on it, as we did not know true labels other than visual information, so just visually tested.

4. **Machine Temperature Failure Dataset**
   - Contains temperature measurements from industrial machines, used to study machine failures and predict potential breakdowns.
   - Dataset: https://github.com/numenta/NAB/blob/master/data/realKnownCause/machine_temperature_system_failure.csv

5. **Large-scale Energy Anomaly Detection (LEAD)**
   - A comprehensive dataset for large-scale anomaly detection in energy systems, including various sensors and measurements from energy grids.
   - https://github.com/samy101/lead-dataset/tree/main/data
   - [did analysis on 2 buildings and also not on the whole dataset, rather on a particular chunk of it]
   
**In this repository we have provided :---------------**

**1.** Notebooks used by us

**2.** Source of Datasets

**3.** The official research papers for the models


**---------------: Official Research Papers :---------------**

1. [TadGAN](https://arxiv.org/abs/2009.07769)

2. [AER](https://arxiv.org/abs/2212.13558)
   

**---------------: Other Library Links :---------------**

[WTPHM Library source](https://github.com/lkev/wtphm)

[Tulog Notebook](https://github.com/sintel-dev/Orion/blob/master/tutorials/tulog/Tulog.ipynb)


**---------------:Other Notebooks referred:---------------**

[Preprocessing of SCADA events data using WTPHM library](https://colab.research.google.com/drive/1NRHN73jdoALxo8PHY8h-mumlR0S2p_Rf?usp=sharing)


**--------------- The Notebooks --------------**

**TadGAN Notebooks :---------------** 


1) [TadGAN results on NASA dataset (S1,P15))](https://www.kaggle.com/code/chiradipbiswas/nasa-tadgan-direct-stat)
   
2) [TadGAN results on NASA data (P1),version-3,4 for model on directly applied on data, version-1 for model on decomposed P-1 data](https://www.kaggle.com/code/chiradipbiswas/tadgan-on-p1-contextual)

3) [TadGAN on Power Laws Anomalies Dataset, model pipeline directly applied on data](https://colab.research.google.com/drive/1OD9K74qk0fMOJIGNdl7HtV48GD0YCO_b?usp=sharing)
  
4) [TadGAN directly applied on SCADA turbine-21 dataset, versions 9,11,12 for best results using 2x of the original time interval](https://www.kaggle.com/code/chiradipbiswas/scada-dataset-turbine21-wtphm-tadgan)
  
5) [TadGAN on SCADA turbine-21 dataset after using EWMA](https://www.kaggle.com/code/chiradipbiswas/exponentially-weighted-ma-tadgan)
    
6) [TadGAN directly on SCADA turbine-22 data, version 17 onwards using smaller window and 2x of the original time interval, version 15,16 for best and consistent results](https://www.kaggle.com/code/chiradipbiswas/scada-dataset-turbine22-tadgan-wtphm)
    
7) [TadGAN directly on turbine 22 data (some initial experiments)](https://colab.research.google.com/drive/1QhDv37hSBlzyqGjTRsbfzgz-xZ81ufhy?usp=sharing)
    
8) [TadGAN on SCADA turbine 22 EWMA](https://www.kaggle.com/code/chiradipbiswas/scada-dataset-turbine22-tadgan-wtphm-ewma)
    
9) [TadGAN on Machine Temperature failure dataset, both direct and EWMA applied](https://www.kaggle.com/code/chiradipbiswas/machine-temp-fail-tadgan)
    
10) [TADGAN LEAD 108](https://colab.research.google.com/drive/1HsMCY2wP-cZJ-N2Jp7ni1WGQNT5lC9IQ?usp=sharing)

11) [TADGAN LEAD 107](https://colab.research.google.com/drive/1u-i7pYnNFN-_4_M7Ck1460EyDKP_whth?usp=sharing)

12) [TADGAN LEAD 139](https://colab.research.google.com/drive/1351mvPSkueD1XtXr7YMCnR02_EVXBeeV?usp=sharing)

13) [building 139 tuning for window](https://colab.research.google.com/drive/1Q5NPAfn_r9F6LvPLR4op-apYs3uCqogl?usp=sharing)
    
14) [tadgan 139 batch size 32](https://colab.research.google.com/drive/1Q0_7jZVzu854bUeDnEel7WwzPO_M5KCF?usp=sharing)

15) [EPOCH tadgan lead 139](https://colab.research.google.com/drive/15fKARj8QoCEPyX-a7Nyl4Xzoy9Ooa0Qh?usp=sharing)
    
16) [tadgan LEAD 139 iter-critic](https://colab.research.google.com/drive/1Qbi-F566GSOHo8BZ_JrLsUsTcFDib0ep?usp=sharing)
    
17) [tadgan LEAD-139 window](https://colab.research.google.com/drive/1AdljD3nW9W4lyQ4XyQSl9cYrbZIY2z-c?usp=sharing)

18) [tadgan LEAD 139 epochs_20](https://colab.research.google.com/drive/1E1ROUrJ6MxUvCVzIeZ5sc4u90tYBMDpa?usp=sharing)



**AER Notebooks :---------------**

1)[AER directly on P15 and S1 data](https://colab.research.google.com/drive/1azG1-8u8vFsLH2aPq3EZV1HqcCT0t5XV?usp=sharing)
   
2)[AER directly on P1 data(best) result](https://colab.research.google.com/drive/1X6zOw0WYbobdWeZcgTVlLB874-JZ7Lhv?usp=sharing)

3)[AER directly on P1 data (notebook for computing model stats)](https://colab.research.google.com/drive/10s1BfSx9nbJlKT3HweAFC3G46zVCfqcQ?usp=sharing)

4)[AER directly on P1 with time interval twice, best results](https://colab.research.google.com/drive/1pLTSRGlePLylmOpZvS-pjdKuuBz2w4JT?usp=sharing)

5)[AER on Decomposed P1 data](https://colab.research.google.com/drive/1quP3sAKe_si6HOjhIySb33y_GAPibG4G?usp=sharing)

6)[AER on decomposed P1 data time interval 2x](https://colab.research.google.com/drive/1Dx31RFuDWro2Ub9V7FllAthTAJhrDsBd?usp=sharing)

7)[AER p1 data decomposed epochs changed](https://colab.research.google.com/drive/1NibQ1gWuEl-hd0R95u8GuJlIUWGOgcTm?usp=sharing)

8)[AER on Power Law Anomalies Dataset](https://www.kaggle.com/code/chiradipbiswas/schneider-dataset-aer)

9)[Turbine 21 EDA](https://colab.research.google.com/drive/1_H0E3IHOW1TfGlIr_R-GzchPLvpTyFuv?usp=sharing)

10)[AER directly on SCADA turbine 21 dataset](https://colab.research.google.com/drive/1GHRRm1LCVMFG65wmw8h9b574WE0vUneF?usp=sharing)

11)[AER directly on turbine-21 with double_time interval](https://colab.research.google.com/drive/1F8NtxbUOkQW8VxLJ7kr5efJl4zvxARAH?usp=sharing)

12)[AER directly on SCADA turbine 21 dataset (changed step size experiment)](https://colab.research.google.com/drive/1KYhieBA15VvyQ9Xq3twHf0p408kpkk2q?usp=sharing)

13)[AER on EWMA applied SCADA turbine 21 dataset](https://www.kaggle.com/code/chiradipbiswas/exponential-weight-ma-on-scada-aer)

14)[EDA on SCADA turbine 22](https://colab.research.google.com/drive/1x92h1Q-hYEIYnj9SoSHE7QVPeTti9Jvw?usp=sharing)

15)[AER on SCADA turbine 22 dataset (feature selecting experiments)](https://colab.research.google.com/drive/13ILS0mkKJ3cQKxyFrXEmksVhSlq9GZ7c?usp=sharing)

16)[AER on SCADA turbine 22 dataset (reg_ratio,window size changing and better performance)](https://colab.research.google.com/drive/1GEEuPDSGYeueYB1k1n0lvIeTR9l0a9e-?usp=sharing)

17)[AER on SCADA turbine 22 (reg-ratio changing)](https://colab.research.google.com/drive/1D2PJ8FLrPX5c5CgKCwB5CCNVf772noZC?usp=sharing)

18)[AER on Machine Temperature Failure Dataset (both directly on data and EWMA applied data) last 3 versions have best results](https://www.kaggle.com/code/chiradipbiswas/machine-temperature-system-failure-aer)

19)[AER on Machine Temperature Failure Dataset (experimenting purpose)](https://colab.research.google.com/drive/1kDTpiHkQZtCp1M9Vvl3wAaNB-w0rRnC_?usp=sharing)

20)[AER on LEAD (107) for some hyperparameters (error type, error comb, lambda, window-size, reg-ratio, batch-size, step-size)](https://www.kaggle.com/code/devoditac/aer-lead-107-tuning)

21)[AER on LEAD (139) for some hyperparameters (error type, error comb, lambda, window-size, reg-ratio, batch-size, step-size)](https://www.kaggle.com/code/devoditac/aer-lead-139-tuning)

22)[AER machine-temperature-system-failure (Step_size)](https://www.kaggle.com/code/devoditac/machine-temperature-system-failure-aer-step)

23)[AER 108 LEAD](https://colab.research.google.com/drive/1bFgbfYIz0jSWpfgSP4EPuosaD3mDSNXP?usp=sharing)
    
24)[eda_and performance improvement for AER LEAD 108](https://colab.research.google.com/drive/1V4Rn-aE4lXdTTIT62p26ZQpgNoqkZ7H6?usp=sharing)





