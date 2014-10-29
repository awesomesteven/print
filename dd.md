Data Dictionary
---------------


Admin
---------------

Parent: PCChair

| Attribute | Description |
| :------ | ----------- |


| Method | Description |
| :------ | ----------- |
| Admin() | Constructor |
| ~Admin() | Destructor |
| createUser() | Create a user |
| createUser() | Lets admin create a user |
| setUserType() | Sets a user's account type |
| approveUser() | Approves a user |
| resetUserPassword() | Resets a user's password |
| setPCChair() | Set the PCChair for a conference |
| createConference() | Create a conference |
| removeConference() | Delete a conference |
| deleteUser() | Delete a user |
| showUsers() | Shows a list of users |
| showMenu() | Shows the user interface |

------------------------------


Author
---------------

Parent: User

| Attribute | Description |
| :------ | ----------- |
| researchTopics | List of research topics |
| pcMemberInvite | Has the author been invited to become a PC Member? |


| Method | Description |
| :------ | ----------- |
| scanPapersDirectory() |  TODO: Make file containing metadata of all papers in Papers directory |
| Author() |  Searches for papers in program's Papers directory |
| Author() |  Uses given papers arg |
| addPaper() | Submit a paper  |
| checkMyPaperStatus() | Check the status of this user's paper |
| updateResearchTopics() | Update the list of research topic this user has |
| deletePaper() | Delete an existing paper |
| presentFinalPaperSubmission() | Submit a final version of paper (if original paper was approved) |
| reviewReply() | Reply to a review  |
| acceptPCInvite() | Accept an invitation to be on the programme committee |
| modifyPaper() | Modify and existing paper |
| addRebuttal() | Add a rebuttal to a review |
| showMenu() | Shows the user interface |

------------------------------


Conference
---------------

Parent: none

| Attribute | Description |
| :------ | ----------- |
| name | The name of the conference |
| topic | The topic of the conference |
| date | The date of the conference |
| location | The location of the conference |
| uuid | The uuid of the conference |
| reviewsOpen | True: reviews can be submitted / False: reviews cannot be submitted |
| rebuttalOpen | True: rebuttals can be submitted / False: rebuttals cannot be submitted |
| forumOpen | True: forum is open / False: forum is closed |
| biddingOpen | True: bids for papers can be submitted / False: bids for papers cannot be submitted |
| papersOpen | True: papers can be submitted / False: papers cannot be submitted |
| Authors | Holds all the authors associated with a conference |
| PCMembers | Holds all the pc members associated with a conference |
| PCChairs | Holds all the pc chairs associated with a conference |
| papers | Holds all the papers associated with a conference |
| reviews | Holds all the reviews associated with a conference |
| global_max_papers | The default maximum number of reviews per paper |
| notifications | Holds all the notifications associated with a conference |
| forums | Holds all the forums associated with a conference |
| reviewAllocations | Holds reviews allocations associated with a conference |
| paperBids | Holds bids for papers associated with a conference |


| Method | Description |
| :------ | ----------- |
| Conference() | Create a new conference |
| updateDetails() | Edit the details of the conference |
| generateSchedule() | Automatically generate the conference's schedule |
| overrideSchedule() | Manually edit the conference's schedule |
| toggleReviews() | Turn the ability to make a review on/off |
| toggleRebuttal() | Turn the ability to rebuttal a review on/off |
| toggleForum() | Turn the ability to make a forum post on/off |
| toggleBidding() | Turn the ability to make a bid on/off |
| togglePapers() | Turn the ability to submit a paper on/off |
| listPapers() | Lists all papers associated with a conference |
| notifyAll() | Notify all users associated with a conference |
| deletePaper() | Delete an existing paper |

------------------------------


ConferenceBank
---------------

Parent: none

| Attribute | Description |
| :------ | ----------- |
| conferences | Holds the conferences |
| currentConference | Holds a pointer to the current conference |


| Method | Description |
| :------ | ----------- |
| newConf() | Creates a new conference |
| listConfs() | Lists all conferences |
| save() | Saves all conference data |
| load() | Loads all conference data |

------------------------------


PCChair
---------------

Parent: PCMember

| Attribute | Description |
| :------ | ----------- |


| Method | Description |
| :------ | ----------- |
| PCChair() | Constructor |
| ~PCChair() | Destructor |
| viewPCMembers() | Shows a list of PC Members |
| checkStatusOfReview() | Shows the submissions status of a review |
| approvePaper() | Allows the PC Chair to approve a paper |
| viewPCDetails() | Shows finer details about a PC Member |
| inviteAuthorToPC() | Allows the PC Chair to invite an author to become a PC Member |
| setAllMaxPapers() | Allows the PC Chair to set the default max of papers one can review |
| rejectPaper() | Allows the PC Chair to reject a paper |
| autoAllocatePapers() | Automatically allocates papers to review |
| manuallyAllocatePaper() | Allows the PC Chair to manually assign a paper to a PC Member for review |
| setMaxPaperReviews() | Sets the max number of reviews a single paper can get |
| setReviewerPapers() | Sets the max number of papers a single PC Member can review |
| accessAllForums() | Allows PC Chair to access all forums except their own paper |
| showMenu() | Shows the user interface |

------------------------------


PCMember
---------------

Parent: Author

| Attribute | Description |
| :------ | ----------- |
| max_papers | The limit to how many papers this user can review |
| personal_paper_limit | Indicates if the PC member has a personal limit on the number of papers he can review, or not |


| Method | Description |
| :------ | ----------- |
| bidForPaperReview() | Bid for the opportunity to review a particular paper |
| reviewPaper() | Review a paper |
| showMenu() | Shows the user interface |
| editReview() | Edit an existing review |
| discussReviews() | Discuss existing reviews of papers |

