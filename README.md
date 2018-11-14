# Journal of Open Source Software

The Journal of Open Source Software (JOSS) is a developer friendly journal for research software packages.

This business network defines:

**Participant**
`person`

**Asset**
`paper`

**Transaction**
`Submit` 
`Feedback`
`Usage`


Initially a `paper` asset is submitted to JOSS by an author `person`. The editor `person` must asign the reviewer(s) `person` using the `Feedback` transaction. This `Feedback` transaction can be re-used to capture the communication and any changes in the `paper`, that is changes in state or any change in the field, for example asigning a proper DOI. After the paper has been accepted then the transaction `usage` will keep track of the number of times the submitted software has been used by a third party. This usage can provide feedback statistics for the editor and the author on the popularity of the software.  
   

To test this Business Network Definition in the **Test** tab:

Create an editor `person`:

```
{
  "$class": "org.joss.person",
  "email": "john@joss",
  "fname": "john",
  "lname": "editor",
  "person_role": "editor",
  "orcid": "001",
  "institute": [
    {
      "$class": "org.joss.afiliation",
      "institution": "University"
    }
  ]
}
```
Create an reviewer `person`:

```
{
  "$class": "org.joss.person",
  "email": "alice@joss",
  "fname": "alice",
  "lname": "reviewer",
  "person_role": "reviewer",
  "orcid": "002",
  "institute": [
    {
      "$class": "org.joss.afiliation",
      "institution": "University"
    }
  ]
}
```


Create an author `person`:

```
{
  "$class": "org.joss.person",
  "email": "john@org",
  "fname": "john",
  "lname": "author",
  "person_role": "author",
  "orcid": "001",
  "institute": [
    {
      "$class": "org.joss.afiliation",
      "institution": "University"
    }
  ]
}
```

Create a `Paper` (submission) asset:

```
{
  "$class": "org.joss.paper",
  "doi": "01",
  "title": "Gala: A Python package for galactic dynamics",
  "tags": [
    "Python", "astronomy", "dynamics", "galactic dynamics", "milky way"
  ],
  "author": "resource:org.joss.person#john@org",
  "bibliography": "paper.bib",
  "description": "paper.md",
  "url_p": "github/paper.git",
  "usage": 0,
  "stage_p": "submitted",
  "editor": "resource:org.joss.person#john@joss",
  "reviewers": [],
  "Comments": ""
}
```