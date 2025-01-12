# Generative AI Correction Criteria:

This repository present the main code used to compare and evaluate the usage of AI for coding assignment. 

## Usage steps

- create your directory that will contain the code history and the students code
- Generate code for the assignment you are asking for using the tools you like (ChatGPT, copilot, ...)
- Add the code to the savedCode directory, you can also include code from the internet related to the assignement or student code from previous batches.
- save all students code to the studentSession
- run the comper code
  - example: python compare.py ./studentSession/ ./savedCodes/

## Results

This code will check for any similarity between the student code and the other codes in the saved diectory. This can detect any copied code between students, or generative AI. 

Then Generate a txt and csv files that contains: 

- Matching ration (MR), which is matching ratio with the saved code
- Average matching ration (AMR), showing the which present the class matching ratio. this is the threshold for the class.
- expected grade chage that should be applied based on MR and counted lines (CL). Note that  GCFCL is optional to be applied.

## Algorithum Flow

- Remove indentation from the studentSession codes
- Remove \newline from the studentSession code
- Count the number of unique coding lines in the code as Counted Line (CL).
- Compare the student code with all the codes in “savedCodes” by counting the  matching
- lines (ML) and saving them.
- Calculate the matching ratio (MR) = ML/CL. Keep the highest three MR with the ML, then discard the rest.
- Repeat these steps for all the sessionStudents codes.
- Calculate the average CL(ACL) = sum(CL)/numberofStudents in studentSession
- Calculate the average MR(AMR) = sum(MR)/numberofstudents in studentSession
- Generate a note file (.txt) for the saved matchingline (highest three per student) with the MR.
- Calculate the grade change for MR which is between -20 to 20 based on the (MR/AMR), since we have the highest three then this value can be averaged again based on the highest three. GradeChangeFromMatchingRation (GCFMR)
- Calculate the grade change for CL which is between -10 to 10 based on the  (CL/ACL). GradeChangeFromMatchingRation (GCFCL)
- Generate a .csv file with the CL, ML, MR, (CL/ACL), (MR/AMR), GCFMR, GCFCL, and sum of GradeChange.
