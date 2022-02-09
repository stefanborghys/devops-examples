# SVN - Subversion

Apache Subversion: https://subversion.apache.org/  
Subversion is an open source version control system.

SVN Quick Guide: https://www.tutorialspoint.com/svn/svn_quick_guide.htm  
Version Control with Subversion: 
- https://svnbook.red-bean.com  
- https://svnbook.red-bean.com/en/1.7/index.html  
- https://svnbook.red-bean.com/en/1.7/svn-book.html  

## Client

| Software | Description    | Website  |
| :------- | :------------- | -------: |
| TortoiseSVN | Apache Subversion client implemented as a Windows shell extention. | [tortoisesvn.net](https://tortoisesvn.net) |

## Commands

### Create Branch

Creating a branch using the local `trunk` to copy from:
```
svn copy trunk branches/branch-name

cd branches
svn status 
svn commit -m "Creating new branch x"
```
> Warning! local incommitted changes on trunk will be copied.  
> Make sure only commit necessary changes.


### Merge

Basic Merging: https://svnbook.red-bean.com/en/1.7/svn.branchmerge.basicmerging.html

`svn merge --reintegrate https://svn.companyname.be/projectname/branches/2.0.0_Refactoring/`

### Delete Branch

`svn delete -m "Verwijderen branch" https://svn.companyname.be/projectname/branches/2.0.0_Refactoring/`

## Errors

### Node remains in conflict

After an update one or more files are in a conflicting state and cannot be resolved and updated automatically. To solve this, accept the local 'working' change of the file and reupdate.

Error message: `node remains in conflict`

Solution: 
`svn resolve --accept=working foldername/filename.txt`