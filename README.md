# Jump-Cloud-Assignment
This repository contains output for the QA assignment for Tom Foster

I have included separate documents for this assignemnt.  One is for the "Test Plan" and the other is an outline of test cases.  I will describe each below.

**Test Plan

Over my career, I have seen many different styles and formats of a test plan.  Their format and content seem to differ across various companies or even indiviual leads/managers within them.  They tend to be given in a template format and one simply fills out the various sections with the pertinent data.  Test plans have also evolved from the times of waterfall development to agile.  They have ventured from long, ridgid (read not agile) documents calling out every phase of test to leaner docuemnts just outling the very essential information.    

For this assignment, I have written my own stripped down format that falls somewhere in between;  It does contain most of the data pertinent to planning a test phase, but I attempted to keep it short for purposes of this assignemnt and because that seems to be the way test plans are heading in the agile world.  

**Test Cases

The included test cases are written in fairly simple manner.  I did not give exact steps for verification (like send this exact curl command) as I didn't feel it was necessary for this assignment.  The verification column is a description of what to do, not exactly how to do it.  If you would like those, I could surely provide them, but I figured you were more interested in the thought process than did I copy and paste curl commands exactly.

The test cases focus around a few areas.  First and foremost, the requirement specification is covered.  There are separate tests for application startup and port verification.  For each endpoint call, I wrote tests for their basic happy path funcitonality, formatting concerns, handling of different request types (send a POST to a GET endpoint), and to verify the correctness of their responses (including the hashing algorithm).  For shutdown, I wrote tests to verify that the application handles a simple shutdown request, the case of an existing request, and that it rejects any new requests. Finally, I have a test to verify the ability to process multiple connections at the same time.  

In summary, I have covered all of the requirement specifications explicitly, verified the data is correct, and I have written other negative tests to verify that the application handles things like incorrect format and input.

I have included a results column and my take on pass/fail, however I haven't listed the bugs themsevles as I figure we should leave something to talk about at a later date. 

**Assumptions

There were a few assumptions I made while writing the tests.  Lacking a spec that said otherwise, I assumed that basically all passwords were allowed to exist.  For instance, I don't really know of any place that allows a blank (or spaces in a) password, yet this applicaiton will has those characters.  There would probably be a set of tests to be written around password validation if it were specified, or maybe another application is handling the validation and is always passing valid data to this app.

I also punted on how to verfiy the AverageTime value was correct.  This is one case where I would have engaged in a discussion to learn how that value was supposed to be calculated (start/stop of request or of the hashing algorithm) and then designed an appropriate test.  If the timing was of the request, it is fairly easy to calculate using either  scripts to timestamp each request or use a tool like jMeter that automatically times such things.  If it was the timing of the algorithm, well its a bit tougher to verify as given.  In any case, the value is wrong most of the time...








