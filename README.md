# author-coi-checker

## Purpose

This tool takes a list of authors (eg. copied and pasted from a manuscript) in the following format:

_Alan Bronson<sup>1</sup>, Carina D. Elephant<sup>2</sup>, Felix Gerald Horton<sup>3</sup>_

...then generates a URL link to run a search in the indexing service PubMed in the following format:

>Reviewer N[au] AND ("Bronson A"[au] OR "Elephant CD"[au] OR "Horton FG"[au])

This will search for any co-publications (which can count as conflicts of interest - a.k.a. 'COIs') between the placeholder "Reviewer N" and any of the authors. Any results found will be displayed in PubMed's own search interface.

If the user additionally provides a list of reviewer candidates, a link will be generated to run the search for each specific reviewer. For instance, the above author list with the following reviewers:

_Amy Voop, Brian C. Wândels, Dimitrii Xorxy_

...will generate the following links:

>Voop A[au] AND ("Bronson A"[au] OR "Elephant CD"[au] OR "Horton FG"[au])

>Wândels BC[au] AND ("Bronson A"[au] OR "Elephant CD"[au] OR "Horton FG"[au])

>Xorxy D[au] AND ("Bronson A"[au] OR "Elephant CD"[au] OR "Horton FG"[au])

## Notes

- The JavaScript code is included in the HTML file, so that the end user can save a local copy of a single file and use it with ease.
- Non-letter characters (like superscript numbers, which are often used to indicate affiliation) are stripped away.
- Common titles, eg. Dr or Prof, and also some suffixes, eg. Jnr, are trimmed away, since they are not relevant for the search.
- This tool is not supported or endorsed by PubMed or NCBI. It is only intended for a real human (not a bot) to use to run reasonable amounts of search queries.