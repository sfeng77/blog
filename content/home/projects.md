+++
# Projects widget.
# Note: this widget will only display if `content/project/` contains projects.

date = "2017-04-15T00:00:00"
draft = false

title = "Projects"
subtitle = ""
widget = "projects"

# Order that this section will appear in.
weight = 50

# View.
# Customize how projects are displayed.
# Legend: 0 = list, 1 = cards.
view = 1

# Filter toolbar.
# Add or remove as many filters (`[[filter]]` instances) as you like.
# Use "*" tag to show all projects or an existing tag prefixed with "." to filter by specific tag.
# To remove toolbar, delete/comment all instances of `[[filter]]` below.
[[filter]]
  name = "All"
  tag = "*"
  
[[filter]]
  name = "GPU"
  tag = ".gpu"

[[filter]]
  name = "Xeon Phi"
  tag = ".phi"

[[filter]]
  name = "Physics"
  tag = ".physics"

[[filter]]
  name = "Data Science"
  tag = ".data"

[[filter]]
  name = "Other"
  tag = ".demo"
  
+++

