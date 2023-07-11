Classes and Data Structures:
-----------------------------------
Main
    Fields:
        Method Calls
        Head pointer
        
GitLet  // Have all the methods defined here 
        private static File Gitlt; 
        private static Commit HEAD; //head pointer

Blob
    Fields:
        - private static File Blob  // create a folder under .gitlet for blobs
        - String sha; // blob identifier
        - String name; // name of file 
        - byte[] content; // entire current contents of file as bytes
        - public Blob(String name) // blob constructor holding name, content, sha1

Stage
    Fields:
        - private static File Stage // create a folder under .gitlet for staging area
        - static File StageAdd // file created for adds, under stage folder
        - static File StageRemove // file created for removals under stage folder
        - private static int count;
        

Commit
    Fields:
        - private static File Commit<Strings> // Create a folder under .gitlet for commits
        - timestamp(of the time in which commit was made) 
        - private String _message; // commit message (inputted at the time of commit command)
        - private String _parent; // SHA1 of previous commit
        - private HashMap<String, String> _blob; // maps sha1 ID to name of Blob
        - private static String id; // sha1 of current commit
        - private Date time; // timestamp
        - public Commit(String message, String parent) // Commit constructor holding message, parent, blob reference
Branches
    Fields:
        -static File Branches_folder = new File(".gitlet/BRANCHES"); //creates folder under gitlet
        - static HashMap<String, String> branches; // hashmap for the branch name to the commit id it is currently on
        - private String branchName; 
        - private String commitID;


Algorithms/Methods:
-----------------------------------
Class Main (current working directory)
    -Init
    -Add
    -Commit 
    -Rm ( remove the file from the working directory)
    -Log 
    -Find 

Class Commit (object for creating commit)
    Gitlet methods that will interact with Commit:
        - Init method (creating repo) [master and head pointers]
        - Mapping of file names to blob references
        - Log ( will start from master to the initial commit)
        - Global Log ( will display all commits done)
    Commit method:
       - public String get_HEAD() // returns id
       - public Date get_date() // returns timestamp of commit
       - public String get_parent() // returns sha of parent
       - public void printLog() // prints history commits for this branch

Class Blob ( More like storage)
    Gitlet methods that will interact with Blob:
        - Add (will add the file in blob area first)
        - Commit ( will add the objects using the commit methods)
    Blob methods:
        - public String getName() // returns name
        - public byte[] getContent() // returns content 
        - public String getSha() // returns sha
        - public static void makeBlob() // initializes blob folders
Class Stage 
        - public static void makeStage() // initializes the staging/adding/removing folders
        -  public static int give_count() // returns number of blobs in folder
        - public static File get_fileAdd() // returns the adding folder
        - public static void addFile(Blob blob) // adds the blob sha to adding folder,
                                                    writes blob object to staging folder                                        
Class Branches
    - Branches constructor: By creating new branch, will add the map of the branch name to the latest commit ID 
    - saves this object into a branches folder?
    - get commit id and branch name methods
        

Persistence: 
-----------------------------------
HashMaps:
    - Names of commits determined by SHA-1, commits hold the SHA-1 of their parents, 
      stores sha id and blob name reference in hashmap
    - Names of blobs determined by SHA-1, Blob contents serialized and stored as an array of bytes,
       put into Hashmap <SHA identifier, blobs>
   

   


