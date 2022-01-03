# Oracle-Database-Including-conceptual-normalisation-logical-model-
Creating a relational database based on customer's requirements. The dtails of customer requirements and tasks are mentioned below:

Conceptual Model - Monash Cabins (MC) : build a conceptual model (Entity Relationship Diagram)

Monash Cabins is a chain of resorts (holiday destinations) located around Australia. At each of these resorts, MC provides cabin-based accommodation for its guests – any given resort consists of several independent cabins. A resort is located in a particular town. MC maintains details of points of interest (POI) in the local area that guests might wish to visit. Each POI is associated with only one town.

For each town in which a resort or point of interest is located MC records the town name, the state the town is located in, the latitude and longitude of the centre of the town, the average summer and winter day temperatures and its population. MC only records details of towns which have a resort or a point of interest. MC does not record a town's postcode since they are only interested in it as a location, not as a postal location.

For points of interest MC records the street and town in which it is located, the name of the point of interest (eg. Merimbula Aquarium), a brief description of the point of interest, its opening hours (if appropriate), and the type of point of interest (café, museum, restaurant, national park etc). The opening hours are recorded as the time at which the POI opens and the time at which it closes, only one set of these times are recorded (ie. the POI is assumed to open and close at the same time all year). Each POI is only classified as one type of point of interest, for example, a cafe in a national park will be classified as a cafe. A scan of the potential MC data has indicated that some towns contain two or more POIs of the same name but they have different street addresses.

Each resort is assigned a unique resort id. MC has several resorts in some towns and only a single resort in others depending on the location's popularity (not all recorded towns have a resort). Each resort has a name (eg. Merimbula Beach Cabins). A resort's street address, town name and contact phone number are recorded. MC also records for each resort the star rating of the resort, which is determined from the average of all guest reviews, and whether guests may bring their pets while staying at the resort.

Each resort consists of a number of cabins – the cabins are numbered starting from cabin 1 at each resort. MC records how many bedrooms there are in each cabin, the sleeping capacity of the cabin (how many people it can sleep) and a description of the cabin to provide potential guests with some details to assist their decision making.

MC guests, those staying at the resorts, are assigned a unique guest number when they first
register with MC. The guest name, home address, email and contact phone number are recorded. A guest makes a booking with MC by choosing the resort they wish to stay at and the cabin they wish to stay in. Guests are required to provide the date they wish to book from and the date they wish to stay to. They must also supply MC with the number of adults and the number of children who will be staying. MC records as part of the booking the total charge for the particular booking, based on the cabin rate and the number of days that the guest will stay.

Guests are offered the opportunity to provide a review of the resort - they are not required to do so, but if they do, they provide a comment and a rating from 1 (poor) to 5 (outstanding). These reviews are treated as general reviews of the resort rather than being related to a particular cabin or stay. A guest may complete many reviews of a particular resort during their stay. The review may also be made after the guest has left the resort. The date of the review is recorded (a guest is not permitted to complete two reviews on the same day).

The rates charged for a cabin depend on the cabin itself (some cabins have special features such as a spa) and the time of the year in which the guest is staying. For example, for seaside resorts, the highest rates are charged in the peak summer period (eg. Jan – Feb) when demand is at its highest. The rate for each cabin is recorded for each of these charge periods – rate periods may vary between different resorts. The start date and end date of the rate period are recorded. Where a booking spans several rate periods, the booking is charged at the rate which applies on the first day of the booking. The data stored on rates is used by the resort staff to calculate a bookings total charge (this calculation is carried out externally to this system).

You are free to make assumptions if needed however they must align with the details mentioned above. 

TASKS

Conceptual model


GIT STORAGE

All working files, as you work on this task, must be stored in GIT and must show a clear history of development. 

Task to complete:

Using LucidChart, prepare a FULL conceptual model (Entity Relationship Diagram) using crow’s foot notation for Monash Cabins (MC) described above.
● For this FULL conceptual model, include:
○ identifiers (keys) for each entity
○ all required attributes, and
○ all relationships. Cardinality (min and max) and connectivity for all relationships must be shown on the diagram.
● Surrogate keys must not be added to this model.


Logical Model - Monash Cabins (MC) – build a logical model

This task continues the work you have started in Conceptual model by refining/extending the model you developed and implementing it as a set of tables under your Monash Oracle database account.

Logical model's brief must be read in conjunction with the conceptual model brief - i.e. your final model must encompass both sets of requirements.  If the supplementary material presented in this document does not guide you in deciding the components you may make any reasonable decision on their simple component attributes.

