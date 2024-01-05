
1. Create resources in API Gateway:

2. First Resource: /employee

3. First Method: POST method
![image](https://github.com/itsnehagarg/AWSProjects/assets/20385826/e4e8a51f-9f52-458f-b297-029fd7ef670f)

![image](https://github.com/itsnehagarg/AWSProjects/assets/20385826/374f0146-548a-4648-88df-5845fb5022f1)


4. Create a new resource: /employee/empID

![image](https://github.com/itsnehagarg/AWSProjects/assets/20385826/23c331c2-ea49-478b-b925-9110faca6173)

5. Now create a GET method for the above resource. Select the resource and click on Create method button.

![image](https://github.com/itsnehagarg/AWSProjects/assets/20385826/1ab52bdc-148f-478c-87c5-de2fe6c8df10)

6. After creating all the resources and methods click on Deploy API:

![image](https://github.com/itsnehagarg/AWSProjects/assets/20385826/2e22c988-af80-45db-a695-105585000489)

7. REST APIs can be tested with the respective endpoints that are created.
8. generate a jar file by running your java code.
9. Go to AWS Lambda and deploy the jar file.
10. Go to Code-> Upload From-> .zip or .jar file
11. ![image](https://github.com/itsnehagarg/AWSProjects/assets/20385826/f3fe4404-3e93-47eb-a68a-c9866c696ac6)
12. Now go to runtime settings and change the handler.
13. Change handler by clicking on Edit: com.app.easy2excel.LambdaHandler::handleRequest (packagename.classname::functioname)
14. ![image](https://github.com/itsnehagarg/AWSProjects/assets/20385826/10db074b-6cfe-4619-8bfd-0141290c9797)
15. Now we will take the endpoints from API gateway and start using them on POSTMAN.
16. Start by POST request and pass the json object in the body.
    {
    "empId": "101",
    "name": "Neha",
    "email": "itsnehagarg"

}
17. Check the DynamoDB for data
18. Click on Explore Table Items.
![image](https://github.com/itsnehagarg/AWSProjects/assets/20385826/5e68444d-9501-4cd1-823d-f1ef1f3d7f49)

19. ![image](https://github.com/itsnehagarg/AWSProjects/assets/20385826/5db8e388-d4a9-40a0-9688-50a6bb61fc71)
20. Next is Resource clean up in AWS.
21. Monitor the Cloudwatch logs.
22. Go to Lambda
23. Click on Monitor-> View CloudWatch logs
24. ![image](https://github.com/itsnehagarg/AWSProjects/assets/20385826/1ff21a50-5b61-4116-b4b3-5d4feb787821)

25. ![image](https://github.com/itsnehagarg/AWSProjects/assets/20385826/5b14f3ed-5468-4035-9d4c-273c0504e8da)








