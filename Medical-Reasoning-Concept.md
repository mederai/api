## Medical Reasoning Concept

The first step to utilize the diagnostic engine is to feed three required observation factors: gender, age, and one or multiple symptoms to our API endpoint `/engdiag`. 

> The initial screening values `{age, sex, evidence}` will be stored in until the 


### MMDE techniques and workflow 
![1.png](https://medera.stoplight.io/api/v1/projects/cHJqOjMyMzQx/images/QxzJTIl3loQ)



### Example
A 27 years old female has an ear pain, and it became worse when it pressed around the ear.

<!-- 
type: tab
title: Request
-->

```json
{
  "age": 27,
  "evidence": [
    {
      "choice_id": "present",
      "id": "symptom_dg"
    }
  ],
  "sex": "female"
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
            "text": "Does the pain irritate when you press it around your ear?",
            "items": [
                {
                    "id": "symptom_dgf",
                    "name": "Pain increases when pressing around ear",
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
                "prob": 0.0708
            }
        ],
        "queue": [
          {
              "queue_id": "762347836hjsdg873643",
              "transition_id": "20220105115001"
          }
        ]
    }
}
```
<!-- type: tab-end -->





