# Article Contest

A high-level overview of a writing contest submission and review system.
----

## Database tables

Database tables for article 'contest', 'contest_article'

| contest | Type | Description |
|  ---- | ---- | ---- |
| contest_id | int(11) | Primary Key |
| title | varchar(255) | Title of contest / topic |
| start_date | datetime | |
| end_date | datetime |  |
| content |  | |
| tags | | Csv of Tags associated with contest |
| created  | | |
| updated | | |


| contest_article | Type | Description |
|  ---- | ---- | ---- |


2. Publish contest and details on Ambassador internal / admin site (if exists).  
	Link to submit article for contest. Parameter for contest_id, and ambassador_id should be passed.
2a. Show contest theme / topics listed by due date and/or visually within a calendar mode.

3. Link to form for posting article submission.  
	Form field for content could use TinyMCE with custom formatting buttons (https://www.tinymce.com/)
	Hidden or disabled fields should include contest_id / ambassador_id.
	Terms and conditions, guidelines, and notification that images require rights.

3a. Submissions should include methods to cleanse posted data.
3b. Add checkbox acknowledging that terms and conditions were read and not violated, then "Submit" button can be enabled to submit article.

4. Internal method for reviewing articles, rating, and selecting winners
5. Winning article or articles published should be normalized for consistent formatting and pushed (method TBD) to publishing platform (wordpress)
6. Articles published could inform the ambassador and provide link for them to publish on their social platforms.  This could help with google's indexing on top of sitemap.

reference:

Webmaster Guidelines: https://support.google.com/webmasters/answer/35769?hl=en&ref_topic=6002025
TinyMCE to help with formatting: https://www.tinymce.com/
