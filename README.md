# InsertCoin ROM documentation project

Welcome to the official [community-driven documentation project](http://docs.insertcoin-roms.org)
for InsertCoin ROM.

If you want to contribute to this project, you're free to fork the Git repository,
work on it and then send a pull request. We'd love to merge your changes.

Currently the project is in a very early stage, so noob-proof instructions on how
to participate are still being worked on. Stay tuned! If you already know what Git is
and how to use it, you're welcome to start working on the project right now.

## File naming conventions and folder structure
The documentation is automatically fetched by a staging server which generates a
documentation website from the source files in this repository. To make your
files appear correctly on this website you have to follow five guidelines:

 * Docs for a specific major or minor version are stored in separate branches
   named *major.minor* (e.g. 2.3 for everything that's specific to Version 2.3.x).
   The current version is always stored in the master branch, which is the top-most
   branch. If you don't know what branches are and how to use them and you actually
   don't care to write docs for older versions, ignore all this stuff about branches.
   It doesn't matter then. Just commit to the repository and changes should
   automatically be recorded in the master branch, i.e. in the branch for the
   latest InsertCoin version.
 * You can create as many folders as you like, but you should keep the directory
   structure shallow. The directories can have any name, but they should not contain
   special caracters or spaces.
   Each new directory should contain a file called *index.markdown* which is the
   default file for this directory.
 * The top-most directory defines the language. Its name must be a language code
   (e.g. en-US for American English, en-GB for British English, de-DE vor German,
   de-AT for Austrian German etc.). If you want to start a translation, just copy over
   the en-US folder, rename it to your language and start translating.
 * The docs are written in Markdown, a very simple markup language. You might already
   know it from several blogs or wikis. These files MUST have the extension  *.markdown*
   (only lowercases, no spaces). Otherwise they will be ignored by the staging
   server. If you want to upload other files (e.g. images) create a folder called
   *assets* in your current directory. This folder can contain files with any extension.
   Note that each file should at least contain one first-level heading. This is
   used by the staging server to extract the page title.
 * You can link your files by using the Markdown link syntax. However, you shouldn't
   link your files as *file.markdown* but as *file.html* since the file extension will
   be rewritten by the staging server. Use absolute paths containing the branch and the
   language you want to link (if you haven't checked out any specific branch, your
   branch is always *master*). That is, if you want to link a file *en-US/foo/bar.markdown*
   in the master branch use */master/en-US/foo/bar.html* (mind the leading slash
   and the file extension!).

That's it. You can get more information about the Markdown syntax on
[Wikipedia](http://en.wikipedia.org/wiki/Markdown) or the
[official Markdown documentation](http://daringfireball.net/projects/markdown/).
Note that you can *only* use Markdown. HTML is not allowed and will be escaped
by the staging server.

## A few things about writing style, grammar and spelling
In an ideal world, docs are a pleasure to read. Actually, this can't be always the
case but we also shouldn't make things worse than necessary.

When you write for the docs, make sure, you use plain sentences with correct grammar
and spelling (in the English docs as well as in any other language). If you're not
a native speaker, this is not a serious issue. Just try to avoid very obvious mistakes.
Don't use chat slang, offending language, unnecessary technical terms or too many
abbreviations.

Also make sure the text you wrote is not just a list of things but a text consisting of full
sentences. Lists my be appropriate when it comes to step-by-step instructions, but
they should be use rarely and deliberately.

Check if there isn't already a similar thing documented before creating a new
file. Better extend an existing one if possible. If you create a new page, don't
foget to add it do the index file.

## And the credit goes to…
Have you worked on the docs? Great! The least we can do is to credit that to you.
Feel free to add you to the *credits.markdown* file. You can use your real name
or any pseudonym you like (both is also okay). If you like, you can also set a link
to your homepage (unless it contains unlawful, offending, pornographic or otherwise
inappropriate content, of course).

You may also add you to this file if you just corrected a spelling mistake or so.
That is also important work which needs to be done and not many people feel like
doing it.

## Where can I find the live version?
The staging server can be found on [docs.insertcoin-roms.org](http://docs.insertcoin-roms.org).
This copy will always contain the latest revisions from all branches parsed to HTML.
If people ask you something about InsertCoin direct them to this website.