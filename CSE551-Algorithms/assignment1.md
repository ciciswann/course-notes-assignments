<h3>Hospital Resident Problem</h3>

**Problem:**

Gale and Shapley published their paper on the Stable Matching Problem in 1962; but a version of their algorithm had already been in use for ten years by the National Resident Matching Program, for the problem of assigning medical residents to hospitals.

Basically, the situation was the following. There were m hospitals, each with a certain number of available positions for hiring residents. There were n medical students graduating in a given year, each interested in joining one of the hospitals. Each hospital had a ranking of the students in order of preference, and each student had a ranking of the hospitals in order of preference. We will assume that there were more students graduating than there were slots available in the m hospitals.

The interest, naturally, was in finding a way of assigning each student to at most one hospital, in such a way that all available positions in all hospitals were filled. (Since we are assuming a surplus of students, there would be some students who do not get assigned to any hospital.)

We say that an assignment of students to hospitals is stable if neither of the following situations arises.

First type of instability: There are students s and s′, and a hospital h, so that

– s is assigned to h, and

– s′ is assigned to no hospital, and

– h prefers s′ to s.

Second type of instability: There are students s and s′, and hospitals h and h′, so that

– s is assigned to h, and

– s′ is assigned to h′, and

– h prefers s′ to s, and

– s′ prefers h to h′.

So, we basically have the Stable Matching Problem, except that (i) hospitals generally want more than one resident, and (ii) there is a surplus of medical students.

**Work**

Time Complexity: O(mn)

Algorithm: 
  ```
  while some hospital h has available positions
    h offers residency to the next student s on preference list
    if s is available then
      s accepts offer
    else (s is already committed to hospital h') 
      if s prefers h' over h then
        s remains commited to h'
      else s becomes commited to h
           number of positions available at h decreases by one
           number of positions available at h' increases by one
  ```
