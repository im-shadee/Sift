# Sift
A french housing data app made in Java using the framework Swing and [FlatLaf](https://www.formdev.com/flatlaf/) for my Software Engineering classes during year 2 of university.
This app was developed with 6 other contributors besides me. Tested and compatible on Windows/Linux.

Code is private for privacy/copyright reasons.


## 💭 What is this project?
This project is a software allowing you to load public [french housing datasets](https://www.data.gouv.fr/datasets/demandes-de-valeurs-foncieres),and generate HTML backlogs on that data. The application allows you to chose filters and specific stats to display, as well as a specific type of diagram to use.

Here's how this application is structured:

<p align="center"><img width="803" height="602" alt="Copie d&#39;écran_20260908_114007" src="https://github.com/user-attachments/assets/e1ccb2ea-fb5b-4ba9-8359-5cf07c64d63d" /></p>

(1) Has two tabs: 'File' and 'Accessibility'. The 'File' tab lets you chose a file (has to be a valid .txt/.csv file in the french datasets' format). The 'Accessibility' tab lets you choose the application theme (Dark/Light), and how much the app is zoomed in (for bigger screen resolutions/people with eye issues).

(2) The filter selection tab. Select the granularity between cities, departments, etc., then filter which data you want (e.g. Houses/Apartments only, housing with a specific mutation date, houses with a specific amount of rooms, etc.). Finally, choose the stats you want to generate data on.

(3) This window shows a recap of the options you chose in each category. You can click on the checkboxes to remove the selection, removing the need to browse through each selection window to find selected filters.

---
When clicking on granularity/filter options, this window will appear:

<img width="330" height="470" alt="Copie d&#39;écran_20260908_111829" src="https://github.com/user-attachments/assets/fb7717ef-01e6-40ba-9a2b-2759c7dc1768" />

You are prompted to choose any option from this window. There are helper buttons (in order) to:
- Select everything ('Tout' button)
- Unselect everything ('Aucun' button)
- Validate the selection ('OK' button)


## 📊​ Backlog generation
Once everything is selected, you can click on any 3 buttons at the top (diagram types - pie chart; bar chart; column chart) to generate your diagram. Some diagrams are locked by design for certain statistics because they don't make sense for these specific stats.

<p align="center"><img width="2115" height="118" alt="image" src="https://github.com/user-attachments/assets/ad15d48b-c050-4d6d-a603-418f494088ec" /></p>

Clicking on any of these buttons makes a request to the backend to get the requested data, and instructs the HTML content to write on disk. The generated HTML is written in /out/ with name `diagOut.html`. Here is what a concrete backlog looks like:

<img width="3200" height="1803" alt="Copie d&#39;écran_20260908_111952" src="https://github.com/user-attachments/assets/492591a0-7a4d-4550-9b51-3df2157cf3c5" />

At the top, there is a section with 'pins' that sum up your selection. Each diagrams' title is generated automatically depending on the stats/filters chosen.
The design was made user-friendly, with a 'card' format, allowing to locate relevant information intuitively.


## 📚​ My roles?

I played the role of team lead during the first half of the development, where we created a library to create shapes and export them to SVG, and then I got to play the role of Scrum Master during the development of the app itself. The goal was to get initiated to team work environments and AGILE practices as well as Test-Driven-Development, to develop a satisfying product in a limited amount of time.

Here's a more detailed list of my work on this project:
- Responsible for making the UI/UX in Swing (making the main app and addons such as JCheckBoxWithEnum, which stores a value enum on a JCheckBox resulting in a solid architecture to avoid using fragile string comparison)
- Created a save system for application settings (last loaded csv/txt file path, current application mode, current zoom settings)
- Connecting the application to the backend and the HTML generation system, and ensured user feedback through warning/error windows
- Measured with a custom profiler and investigated slow load times, and reduced them by 80% (15 seconds -> 3 seconds on average, with times as low as 2.1 seconds), which allowed us to use the real 4 000 000 lines file for the final demo, while other teams had to use considerably smaller, pre-loaded samples.
- Assisted ticket-making on Taiga (Jira alternative)
- Test-writing for the application. Helped with writing backend tests and maintained/updated tests after refactors. Ensured a code coverage of at least 75% for all relevant classes.
- Coordinated the team to ensure project deadlines were met while respecting AGILE rituals. Played the role of "Scrum Master", supervised by a professional.


## 🗒️​ Licensing

Copyright (c) 2026 im-shadee

No permission is granted to use, modify, or redistribute this repository or its contents. This repository is provided for viewing and portfolio purposes only.
