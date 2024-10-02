# Lab 01 - Set up AI Skill in Fabric

## Steps
1. [Create the AI Skill](#1-create-the-ai-skill)
2. [Ask AI Skill some questions](#2-ask-ai-skill-some-questions)
3. [Add some model instructions](#3-add-some-model-instructions)
4. [Add some sample queries](#4-add-some-sample-queries)

### 1. Create the AI Skill
1a. In your Fabric workspace, click on the **Data Science** experience in the workload switcher (bottom left-hand side of the Fabric screen):

![Data Science Experience](/labs/lab01/images/datascienceexperience.png)

1b.  Click on **AI Skill (preview)**

![AI Skill](/labs/lab01/images/aiskill.png)

1c. Give the AI Skill a name, eg `ai_films`.

![AI Skill Name](/labs/lab01/images/aiskillname.png)

1d. Select the tables you want to be included, eg the two tables in the Lakehouse imported earlier:

![Select Tables](/labs/lab01/images/aiskillselecttables.png)

1e. Click **Get Started**

The AI Skill will take a few moments to create.

> [!NOTE]
> If you experience the **NoCrossGeo** error, enable the Cross Geo option in the Fabric Admin portal

![Enable Cross Geo](/labs/lab01/images/enablecrossgeo.png)

### 2. Ask AI Skill some questions
2a.  Try this question
```
List some films 
```

![List some films](/labs/lab01/images/listsomefilms.png)

Observe the SQL that is generated and run.

> [!CAUTION]
> AI Skill does not always work first time.  Give it a few moments and try again.

2b.  Try this question:
```
List some films from 2024  
```

2c.  Try this question:
```
What is the highest grossing film of all time?
```  

2d. Come up with some other questions  

### 3. Add some notes for the model
3a. Add this text to the **Notes for model** section:

```
dbo.films250 stores films.  Column primaryTitle is the film name.  dbo.filmsgross is related to dbo.films250 on primaryTitle.  Column gross should always be cast to dollars.

```
3b. Try the questions again  

![Answers with model notes](/labs/lab01/images/notesandcasting.png)

3c. Try this question on sequels:

```
Look for sequels, they will have the same root film name and an additional number. List them
```

- Try different wording of this question.  How could this question be improved?

## 4. Add some sample queries
4a. Click the pencil symbol by **Example SQL Queries** in the lower right-hand side of the screen

4b. Add the following text for the question:
```
List all films and their total gross sales
```

- Add the following SQL query example:
```sql
SELECT *
FROM dbo.films250 f
	INNER JOIN dbo.filmsgross g ON f.primaryTitle = g.primaryTitle;

```

![Example SQL Queries](/labs/lab01/images/examplesqlqueries.png)

4c. Add the following SQL query example:
```
List all films and their gross values in descending order
```

- Add the following SQL query example:
```sql
-- List all films and their gross values in descending order
SELECT primaryTitle, gross
FROM dbo.filmsgross
ORDER BY gross DESC;
```

## Questions
- Was it easy to configure the AI Skill?
- What did the model instructions do?
- Did the sample query improve the questions and answers?

## Next Steps
[Lab 02 - Publish the AI Skill Endpoint](/labs/lab02/lab02.md)