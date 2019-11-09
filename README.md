# BoilerBot Documentation

Simple team documentation built with markdown and Github Pages. Aims at providing newcomers with self-learning materials.

## Structure Explanation

Each folder under root should be the team folder for the specified team, which contains all materials for that team's documentation.

The media folder under each team folder is intended for hosting media files like images, videos, etc.

Each team will have an `index.md` file as the main entry point for its documentation which outline has been provided. To create subpages, one can either choose to first create a folder to host the subpages if there are many of them, or can directly create a separate markdown page under the team folder. 

To create hyperlink in markdown, one should use relative refernce rather than absolute reference in each team folder. For instance, if I want to refer to the file name `hello.world` under the electrical team folder, I should use `./hello.world` rather than `/electrical/hello.world`.

If one want to refer a header created in the same file, one can use the pound sign `#` attached with the header name to refer to it.