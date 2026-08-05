# Applying AI to Optimize Dental Outpatient Registration Decision-Making: A Smart Tooth Mapping and Doctor Recommendation System

## 1. Introduction

Artificial intelligence (AI) has become an important technology for improving business decision-making across different industries. Organizations are increasingly using AI to improve operational efficiency, customer experience, resource allocation, and decision accuracy. In healthcare services, AI has been applied in areas such as medical assistance, patient management, and hospital operation optimization. However, one practical challenge that many outpatient hospitals still face is that patients often cannot accurately select the correct medical department during registration.

This problem is especially common in dental hospitals because dental services are divided into many specialized departments. Most patients describe their problems using everyday language, such as “my tooth hurts,” “my tooth is broken,” or “I want to repair my tooth.” However, hospitals organize dental services based on professional classifications, including Endodontics, Prosthodontics, Periodontics, and Oral Surgery. The difference between patient understanding and professional medical classification creates a decision-making gap.

For example, a patient visiting Zhongshan Guangda Dental Hospital because of tooth pain may believe that they only need a department related to tooth repair. However, according to professional dental classification, the appropriate department may actually be Endodontics if the problem involves tooth pulp inflammation or nerve-related issues. Since ordinary patients usually do not have professional dental knowledge, they may successfully obtain a registration appointment but later discover that they selected the wrong department. As a result, they may be unable to receive treatment on the scheduled day and need to register again. Because popular dental departments often have limited appointment availability, patients may need to wait several additional days before receiving appropriate treatment.

This situation creates problems for both patients and hospitals. Patients experience longer waiting times, frustration, and additional registration difficulties. Meanwhile, hospitals face inefficient appointment allocation, increased administrative workload, and reduced utilization of medical resources.

Therefore, improving outpatient registration decision-making has become an important operational management challenge. This report proposes an AI-powered dental registration decision support system that combines tooth mapping, symptom analysis, department recommendation, and doctor matching. The purpose of this system is not to replace dentists but to help patients and hospitals make more accurate registration decisions.

---

## 2. Organization Background and Decision Problem

This report focuses on a large dental hospital in China, using Zhongshan Guangda Dental Hospital as an example organization. The hospital provides various dental healthcare services, including tooth restoration, root canal treatment, orthodontics, dental cleaning, and oral surgery. With increasing demand for dental services, specialized departments often experience high appointment pressure, and patients may face difficulties when selecting available medical resources.

The major decision-making problem is that patients are required to choose professional departments without sufficient medical knowledge. Unlike dentists, ordinary patients usually cannot identify whether their symptoms are related to tooth nerves, gums, tooth structure, or other oral conditions.

For instance, a patient experiencing sensitivity when drinking cold water may assume that they only need a general dental consultation. However, the actual condition may require treatment from the Endodontics department. Similarly, a patient who wants to “repair a tooth” may need Prosthodontics instead of a simple filling service.

Incorrect registration creates several operational problems. First, doctors may receive patients whose conditions do not match their department expertise, reducing appointment efficiency. Second, patients may cancel their appointments and search for another available registration slot. Third, inaccurate registration data makes it harder for hospital managers to understand actual patient demand and optimize resource allocation.

AI can help solve this problem because it can analyze large amounts of historical healthcare information and identify relationships between symptoms, treatments, departments, and doctors. Instead of requiring patients to understand complicated medical classifications, AI can translate simple descriptions into suitable registration decisions.

---

## 3. Proposed AI Solution

The proposed solution is an AI-powered Dental Registration Decision Support System. The main goal of this system is to help patients select appropriate departments and doctors before completing registration.

The first function of the system is an interactive tooth mapping interface. Instead of asking patients to directly select medical departments, the system provides a visual dental chart. Patients can click on the specific tooth area where they feel discomfort. This design reduces confusion because patients usually understand the location of their pain better than professional department names.

After selecting the tooth position, patients answer several simple questions generated by the AI system. These questions include:

- What type of discomfort do you experience?
- Does the pain occur when eating, drinking cold water, or chewing?
- How long has the problem existed?
- Is there swelling, bleeding, or sensitivity?
- What treatment are you expecting, such as filling, cleaning, or repair?

The AI system then analyzes this information through Natural Language Processing (NLP), machine learning models, and a dental knowledge database. It compares patient information with historical registration records, treatment outcomes, and professional department classifications.

