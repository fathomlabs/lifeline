# Life line

## The idea

The basic premise is to make an interactive, pretty time line of the events in our life. We will make the framework in d3js and store the event data in a json which can be switched out so that others can use the tool to view their own life.

---

## UI

Initially the user will be asked their name and date of birth. This can be given to the nearest year or as an exact date and time.

Next, the user will be prompted to choose the categories of the key themes in their life, for example: schools, jobs, relationships, major events, homes, hobbies, pets, *etc*.

When they are finished (and it doesn't have to be complete), they are ready to start adding events.

The event adding form will have the following fields:
- name/brief description **[required field]**
- key theme(s) **[required field]**
  - this will be from a selection of the previously chosen themes, with the option to add a new theme included
- date **[required field]**
  - this can either be a single date (with arbitrary specificity allowed (from whole year down to exact minute)) or a date range: beginning and ending also with arbitrary specificity allowed
- detailed description
- photo(s)
  - the user will be able to upload photos for a given event, these will be added to a folder named "photos"

The json will be constructed from these events. It will contain three root keys: "name", "themes", and "events". The user's name will be the value for "name", an array of their chosen categories of events in their life will be the value for "themes", and the events will be placed as an array of objects with keys matching the bulleted list above. The name field will take a string. The key theme(s) field will be an array of at least one index of the "themes" field. The date field will be an array of either one or two dates (and times) of the form yyyy.mm.dd.hh.mm (24-hour clock). The detailed description field will take a string. The photo(s) field will be the filename of an image in the "photos" folder.
