Algorithum Steps:
example: python compare.py ./sessionStudents/ ./savedCodes/ 
this will do the following:
remove indentation from the sessionStudents codes
remove \newline from the sessionStudents code 
Count the number of unique coding lines in the code as Counted Line (CL). 
Compare the student code with all the codes in “savedCodes” by counting the  matching lines (ML) and saving them.
Calculate the matching ratio (MR) = ML/CL. 
Keep the highest three MR with the ML, then discard the rest. 
Repeat these steps for all the sessionStudents codes. 
Calculate the average CL(ACL) = sum(CL)/numberofStudents in sessionStudents
Calculate the average MR(AMR) = sum(MR)/numberofstudents in sessionStudents
Generate a note file (.txt) for the saved matchingline (highest three per student) with the MR.
Calculate the grade change for MR which is between -20 to 20 based on the (MR/AMR), since we have the highest three then this value can be averaged again based on the highest three. GradeChangeFromMatchingRation (GCFMR)
Calculate the grade change for CL which is between -10 to 10 based on the  (CL/ACL). GradeChangeFromMatchingRation (GCFCL)
Generate a .csv file with the CL, ML, MR, (CL/ACL), (MR/AMR), GCFMR, GCFCL, and sum of GradeChange. 

