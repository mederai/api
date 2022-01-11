## Medical Reasoning Concept

The first step to utilize the diagnostic engine is to feed three required observation factors: gender, age, and one or multiple symptoms to our API endpoint `/engdiag`. 


### MMDE techniques and workflow 
![1.png](https://medera.stoplight.io/api/v1/projects/cHJqOjMyMzQx/images/QxzJTIl3loQ)




## Concept of Classification
The first step to utilize the diagnostic engine is to feed three required observation factors: Gender, Age, and one or multiple Symptoms to our API endpoint `/engdiag`. For example:



<!-- 
type: tab
title: Request
-->

```json
{
  "age": 0,
  "evidence": [
    {
      "choice_id": "string",
      "id": "string"
    }
  ],
  "sex": "string"
}
```

<!-- 
type: tab
title: Response
-->
```json
{
    "success": true,
    "content": {
        "question": {
            "type": "single",
            "text": "Does the pain worsen when you touch or press around your ear?",
            "items": [
                {
                    "id": "symptom_dgf",
                    "name": "Pain increases when touching ear area",
                    "choices": [
                        {
                            "id": "present",
                            "label": "Yes"
                        },
                        {
                            "id": "absent",
                            "label": "No"
                        },
                        {
                            "id": "unknown",
                            "label": "Don't know"
                        }
                    ]
                }
            ],
            "extras": {}
        },
        "conditions": [
            {
                "id": "condition_hg",
                "name": "Common cold",
                "common_name": "Common cold",
                "probability": 0.0708
            }
        ],
        "extras": {}
    }
}
```
<!-- type: tab-end -->