------------------------------


Paper
---------------

Parent: none

| Attribute | Description |
| :------ | ----------- |
| paperID | Holds the unique id of the paper |
| title | Holdes the titles of the paper |
| authors | Holds the authors of the paper |
| abstract | Holds the abstract of the paper |
| max_reviewers | Max reviews of the paper |
| contentPath | Path on disk to the paper |
| relativeContentPath | True: path is relative, False: path is not relative |
| submitted | True: paper has been submitted, False: paper has not been submitted |
| final | True: paper has been submitted as final, False: paper has not been submitted as final |
| approvalStatus | True: paper has been approved, False: paper has not been approved |


| Method | Description |
| :------ | ----------- |
| submit() | Submits the paper |
| updateMetadata() | Updates the paper's metadata |
| isContentPathValid() | Checks to see if the file exists |
| findSupportedFiles() | Finds papers on disk |

------------------------------


Review
---------------

Parent: none

| Attribute | Description |
| :------ | ----------- |
| reviewID | The review's unique id |
| paperID | The corresponding paper's ID |
| username | Username of who made the review |
| strengths | Strengths of the paper |
| weaknesses | Weaknesses of the paper |
| comments | Detailed comments and suggestions |
| shortList | Is this paper short? |
| canBeBest | Should this paper be considered for a best paper award? |
| shouldBedDiscussed | Agree or Disagree if the paper should be discussed |
| overall | Overall rating (-3 to 3) |
| confidence | Reviewer's confidence (0 to 4) |
| relevance | Relevance of the paper (1 to 5) |
| presentation | Presentation of the paper (1 to 5) |
| technical | Technical Quality (1 to 5) |
| evaluation | Evaluation (1 to 5) |
| originality | How original is this paper (1 to 5) |
| significance | How significant is this paper (1 to 5) |
| pcComments | Additional comments for PC members (and Chair) only |


| Method | Description |
| :------ | ----------- |
| editReview() | Edits the review |

------------------------------


ReviewBank
---------------

Parent: none

| Attribute | Description |
| :------ | ----------- |
| vec | Holds all the reviews |


| Method | Description |
| :------ | ----------- |
| add() | Adds a review |

------------------------------


ReviewAllocation
---------------

Parent: none

| Attribute | Description |
| :------ | ----------- |
| username | Username of the user |
| paperID | ID of the paper to review |
| submission_status | Has the review been submitted |
| review_id | ID of the review |


| Method | Description |
| :------ | ----------- |

------------------------------


ReviewAllocationBank
---------------

Parent: none

| Attribute | Description |
| :------ | ----------- |
| reviewAllocations | Holds the allocations of review jobs |


| Method | Description |
| :------ | ----------- |
| add() | Adds a review |

------------------------------


PaperBid
---------------

Parent: none

| Attribute | Description |
| :------ | ----------- |
| interestStatus | Can we None, Interested, Conflict of Interest |
| paperID | ID of the paper |
| user | Username of the user who bid |


| Method | Description |
| :------ | ----------- |

------------------------------


User
---------------

Parent: none

| Attribute | Description |
| :------ | ----------- |
| username | The name the user uses to login |
| password | The password the user users to login |
| name | The user's full name |
| email | The user's email |
| university | The university that the user is representing |
| interests | Array of Interests for possible papers to review |
| account_confirmed | Is the account confirmed? |
| user_id | Unique internal ID |


| Method | Description |
| :------ | ----------- |
| updateEmail() | Update the user's email. |
| updatePassword() | Update the user's password |
| updateInterests() | Update the user's interests |
| showNotifications() | Gets the user's notifications eg. New programme committee invite |
| joinConference() | Join the user to a conference |
| showMenu() | Shows the user interface |

------------------------------


UserDatabase
---------------

Parent: none

| Attribute | Description |
| :------ | ----------- |


| Method | Description |
| :------ | ----------- |
| loadUserInterests() | Load User Interests from disk |
| loadUserResearchTopics() | Load User Research Topics from disk |
| loadDatabase() | Load user database from disk |
| saveDatabase() | Saves user database to disk |
| UserDatabase() | Constructor loads the users from the file |
| ~UserDatabase() | Destructor saves the users to the disk |
| shared() | Shared instance that has to be called when wanting the instance |

------------------------------


ForumPost
---------------

Parent: none

| Attribute | Description |
| :------ | ----------- |
| forumPostID | Unique ID of the comment |
| username | The username of the person who made the comment |
| paper_id | The ID of the paper the comment is about |
| comment | The text of the comment made |


| Method | Description |
| :------ | ----------- |
| ForumPost() | Constructor |

------------------------------


Forums
---------------

Parent: none

| Attribute | Description |
| :------ | ----------- |
| posts | Holds all the forum posts |
| counter | Holds an incrementing counter to assign unique ids |


| Method | Description |
| :------ | ----------- |
| add() | Adds a new forum post |
| remove() | Deletes a forum post by ID |

------------------------------


notifications
---------------

Parent: none

| Attribute | Description |
| :------ | ----------- |
| username | Username of who the notification is for |
| message | Content of the notification |


| Method | Description |
| :------ | ----------- |

------------------------------


notificationBank
---------------

Parent: none

| Attribute | Description |
| :------ | ----------- |
| notificationVec | Holds all notifications |
| notificationFile | Where to save notifications to file |


| Method | Description |
| :------ | ----------- |
| addNotification() | Add a notification to the bank |
| showNotifications() | Show notifications for a user |

------------------------------

