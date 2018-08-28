---
swagger: "2.0"
x-collection-name: ParallelDots
x-complete: 0
info:
  title: ParallelDots Phrase Extractor
  description: |-
    # Introduction
    What does your API do?

    Get phrase keywords from the text in the input.

    # Overview
    Things that the developers should know about

    The API accepts the input parameters as form-data.

    Response will be in JSON as shown below:

    ```
    {
        "keywords": [
            {
                "relevance_score": 1,
                "keyword": "Ronaldo"
            },
            {
                "relevance_score": 2,
                "keyword": "Principality Stadium"
            },
            {
                "relevance_score": 1,
                "keyword": "Cardiff"
            },
            {
                "relevance_score": 1,
                "keyword": "last"
            },
            {
                "relevance_score": 1,
                "keyword": "June"
            },
            {
                "relevance_score": 2,
                "keyword": "Real Madrid"
            },
            {
                "relevance_score": 1,
                "keyword": "its"
            },
            {
                "relevance_score": 2,
                "keyword": "third champions"
            },
            {
                "relevance_score": 2,
                "keyword": "League trophy"
            }
        ],
        "usage": "By accessing ParallelDots API or using information generated by ParallelDots API, you are agreeing to be bound by the ParallelDots API Terms of Use: http://www.paralleldots.com/terms-and-conditions"
    }

    ```

    # Authentication
    What is the preferred way of using the API?

    An API key is required to be sent as a parameter to authenticate your requests.


    # Rate limit
    Is there a limit to the number of requests an user can send?

    There is no rate limit as such but too many concurrent requests will throw 504 time-out error from nginx.
  version: 1.0.0