Monash Cabins management have provided the following further information:

When guests vacate a cabin, MC use contract cleaners to clean the cabin. MC maintain, for each resort, a record of the cleaning activity for its cabins (a small sample of this is shown below):

Document A : See document_A attachments

 
A cleaning contractor is assigned a unique contractor number when first taking up work with MC. 
Contract cleaners may work as casual staff or fixed term staff.
Fixed-term staff sign a contract to clean for a set period of time eg. 12 months.
Casual cleaners are not locked into any fixed period to clean, they are available on a weekly basis as work is available or suits them. Casual cleaners are contacted when work is available to clean a particular cabin and may accept or reject the job.
Contract cleaners may shift between these two modes depending on what suits them better.
MC maintain a record of the contract history for all cleaners (a small sample of a report of this data is shown below):


Document B & C : See document_B_C attachments
 

You are free to make assumptions if needed however they must align with the details mentioned above 

TASKS
.
GIT STORAGE
All working files, as you work on this task, must be stored in GIT and must show a
clear history of development. 

Task to complete:

1. 
Perform normalisation to 3NF for the data depicted in the sample MC reports. You only need to do a single normalisation for the cleaner contract history (documents B & C) - two
documents have been provided so you are aware of possible variations in the data.

The approach you are required to use is the same approach as shown in the normalisation
tutorial solution. The normalisation must be carried out form by form, beginning by you
representing the document you are working on as a single UNF form and then moving
through 1NF, 2NF and 3NF.

During normalisation, you must:
•	Not add surrogate keys.
•	Include all attributes (you must not remove any attribute as derivable)
•	Clearly show UNF, 1NF, 2NF and 3NF.
•	Clearly identify the Primary Key in all relations.
•	Clearly identify all dependencies at the various normalisation stages (Partial at 1NF,
Transitive at 2NF and Full at 3NF). You should use the same notation as depicted in the normalisation sample solutions, for example: attr1 -> attr2, attr3 
If none exist you must note this by stating:
                  No partial dependencies present and/or
                  No transitive dependencies present
•	If required, carry out attribute synthesis.

The attribute names used in your normalisation and those on your subsequent logical model
must be the same.

2. 
Based on your task-1 conceptual model, your reading of this case study and the normalisations you carried out in step 1 above, prepare a logical level design for the Monash Cabins database.
•	The logical model must be drawn using the Oracle Data Modeler. The information engineering or Crow’s foot notation must be used in drawing the model. Your logical model must not show datatypes.
•	All relations depicted on this model must be in 3NF
•	You are required to add at least one surrogate key to your design (you are free to select the most appropriate relation to make this change in) - you may add more if you wish
•	All attributes must be commented in the database (ie. the comments must be part of the table structure, not simply comments in the schema file).
•	Check clauses/look up tables must be applied to attributes where appropriate.
•	You MUST include the legend as part of your model.
•	Note that your GIT repository must clearly indicate your development history with multiple commits/pushes as you work on your model.

3. 
Generate the schema for the database in Oracle Data Modeler and use the schema to
create the database in your Oracle account. The only edits you are permitted to carry out to
the generated schema file is to add header comment/s containing your details (student
name/id) and the commands to turn on and off spool/echo for your script. Ensure you:
•	Capture the output of the run of your schema statements using the spool command.
•	Ensure your script includes drop table statements at the start of the script.
•	Name the schema file as mc_schema.sql.

Submission Requirements

Task: Logical Model:

The following files are to be submitted and must exist in your FITGitLab server repo, along with the source documents from which they were generated:
● A pdf document showing your full normalisation of the sample MC documents showing all
normal forms (UNF, 1NF, 2NF and 3NF). Name the file mc_normalisation.pdf
● A single page pdf file containing the final logical Model you created in Oracle Data
Modeller. Name the file mc_logical.pdf. This pdf must be created via File - Data Modeler -
Print Diagram - To PDF File from within SQL Developer, do not use screen capture.
● A zip file containing your Oracle data modeler project (in zipping these files be sure you
include the .dmd file and the folder of the same name). Name the file mc_oraclemodel.zip.
● A schema file (CREATE TABLE statements) generated by Oracle Data Modeller. Name the
file mc_schema.sql
● The output from SQL Developer spool command showing the tables have been created.
Name the file mc_schema_output.txt
● A pdf document containing any assumptions you have made in developing the model or
comments your marker should be aware of. If you have made no assumptions, submit the
document with a single statement saying "No assumptions made". Name the file
mc_assumptions.pdf

These files must be submitted as individual files.

