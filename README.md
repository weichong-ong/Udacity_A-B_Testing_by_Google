# Udacity A/B Testing by Google

This is the final project of the [A/B testing course](https://www.udacity.com/course/ab-testing--ud257) from Udacity in collaboration with Google. This project covers experiment design and results analysis of a A/B test titled "Free Trial Screener", which was performed by Udacity.

## Project Outline
### **Part I: Experiment Design:**
1. Metric Choice - Invariants Metrics, Evaluation Metrics
2. Measuring Variability of Evaluation Metrics
3. Sizing - Number of Samples vs. Power, Duration vs. Exposure

### **Part II: Experiment Analysis:**
1. Sanity Checks - Population Sizing Invariants, Probability Invariants
2. Results Analysis - Effect Size Tests, Sign Tests
3. Results Intepretation
4. Recommendation

## Experiment Overview: Free Trial Screener
### Existing Signup Process
At the time of this experiment, Udacity courses currently have two options on the course overview page: **"start free trial"**, and **"access course materials"**.
* If the student clicks **"start free trial"**, they will be asked to enter their credit card information, and then they will be enrolled in a free trial for the paid version of the course. After 14 days, they will automatically be charged unless they cancel first.
* If the student clicks **"access course materials"**, they will be able to view the videos and take the quizzes for free, but they will not receive coaching support or a verified certificate, and they will not submit their final project for feedback.

### A/B Test
In the experiment, Udacity tested a change where if the student clicked "start free trial", they were asked how much time they had available to devote to the course.
* If the student indicated 5 or more hours per week, they would be taken through the checkout process as usual.
* If they indicated fewer than 5 hours per week, a message would appear indicating that Udacity courses usually require a greater time commitment for successful completion, and suggesting that the student might like to access the course materials for free. At this point, the student would have the option to continue enrolling in the free trial, or access the course materials for free instead. This screenshot shows what the experiment looks like.

### Hypothesis
The hypothesis was that this might set clearer expectations for students upfront, thus reducing the number of frustrated students who left the free trial because they didn't have enough time — without significantly reducing the number of students to continue past the free trial and eventually complete the course. If this hypothesis held true, Udacity could improve the overall student experience and improve coaches' capacity to support students who are likely to complete the course.

### Unit of Diversion
The unit of diversion is a cookie, although if the student enrolls in the free trial, they are tracked by user-id from that point forward. The same user-id cannot enroll in the free trial twice. For users that do not enroll, their user-id is not tracked in the experiment, even if they were signed in when they visited the course overview page.

## Dataset
This dataset contains the raw information needed to compute the above metrics, broken down day by day. Note that there are data for both the control group and the experiment group, with suffix _cont and _exp respectively.
* **Pageviews:** Number of unique cookies to view the course overview page that day.
* **Clicks:** Number of unique cookies to click the course overview page that day.
* **Enrollments:** Number of user-ids to enroll in the free trial that day.
* **Payments:**
 Number of user-ids who who enrolled on that day to remain enrolled for 14 days and thus make a payment. (Note that the date for this column is the start date, that is, the date of enrollment, rather than the date of the payment. The payment happened 14 days later. Because of this, the enrollments and payments are tracked for 14 fewer days than the other columns.)

For further reading about A/B Testing:
- [A/B Testing Guide](https://vwo.com/ab-testing/)
- [The Complete Guide To A/B Testing & Split Testing (2020)](https://www.convertize.com/ab-testing/)