host: apis.paralleldots.com
basePath: /v3
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /sentiment:
    post:
      summary: Sentiment
      description: |-
        # Introduction
        What does your API do?

        Sentiment API accepts input text, language code and API key to return a JSON response classifying the input text into a sentiment.

        # Overview
        Things that the developers should know about

        The API accepts the input parameters as form-data.Languages supported are German (de), French (fr), Dutch (nl), Italian (it), Spanish (es), Chinese (zh), Portuguese (pt), Japanese (ja), Indonesian (id), Thai (th), Danish (da), Finish (fi)

        Response will be in JSON sorted by confidence score as shown below:

        ```
        {
            "probabilities": {
                "positive": 0.241,
                "neutral": 0.304,
                "negative": 0.454
            },
            "usage": "By accessing ParallelDots API or using information generated by ParallelDots API, you are agreeing to be bound by the ParallelDots API Terms of Use: http://www.paralleldots.com/terms-and-conditions",
            "sentiment": "negative"
        }
        ```

        # Authentication
        What is the preferred way of using the API?

        An API key is required to be sent as a parameter to authenticate your requests.


        # Rate limit
        Is there a limit to the number of requests an user can send?

        There is no rate limit as such but too many concurrent requests will throw 504 time-out error from nginx.
      operationId: SentimentPost
      x-api-path-slug: sentiment-post
      parameters:
      - in: formData
        name: api_key
      - in: formData
        name: lang_code
      - in: formData
        name: text
      responses:
        200:
          description: OK
      tags:
      - Machine Learning
      - Sentiment
  /emotion:
    post:
      summary: Emotion
      description: |-
        # Introduction
        What does your API do?

        Sometimes the three classes of sentiment (positive, negative and neutral) are not sufficient to understand the nuances regarding the underlying tone of a sentence. Our Emotion Analysis classifier is trained on our proprietary dataset and tells whether the underlying emotion behind a message is: Happy, Sad, Angry, Fearful, Excited, Funny or Indifferent.

        # Overview
        Things that the developers should know about

        The API accepts the input parameters as form-data.Languages supported are German (de), French (fr), Dutch (nl), Italian (it), Spanish (es), Chinese (zh), Portuguese (pt), Japanese (ja), Indonesian (id), Thai (th), Danish (da), Finish (fi)

        Response will be in JSON as shown below:

        ```
        {
            "emotion": {
                "probabilities": {
                    "angry": 0.376,
                    "indifferent": 0.189,
                    "sad": 0.381,
                    "excited": 0.014,
                    "happy": 0.04
                },
                "emotion": "sad"
            },
            "usage": "By accessing ParallelDots API or using information generated by ParallelDots API, you are agreeing to be bound by the ParallelDots API Terms of Use: http://www.paralleldots.com/terms-and-conditions"
        }

        ```

        # Authentication
        What is the preferred way of using the API?

        An API key is required to be sent as a parameter to authenticate your requests.


        # Rate limit
        Is there a limit to the number of requests an user can send?

        There is no rate limit as such but too many concurrent requests will throw 504 time-out error from nginx.
      operationId: EmotionPost
      x-api-path-slug: emotion-post
      parameters:
      - in: formData
        name: api_key
      - in: formData
        name: lang_code
      - in: formData
        name: text
      responses:
        200:
          description: OK
      tags:
      - Machine Learning
      - Emotion
      - Analysis
  /similarity:
    post:
      summary: Semantic Similarity
      description: |-
        # Introduction
        What does your API do?

        Semantic Analysis API helps users cluster similar articles by understanding the relatedness between different content and streamlines research by eliminating redundant text contents.

        # Overview
        Things that the developers should know about

        The API accepts the input parameters as form-data.

        Response will be in JSON as shown below:

        ```
        {
          "usage": "By accessing ParallelDots API or using information generated by ParallelDots API, you are agreeing to be bound by the ParallelDots API Terms of Use: http://www.paralleldots.com/terms-and-conditions",
          "actual_score": 0.842932,
          "normalized_score": 4.931469
        }

        ```

        # Authentication
        What is the preferred way of using the API?

        An API key is required to be sent as a parameter to authenticate your requests.


        # Rate limit
        Is there a limit to the number of requests an user can send?

        There is no rate limit as such but too many concurrent requests will throw 504 time-out error from nginx.
      operationId: SimilarityPost
      x-api-path-slug: similarity-post
      parameters:
      - in: formData
        name: api_key
      - in: formData
        name: text1
      - in: formData
        name: text2
      responses:
        200:
          description: OK
      tags:
      - Machine Learning
      - Semantic
      - Similarity
      - Analysis
  /ner:
    post:
      summary: Name Entity Recognition
      description: |-
        # Introduction
        What does your API do?

        Named-entity recognition(NER) can identify individuals, companies, places, organization, cities and other various type of entities. API can extract this information from any type of text, web page or social media network.

        # Overview
        Things that the developers should know about

        The API accepts the input parameters as form-data.

        Response will be in JSON as shown below:

        ```
        {
            "usage": "By accessing ParallelDots API or using information generated by ParallelDots API, you are agreeing to be bound by the ParallelDots API Terms of Use: http://www.paralleldots.com/terms-and-conditions",
            "entities": [
                {
                    "category": "name",
                    "name": "Donald Trump",
                    "confidence_score": 0.977811
                },
                {
                    "category": "place",
                    "name": "United States",
                    "confidence_score": 0.982107
                }
            ]
        }

        ```

        # Authentication
        What is the preferred way of using the API?

        An API key is required to be sent as a parameter to authenticate your requests.


        # Rate limit
        Is there a limit to the number of requests an user can send?

        There is no rate limit as such but too many concurrent requests will throw 504 time-out error from nginx.
      operationId: NerPost
      x-api-path-slug: ner-post
      parameters:
      - in: formData
        name: api_key
      - in: formData
        name: text
      responses:
        200:
          description: OK
      tags:
      - Machine Learning
      - Name
      - Entity
      - Recognition
  /keywords:
    post:
      summary: Keywords
      description: |-
        # Introduction
        What does your API do?

        Keyword Generator are powerful tools in text analysis that can be used to index data, generate tag clouds and accelerate the searching time. It generates an extensive list of relevant keywords and phrases to make research more context focussed.

        # Overview
        Things that the developers should know about

        The API accepts the input parameters as form-data.

        Response will be in JSON as shown below:

        ```
        {
            "keywords": [
                {
                    "keyword": "Cristiano Ronaldo",
                    "confidence_score": 0.887065
                },
                {
                    "keyword": "Principality Stadium",
                    "confidence_score": 0.903289
                },
                {
                    "keyword": "Cardiff last",
                    "confidence_score": 0.806802
                },
                {
                    "keyword": "couple",
                    "confidence_score": 0.69036
                },
                {
                    "keyword": "hours",
                    "confidence_score": 0.984956
                },
                {
                    "keyword": "Real Madrid win",
                    "confidence_score": 0.812151
                }
            ],
            "usage": "By accessing ParallelDots API or using information generated by ParallelDots API, you are agreeing to be bound by the ParallelDots API Terms of Use: http://www.paralleldots.com/terms-and-conditions"
        }
        ```

        # Authentication
        What is the preferred way of using the API?

        An API key is required to be sent as a parameter to authenticate your requests.


        # Rate limit
        Is there a limit to the number of requests an user can send?

        There is no rate limit as such but too many concurrent requests will throw 504 time-out error from nginx.
      operationId: KeywordsPost
      x-api-path-slug: keywords-post
      parameters:
      - in: formData
        name: api_key
      - in: formData
        name: text
      responses:
        200:
          description: OK
      tags:
      - Machine Learning
      - Keywords
      - Analysis
  /taxonomy:
    post:
      summary: Taxonomy
      description: |-
        # Introduction
        What does your API do?

        Text Classification can be useful in understanding customer behaviour by categorizing conversations on social networks, feedback and other web sources.

        # Overview
        Things that the developers should know about

        The API accepts the input parameters as form-data.

        Response will be in JSON as shown below:

        ```
        {
            "usage": "By accessing ParallelDots API or using information generated by ParallelDots API, you are agreeing to be bound by the ParallelDots API Terms of Use: http://www.paralleldots.com/terms-and-conditions",
            "taxonomy": [
                {
                    "tag": "News and Politics",
                    "confidence_score": 0.576461
                },
                {
                    "tag": "Religion & Spirituality",
                    "confidence_score": 0.473842
                },
                {
                    "tag": "Hobbies & Interests",
                    "confidence_score": 0.318032
                }
            ]
        }
        ```

        # Authentication
        What is the preferred way of using the API?

        An API key is required to be sent as a parameter to authenticate your requests.


        # Rate limit
        Is there a limit to the number of requests an user can send?

        There is no rate limit as such but too many concurrent requests will throw 504 time-out error from nginx.
      operationId: TaxonomyPost
      x-api-path-slug: taxonomy-post
      parameters:
      - in: formData
        name: api_key
      - in: formData
        name: text
      responses:
        200:
          description: OK
      tags:
      - Machine Learning
      - Taxonomy
  /intent:
    post:
      summary: Intent
      description: |-
        # Introduction
        What does your API do?

        This classifier tells whether the underlying intention behind a sentence is opinion, news, marketing, complaint, suggestion, apprectiation, query. This is trained on our proprietary dataset.

        # Overview
        Things that the developers should know about

        The API accepts the input parameters as form-data.

        Response will be in JSON as shown below:

        ```
        {
            "probabilities": {
                "marketing": 0.038,
                "news": 0.916,
                "query": 0.008,
                "feedback/opinion": 0.017,
                "spam/junk": 0.02
            },
            "usage": "By accessing ParallelDots API or using information generated by ParallelDots API, you are agreeing to be bound by the ParallelDots API Terms of Use: http://www.paralleldots.com/terms-and-conditions",
            "intent": "news"
        }

        ```

        # Authentication
        What is the preferred way of using the API?

        An API key is required to be sent as a parameter to authenticate your requests.


        # Rate limit
        Is there a limit to the number of requests an user can send?

        There is no rate limit as such but too many concurrent requests will throw 504 time-out error from nginx.
      operationId: IntentPost
      x-api-path-slug: intent-post
      parameters:
      - in: formData
        name: api_key
      - in: formData
        name: text
      responses:
        200:
          description: OK
      tags:
      - Machine Learning
      - Intent
  /abuse:
    post:
      summary: Abuse
      description: |-
        # Introduction
        What does your API do?

        Abusive content specifier specifies whether the content is abusive or not.

        # Overview
        Things that the developers should know about

        The API accepts the input parameters as form-data.

        Response will be in JSON as shown below:

        ```
        {
          "usage": "By accessing ParallelDots API or using information generated by ParallelDots API, you are agreeing to be bound by the ParallelDots API Terms of Use: http://www.paralleldots.com/terms-and-conditions",
          "sentence_type": "Abusive",
          "confidence_score": 0.953125
        }

        ```

        # Authentication
        What is the preferred way of using the API?

        An API key is required to be sent as a parameter to authenticate your requests.


        # Rate limit
        Is there a limit to the number of requests an user can send?

        There is no rate limit as such but too many concurrent requests will throw 504 time-out error from nginx.
      operationId: AbusePost
      x-api-path-slug: abuse-post
      parameters:
      - in: formData
        name: api_key
      - in: formData
        name: text
      responses:
        200:
          description: OK
      tags:
      - Machine Learning
      - Abuse
  /text_parser:
    post:
      summary: Text Parser
      description: |-
        # Introduction
        What does your API do?

        Understand the text entered by using our API.

        # Overview
        Things that the developers should know about

        The API accepts the input parameters as form-data.

        Response will be in JSON as shown below:

        ```
        {
            "usage": "By accessing ParallelDots API or using information generated by ParallelDots API, you are agreeing to be bound by the ParallelDots API Terms of Use: http://www.paralleldots.com/terms-and-conditions",
            "output": [
                {
                    "text": "Donald",
                    "Dependency": "compound",
                    "Tags": "noun"
                },
                {
                    "text": "Trump",
                    "Dependency": "nominal subject",
                    "Tags": "noun"
                },
                {
                    "text": "is",
                    "Dependency": "root",
                    "Tags": "verb"
                },
                {
                    "text": "the",
                    "Dependency": "determiner",
                    "Tags": "determiner"
                },
                {
                    "text": "President",
                    "Dependency": "attribute",
                    "Tags": "noun"
                },
                {
                    "text": "of",
                    "Dependency": "prepositional modifier",
                    "Tags": "preposition or conjunction"
                },
                {
                    "text": "the",
                    "Dependency": "determiner",
                    "Tags": "determiner"
                },
                {
                    "text": "United",
                    "Dependency": "compound",
                    "Tags": "noun"
                },
                {
                    "text": "States",
                    "Dependency": "object of a preposition",
                    "Tags": "noun"
                },
                {
                    "text": "of",
                    "Dependency": "prepositional modifier",
                    "Tags": "preposition or conjunction"
                },
                {
                    "text": "America",
                    "Dependency": "object of a preposition",
                    "Tags": "noun"
                }
            ]
        }

        ```

        # Authentication
        What is the preferred way of using the API?

        An API key is required to be sent as a parameter to authenticate your requests.


        # Rate limit
        Is there a limit to the number of requests an user can send?

        There is no rate limit as such but too many concurrent requests will throw 504 time-out error from nginx.
      operationId: TextParserPost
      x-api-path-slug: text-parser-post
      parameters:
      - in: formData
        name: api_key
      - in: formData
        name: text
      responses:
        200:
          description: OK
      tags:
      - Machine Learning
      - Text
      - Parser
  /custom_classifier:
    post:
      summary: Custom Classifier
      description: |-
        # Introduction
        What does your API do?

        Custom Classifier API accepts input text, categories with a list of sub-categories and API key to return a JSON response classifying the input text into categories provided.

        # Overview
        Things that the developers should know about

        The API accepts the input parameters as form-data. Providing sub-categories is optional, send an empty array ('[]') in case you do want to add any sub-categories to your category.

        Response will be in JSON sorted by confidence score as shown below:

        ```
        {
            "usage": "By accessing ParallelDots API or using information generated by ParallelDots API, you are agreeing to be bound by the ParallelDots API Terms of Use: http://www.paralleldots.com/terms-and-conditions",
            "taxonomy": [
                {
                    "tag": "world politics",
                    "confidence_score": 0.622804
                },
                {
                    "tag": "finance",
                    "confidence_score": 0.325811
                }
            ]
        }
        ```

        # Authentication
        What is the preferred way of using the API?

        An API key is required to be sent as a parameter to authenticate your requests.


        # Rate limit
        Is there a limit to the number of requests an user can send?

        There is no rate limit as such but too many concurrent requests will throw 504 time-out error from nginx.
      operationId: CustomClassifierPost
      x-api-path-slug: custom-classifier-post
      parameters:
      - in: formData
        name: api_key
      - in: formData
        name: category
      - in: formData
        name: text
      responses:
        200:
          description: OK
      tags:
      - Machine Learning
      - Custom
      - Classifier
  /popularity:
    post:
      summary: Virality Detection
      description: "# Introduction\nWhat does your API do?\n\nGet the virality score
        of your picture on socail media.  \n\n# Overview\nThings that the developers
        should know about\n\nThe API accepts the input parameters as form-data.\n\nResponse
        will be in JSON as shown below:\n\n```\n{\n    \"Popular\": \"59.8144471645\",\n
        \   \"usage\": \"By accessing ParallelDots API or using information generated
        by ParallelDots API, you are agreeing to be bound by the ParallelDots API
        Terms of Use: http://www.paralleldots.com/terms-and-conditions\",\n    \"Not
        Popular\": \"40.1855528355\"\n}\n\n```\n\n# Authentication\nWhat is the preferred
        way of using the API?\n\nAn API key is required to be sent as a parameter
        to authenticate your requests.\n\n\n# Rate limit\nIs there a limit to the
        number of requests an user can send?\n\nThere is no rate limit as such but
        too many concurrent requests will throw 504 time-out error from nginx."
      operationId: PopularityPost
      x-api-path-slug: popularity-post
      parameters:
      - in: formData
        name: api_key
      - in: formData
        name: file
      responses:
        200:
          description: OK
      tags:
      - Machine Learning
      - Virality
      - Detection
  /nsfw:
    post:
      summary: NSFW
      description: |-
        # Introduction
        What does your API do?

        Nudity detection classifier is a powerful tool to filter out pornographic and non-pornographic images from social media feeds, forums, messaging apps, etc.. ParallelDots nudity detection classifier can filter such content and help build a safer platform for your community.

        # Overview
        Things that the developers should know about

        The API accepts the input parameters as form-data.

        Response will be in JSON as shown below:

        ```
        {
            "usage": "By accessing ParallelDots API or using information generated by ParallelDots API, you are agreeing to be bound by the ParallelDots API Terms of Use: http://www.paralleldots.com/terms-and-conditions",
            "output": "safe to open at work",
            "prob": 0.911244809627533
        }

        ```

        # Authentication
        What is the preferred way of using the API?

        An API key is required to be sent as a parameter to authenticate your requests.


        # Rate limit
        Is there a limit to the number of requests an user can send?

        There is no rate limit as such but too many concurrent requests will throw 504 time-out error from nginx.
      operationId: NsfwPost
      x-api-path-slug: nsfw-post
      parameters:
      - in: formData
        name: api_key
      - in: formData
        name: file
      responses:
        200:
          description: OK
      tags:
      - Machine Learning
      - NSFW
  /phrase_extractor:
    post:
      summary: Phrase Extractor
      description: |-
        # Introduction
        What does your API do?

        Get phrase keywords from the text in the input.

        # Overview
        Things that the developers should know about

        The API accepts the input parameters as form-data.

        Response will be in JSON as shown below:

        ```
        {
            "keywords": [
                {
                    "relevance_score": 1,
                    "keyword": "Ronaldo"
                },
                {
                    "relevance_score": 2,
                    "keyword": "Principality Stadium"
                },
                {
                    "relevance_score": 1,
                    "keyword": "Cardiff"
                },
                {
                    "relevance_score": 1,
                    "keyword": "last"
                },
                {
                    "relevance_score": 1,
                    "keyword": "June"
                },
                {
                    "relevance_score": 2,
                    "keyword": "Real Madrid"
                },
                {
                    "relevance_score": 1,
                    "keyword": "its"
                },
                {
                    "relevance_score": 2,
                    "keyword": "third champions"
                },
                {
                    "relevance_score": 2,
                    "keyword": "League trophy"
                }
            ],
            "usage": "By accessing ParallelDots API or using information generated by ParallelDots API, you are agreeing to be bound by the ParallelDots API Terms of Use: http://www.paralleldots.com/terms-and-conditions"
        }

        ```

        # Authentication
        What is the preferred way of using the API?

        An API key is required to be sent as a parameter to authenticate your requests.


        # Rate limit
        Is there a limit to the number of requests an user can send?

        There is no rate limit as such but too many concurrent requests will throw 504 time-out error from nginx.
      operationId: PhraseExtractorPost
      x-api-path-slug: phrase-extractor-post
      parameters:
      - in: formData
        name: api_key
      - in: formData
        name: text
      responses:
        200:
          description: OK
      tags:
      - Machine Learning
      - Phrase
      - Extractor
x-streamrank:
  polling_total_time_average: 0
  polling_size_download_average: 0
  streaming_total_time_average: 0
  streaming_size_download_average: 0
  change_yes: 0
  change_no: 0
  time_percentage: 0
  size_percentage: 0
  change_percentage: 0
  last_run: ""
  days_run: 0
  minute_run: 0
---