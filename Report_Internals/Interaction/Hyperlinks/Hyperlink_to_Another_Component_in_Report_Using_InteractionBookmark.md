## Hyperlink to Another Component in Report Using Interaction.Bookmark

In this way you should put the **#** symbol before the hyperlink text. This makes the report generator understand that this is a reference inside of a document. If, in the window of preview, a user clicks on this component then the report generator will start to search all bookmarks of this report. If the bookmark name matches the hyperlink name (the # symbol is skipped) then this component will be displayed in the window of preview. It is important to remember that a bookmark is shown in the tree of bookmarks.


* **Note:** The Interaction.Bookmark property contains the text marker by which this component will be found during hyperlink processing.
