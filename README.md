# Coding-Assignment-3-Data-Bias-MO

The goal of this assignment is to determine some form of bias in the Perspective API, which is a natural language processing model designed to provide a toxicity score for internet comments.

Throughout this assignment, I tested the Perspective APIs ability to flag comments that contain profane language hidden in acronyms. The goal is to see if the API has some form of age bias because children are the most vulnerable to seeing harmful language on the internet, but many times the language is hidden in the form of acronyms, so it is not detected by platforms. Even commonly used acronyms may contain profane language, and these acronyms are seen in many internet comments, which puts children at risk of being exposed to langauge that they should not see. 

##Hypothesis:

#### The model will likely score obscenities as much more toxic than other negative language, but, given acronyms that contain obscenities, the model will output a much lower score than the statements that contain the obscenities in full.

If the model is unable to correctly identify acronyms as toxic, this could demonstrate age bias. Online, children are the most vulnerable to being exposed to profanities, and they are much more likely to see these in the form of acronyms. Platforms and developers that use Perspective API should then be aware that the API does not account for profane text that is seen in the form of acronyms.

##Results 

The model accurately predicted that a statement containing an acronym was toxic 0% of the time. Looking at the previous data, the model only predicted that a comment containing an acronym was toxic once, but, in the test data, this comment was marked not toxic. This proves my hypothesis to be true because the model was unable to identify when a comment that contains profanity hidden in a commonly used acronym was toxic. This means that developers using the perspective API need to be aware that users could potentially be exposed to toxic comments if obscenities are hidden in an acronym. This could represent a form of age bias because, on the internet, children are the most vulnerable to seeing inappropriate language, and could be exposed to such obscenities without their parents being aware. 


The model accurately predicted that a comment containing an acronym that contains profanity was not toxic 83.3% of the time. In this situation, a false positive, as seen with the lack of true negatives, is much more harmful than a false negative. This means that, although the model did accurately classify many comments that contain acronyms with obscenities as not toxic, the vulnerability in the model is still obvious, and the model could still cause unintentional harm. 

The model accurately predicted that a comment containing full text profanities was toxic 100% of the time. In fact, every comment containing a full text profanity was labelled toxic. Although this definitely proves the models ability to flag profane language to a degree, it still does not make up for the potential deficiencies in the model that could cause harm due to its inability to flag comments with acronyms; the statements "that test was so hard i'm going to kms" and "that test was so hard, im going to kill myself", can cause just as much harm because they have the same meaning, but the former received a toxicity score of 0.24 and the latter received a score of 0.73. 


Finally, the model accurately predicted that a comment containing full text profanities were not toxic 0% of the time. Because the model does not understand social cues or slang, it is understanable, that many of the comments with profanities are labelled as toxic. As I said before, a false negative, in this situation is much more harmful than a false positive. Because of this, deficiencies in the models ability to accurately flag comments containing profanities as not toxic are much less concerning, and can be seen as a potential strength of the model. 

Generally, the model is likely to flag comments as toxic if they contain any harmful words, regardless of the content of the rest of the statement. This means that the model is likely unable to identify slang words like "cringe" or "cheugy" as toxic as well. However, this means that neutral statements containing words with double meanings (for instance, "the bitch just gave birth to a litter of puppies") would also likely be inaccurately flagged as toxic. Additionally, this means that users on platforms that use Perspective API could get around the models flags by hiding their language in acronyms, as seen throughout the dataset. 

