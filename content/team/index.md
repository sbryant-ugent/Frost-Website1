---
# TEAM PAGE
# People are listed automatically from the files in data/authors/.
# To add someone: copy one of those files, rename it (e.g. jane-doe.yaml),
# edit the details, and set "user_groups" to one of the groups below.
# Photos: assets/media/authors/<file-name>.jpg (square, about 400×400 px).
# The current pictures are placeholders showing initials.
title: Team
date: 2026-10-01
type: landing

sections:
  - block: team-showcase
    content:
      title: The FROST team
      subtitle: ''
      text: FROST is based in the Department of Archaeology at Ghent University and works closely with the university's Department of Geology.
      user_groups:
      sort_by: weight
      sort_ascending: true
    design:
      show_role: true
      show_organizations: false
      show_interests: true
      max_interests: 3
      show_social: true
      max_columns: 3
      align: center

  - block: markdown
    content:
      title: Expert advisory board
      text: |-
        An international advisory board supports FROST at key stages of the project. <!-- TODO: confirm the board members are happy to be listed publicly before going live. -->

        - **Dr Sophie Verheyden**, Royal Belgian Institute of Natural Sciences: speleothem palaeoclimate
        - **Prof. Felix Riede**, Aarhus University: human societies and volcanic activity, (crypto)tephra
        - **Morgane Ollivier** and **Frédérique Hubler**, University of Rennes: sedimentary ancient DNA

        ## Collaborators and partner laboratories

        TODO: list the institutions and laboratories you want to acknowledge here (for example the dating, isotope and sedaDNA laboratories)
    design:
      columns: '1'
      css_class: "bg-slate-50 dark:bg-gray-900/50"
---
