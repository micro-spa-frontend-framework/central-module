Basic design:

A central project injected dynamically with different business modules. The framework should fulfill following requirement:

I.   SPA (Single Page Application), with decoupled business modules and a central module, the central module provide unified entry point;
II.  Central module should provide login/logout/sso support/privilege control/navigation support etc;
III. Common resourses such as css, 3rd party js libs, and common components should be in a common module named assets.
IV.  Simplified compile/build process, support to disable any unrelated modules during develpment; 
V.   Git-based version control, support independent version control for each modules.


The Central module structure:
|-Gulpfile.js 
|
|-Modules
  |
  |--- Dynamic imported business modules
  |--- Assets module shared with other projects
  |--- Central module code.

|-Dist
|-Navigation.json 

1. Gulpfile.js will define compile/build/test/install/package tasks.
2. Modules is the src code area, basically only contains the core functions such as login/logout/navigtaion/privilege control etc.Note, the
   Dynamic imported business modules are imported using gulp task (e.g. gulp import ${module-name}), developers can edit code there and push
   their commit under each module directory. 
3. Dist is the staging area that stores compiled resources, such as HTML/css/js etc. package task will use the content to create war file 



