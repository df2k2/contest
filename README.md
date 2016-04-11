# Article Contest

A high-level overview of a writing contest submission and review system.
====

**Development Notes**

I would suggest a re-usable framework such as Laravel, Yii, Zend, etc..., if there doesn't already exist methods or plug-ins for this process.  Using a framework such as laravel would allow for a scalable component architecture with API capabilities to integrate into any existing architecture. 

## Database tables

Overview of possible database tables

#### Contest Table

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

#### Contest Article Table

| contest_article | Type | Description |
|  ---- | ---- | ---- |
| id | | |
| contest_id | | |
| ambassador_id  | | |
| title  | | |
| content  | | |
| tags  | | |
| date_reviewed  | | |
| rating | | |
| date_submitted | | |
| created | | |
| updated | | |
| status | | |


_Note: If multiple reviewers, there needs to be a many to one association to the articles; Reviewers need id for accountability_

----

## Contest List

Contests need to be accessible by the ambassadors and can be announced via email or internal admin.

 - Publish contest and details on Ambassador internal / admin site (if exists).
 - Contain links to form for submitting article for contest. Parameter for contest_id, and ambassador_id should be passed.
 - Show contest themes / topics listed by due date and/or visually within a calendar mode.

----

## Contest Article Form



- Clicking contest article link should post related data needed for proper data associations
- User authorization methods can be used
- Form field for content could use [TinyMCE](https://www.tinymce.com/) with custom formatting buttons 
  - Limit the functionality buttons available
- Hidden or disabled fields should include contest_id, ambassador_id, unique form key
- Pop-up (one time) and / or links for terms and conditions, guidelines, and notification that images require rights.
- Client-side validation

**Possible Additional Functionality**

- Auto-Save drafts
- Checkbox to acknowledge terms and conditions were not knowingly violated, images rights are not violated, etc...
  - Disabled "Submit" until checkbox is acknowledged (would help with spambots and accidental pre-mature submissions)
- Preview mode
- Upload images (instead of linking to img src)

### Article Post-Submission

- Server side validation, cleansing, normalization, character escapes
- Notifications
- Determine if submitted articles may be edited

---- 

## Article Reviews



4. Internal method for reviewing articles, rating, and selecting winners
5. Winning article or articles published should be normalized for consistent formatting and pushed (method TBD) to publishing platform (wordpress)
6. Articles published could inform the ambassador and provide link for them to publish on their social platforms.  This could help with google's indexing on top of sitemap.

reference:

Webmaster Guidelines: https://support.google.com/webmasters/answer/35769?hl=en&ref_topic=6002025
TinyMCE to help with formatting: https://www.tinymce.com/
