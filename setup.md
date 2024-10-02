# Setup

- Import some data to the lakehouse from the repo ready for AI Skill


> [!TIP]
> Clone the repo to have the data files locally prior to this step.  Alternately just download them from the `/data` folder in the repo.


## Steps
1.  Go to the Lakehouse you created in [Prerequisites](/prerequisites.md)
2. In the **Files** area of the Lakehouse, create a folder called `Adhoc`
3. Click the elipsis (three dots) next to the new **Adhoc** folder
4. Click **Upload**
5. Click **Upload files**
6. Upload the two csvs from the data area in the repo:

![Upload Files](/images/uploadfiles.png)

7. Right-click each file and click **Load to Tables** then **New table**:

![Load to Table](/images/loadtotables.png)

Accept the default options of **New table name**,(same as the file name), **Column header** (true), and a comma as the **Separator**.

Click **Load**.

8. When the import completes successfully, review the two new tables in Lakehouse mode:

![Lakehouse Mode](/images/lakehousemode.png)

## Next Steps
[Lab 01 - Set up AI Skill in Fabric](/labs/lab01/lab01.md)