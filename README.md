-- USE hospital;

-- question 1.1: Total number of patient admissions
-- SELECT COUNT(*) AS total_admissions
-- FROM admissions;

-- question 1.2: Average length of stay (difference between discharge date and admission date)
-- SELECT AVG(DATEDIFF(d.discharge_date, a.admission_date)) AS avg_length_of_stay
-- FROM admissions a
-- JOIN discharges d ON a.admission_id = d.admission_id;

-- question 2.1: Total number of admissions by primary diagnosis
-- SELECT primary_diagnosis, COUNT(*) AS total_admissions
-- FROM admissions
-- GROUP BY primary_diagnosis;

-- question 2.2: Average length of stay by service
-- SELECT a.service, AVG(DATEDIFF(d.discharge_date, a.admission_date)) AS avg_length_of_stay
-- FROM admissions a
-- JOIN discharges d ON a.admission_id = d.admission_id
-- GROUP BY a.service;

-- question 2.3: Count of discharges by discharge disposition
-- SELECT discharge_disposition, COUNT(*) AS total_discharges
-- FROM discharges
-- GROUP BY discharge_disposition;

-- question 3.1: Services with total number of admissions greater than 5
-- SELECT service, COUNT(*) AS total_admissions
-- FROM admissions
-- GROUP BY service
-- HAVING total_admissions > 5;

-- question 3.2: Average length of stay for "Stroke" patients
-- SELECT AVG(DATEDIFF(d.discharge_date, a.admission_date)) AS avg_length_of_stay
-- FROM admissions a
-- JOIN discharges d ON a.admission_id = d.admission_id
-- WHERE a.primary_diagnosis = 'Stroke';

-- question 4.1: Total emergency department visits by acuity
-- SELECT acuity, COUNT(*) AS total_visits
-- FROM ed_visits
-- GROUP BY acuity;

-- question 4.2: Total number of admissions by primary diagnosis and service
-- SELECT primary_diagnosis, service, COUNT(*) AS total_admissions
-- FROM admissions
-- GROUP BY primary_diagnosis, service;

-- question 5.1: Total admissions per month
-- SELECT MONTH(admission_date) AS month, COUNT(*) AS total_admissions
-- FROM admissions
-- GROUP BY MONTH(admission_date);

-- question 5.2: Maximum length of stay for each primary diagnosis
-- SELECT a.primary_diagnosis, MAX(DATEDIFF(d.discharge_date, a.admission_date)) AS max_length_of_stay
-- FROM admissions a
-- JOIN discharges d ON a.admission_id = d.admission_id
-- GROUP BY a.primary_diagnosis;

-- Bonus challenge: Total and average length of stay by service, ordered by highest average length of stay
-- SELECT a.service, 
       -- SUM(DATEDIFF(d.discharge_date, a.admission_date)) AS total_length_of_stay,
       -- AVG(DATEDIFF(d.discharge_date, a.admission_date)) AS avg_length_of_stay
-- FROM admissions a
-- JOIN discharges d ON a.admission_id = d.admission_id
-- GROUP BY a.service
-- ORDER BY avg_length_of_stay DESC;



