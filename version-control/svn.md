# SVN - Subversion

Apache Subversion: https://subversion.apache.org/  
Subversion is an open source version control system.

SVN Quick Guide: https://www.tutorialspoint.com/svn/svn_quick_guide.htm

## Client

| Software | Description    | Website  |
| :------- | :------------- | -------: |
| TortoiseSVN | Apache Subversion client implemented as a Windows shell extention. | [tortoisesvn.net](https://tortoisesvn.net) |

## Commands

### Merge

`svn merge --reintegrate https://svn.companyname.be/projectname/branches/2.0.0_Refactoring/`

## Errors

### Node remains in conflict

After an update one or more files are in a conflicting state and cannot be resolved and updated automatically. To solve this, accept the local 'working' change of the file and reupdate.

Error message: `node remains in conflict`

Solution: 
`svn resolve --accept=working foldername/filename.txt`