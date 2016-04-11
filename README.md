# Article Contest

A high-level overview of a writing contest submission and review system.
====

**Development Notes**

I would suggest a re-usable framework such as Laravel, Yii, Zend, etc..., if there doesn't already exist methods or plug-ins for this process.  Using a framework such as laravel would allow for a scalable component architecture with API capabilities to integrate into any existing architecture.  Alternatively, articles may be pushed via Wordpress API (depending on version).

> Look up Wordpress plug-ins before considering outside framework.

## Database tables

Overview of possible database tables

#### Contest Table

| contest | Type | Description |
|  ---- | ---- | ---- |
| contest_id | int(11) | Primary Key |
| title | varchar(255) | Title of contest / topic |
| start_date | datetime | Contest start date |
| end_date | datetime | Contest end date  |
| content | text | Contest description and information |
| tags | varchar(255) | Csv of Tags associated with contest |
| created  | datetime | Created date for the record |
| updated | timestamp | Updated date for the record in the database |

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

## Article Reviews, Publishing

- Internal method for reviewing articles, rating, and selecting winners
- If component API framework used to build out system, this can be integrated into wordpress using API hooks.
- Winning article or articles published should be normalized for consistent formatting and pushed (method TBD) to publishing platform (wordpress)
- Articles published could inform the ambassador and provide link for them to publish on their social platforms.  This could help with google's indexing on top of sitemap.

====

## Developer Notes:

### Pages Required

**Admin**

_Contest_

- Create / View / Update contest
- List contests with edit / delete capability

_Contest Articles_

- List article submissions for a contest
- View / Update (Rate) article submission

**Frontend**

_Authorized_

- List contests (calendar or list mode)
- View / Edit / Update contest article

_Unauthorized_

- View article
- View article list by filtering (custom) author field


### Version 2 Considerations:

- Allow update of submitted post
- Uploading of images by user for articles

### Issues:

**Current Installed Wordpress Version is 3.8**

- [Wordpress 3.9 Changelog](https://codex.wordpress.org/Version_3.9)
- [Wordpress 4.0 Changelog](https://codex.wordpress.org/Version_4.0)
- [Wordpress 4.1 Changelog](https://codex.wordpress.org/Version_4.1)
- [Wordpress 4.2 Changelog](https://codex.wordpress.org/Version_4.2)
- [Wordpress 4.3 Changelog](https://codex.wordpress.org/Version_4.3)
- [Wordpress 4.4 Changelog](https://codex.wordpress.org/Version_4.4)
- [Wordpress 4.5 Changelog](https://codex.wordpress.org/Version_4.5)




====

**References**

- [Webmaster Guidelines](https://support.google.com/webmasters/answer/35769?hl=en&ref_topic=6002025)
- [TinyMCE](https://www.tinymce.com/)