For example, if a patient selects a molar area and reports continuous pain caused by cold stimulation, the AI system may identify that the symptoms are more related to tooth pulp problems and recommend the Endodontics department.

After selecting the department, the system can further recommend suitable dentists. The recommendation algorithm can consider factors including doctor specialization, previous treatment experience, appointment availability, and patient feedback. This creates a more personalized registration experience.

The required data includes historical registration records, patient symptom descriptions, treatment results, doctor expertise information, appointment schedules, and patient satisfaction feedback. Patients can use the AI recommendation results during registration, while hospital managers can use AI insights to improve scheduling and resource planning.

---

## 4. Expected Benefits, Risks, and Evaluation

### Expected Benefits

The first expected benefit is improved operational efficiency. By reducing incorrect registrations, hospitals can improve the matching between patients and medical departments. Currently, some patients may select unsuitable departments and need to register again, creating additional workload. After implementing the AI system, the wrong registration rate could potentially decrease from approximately 15% to below 5%. This improvement may reduce ineffective registrations every day and allow doctors to focus on more suitable patients.

The second benefit is improved patient satisfaction. Many patients feel frustrated because they must understand complex medical department classifications before registration. With AI assistance, patients can receive department and doctor recommendations through a simple interactive process. The average registration decision time is expected to decrease from around 5 minutes to less than 1 minute, while patient satisfaction may improve by approximately 10% to 15%.

The third benefit is improved resource planning. By analyzing registration patterns, AI can help hospital managers predict department demand and adjust doctor schedules. For example, increasing demand for tooth pain-related treatment may indicate the need for more Endodontics appointments.

---

### AI Risks and Ethical Issues

The first risk is patient data privacy. The AI system processes sensitive healthcare information, including symptoms and treatment history. Hospitals must protect this information through encryption, access control, and strict data management policies.

The second risk is algorithm bias. If AI training data mainly comes from specific hospitals or patient groups, recommendations may not perform equally well for all users. Differences in age, language expression, or medical background may influence accuracy. Therefore, continuous monitoring and improvement are required.

The third risk is employee acceptance and organizational change. The AI recommendation system may change the workflow of front-desk staff, nurses, and patient guidance employees. Some employees may worry that AI reduces the importance of their professional judgment or feel uncomfortable using new technology. If employees do not actively participate, the system effectiveness may be limited. To reduce this risk, hospitals should provide training before implementation, explain that AI is an assistance tool rather than a replacement, and involve frontline employees in testing and feedback.

Another concern is over-reliance on AI. Patients and employees may assume that AI recommendations are always correct. Therefore, the system should clearly explain that AI supports registration decisions but cannot replace professional dental diagnosis.

---

### Evaluation KPIs

The AI system can be evaluated through the following KPIs:

1. **Wrong Registration Rate:**  
Measures whether incorrect department selection decreases after AI implementation.

2. **Patient Satisfaction Score:**  
Evaluates whether patients experience a better registration process.

3. **Registration Decision Time Reduction:**  
Measures whether AI reduces the time required to select departments and doctors.

4. **AI Recommendation Accuracy:**  
Measures whether recommended departments and doctors match professional decisions.

5. **Hospital Resource Utilization Efficiency:**  
Evaluates whether appointment resources are allocated more effectively.

6. **Staff Adoption Rate:**  
Measures the percentage of nurses and registration employees actively using the AI system. The target is to achieve more than 80% employee adoption within three months after implementation.

---

## 5. Conclusion

In conclusion, incorrect outpatient registration is an important operational challenge for dental hospitals because patients often lack professional knowledge when selecting departments. This problem affects patient satisfaction, increases administrative workload, and reduces hospital efficiency.

The proposed AI-powered dental registration decision support system provides a practical solution by combining tooth mapping, symptom analysis, department recommendation, and doctor matching. Instead of replacing healthcare professionals, AI works as a decision-support tool that improves decision quality for both patients and hospitals.

However, successful AI implementation requires attention to privacy protection, algorithm fairness, employee acceptance, and responsible technology management. Therefore, the hospital should first conduct a three-month pilot project in one department, such as Endodontics, collect operational data, evaluate system performance, and optimize the model before gradually expanding the system to other departments.

With appropriate implementation and continuous improvement, this AI solution can improve outpatient management efficiency, enhance patient experience, and support smarter healthcare decision-making.

