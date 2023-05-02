Download Link: https://assignmentchef.com/product/solved-cop4600-pr-1-system-call
<br>
<strong>Before you begin:</strong>

<ul>

 <li>Install VirtualBox and load Reptilian VM (see Ex-0).</li>

</ul>

<strong>Assignment:</strong>

<ol>

 <li>Create a new system call.</li>

 <li>Create procedure calls to access system call; install into the system library</li>

 <li>Create a man page accessible through the man command to document the new library calls, so man get_tag or man set_tag should display a man page for these system library calls (in section 2).</li>

 <li>Write a short report describing what you did, any challenges you encountered, how you got past them, how you tested your code, any known bugs/limitations</li>

 <li>Produce a patch file to apply updates and submit this.</li>

</ol>

I have provided <span class="instructure_file_holder link_holder"><a class="instructure_file_link" title="gettag.c" href="https://ufl.instructure.com/courses/389574/files/47444420/download?wrap=1" target="" rel="noopener noreferrer" data-api-endpoint="https://ufl.instructure.com/api/v1/courses/363046/files/41565131" data-api-returntype="File" data-id="47444420">gettag.c</a><a class="file_preview_link" title="Preview the document" href="https://ufl.instructure.com/courses/389574/files/47444420/download?wrap=1" aria-hidden="true" data-id="47444420"><img decoding="async" alt="Preview the document" data-recalc-dims="1" data-src="https://i0.wp.com/ufl.instructure.com/images/preview.png?w=980&amp;ssl=1" class="lazyload" src="data:image/gif;base64,R0lGODlhAQABAAAAACH5BAEKAAEALAAAAAABAAEAAAICTAEAOw==">

   <noscript>

    <img decoding="async" alt="Preview the document" data-recalc-dims="1" data-src="https://i0.wp.com/ufl.instructure.com/images/preview.png?w=980&amp;ssl=1" class="lazyload" src="data:image/gif;base64,R0lGODlhAQABAAAAACH5BAEKAAEALAAAAAABAAEAAAICTAEAOw==">

    <noscript>

     <img decoding="async" alt="Preview the document" data-recalc-dims="1" data-src="https://i0.wp.com/ufl.instructure.com/images/preview.png?w=980&amp;ssl=1" class="lazyload" src="data:image/gif;base64,R0lGODlhAQABAAAAACH5BAEKAAEALAAAAAABAAEAAAICTAEAOw==">

     <noscript>

      <img decoding="async" src="https://i0.wp.com/ufl.instructure.com/images/preview.png?w=980&amp;ssl=1" alt="Preview the document" data-recalc-dims="1">

     </noscript>

    </noscript>

   </noscript></a></span> and <span class="instructure_file_holder link_holder"><a class="instructure_file_link" title="settag.c" href="https://ufl.instructure.com/courses/389574/files/47444421/download?wrap=1" target="" rel="noopener noreferrer" data-api-endpoint="https://ufl.instructure.com/api/v1/courses/363046/files/41565134" data-api-returntype="File" data-id="47444421">settag.c</a><a class="file_preview_link" title="Preview the document" href="https://ufl.instructure.com/courses/389574/files/47444421/download?wrap=1" aria-hidden="true" data-id="47444421"><img decoding="async" alt="Preview the document" data-recalc-dims="1" data-src="https://i0.wp.com/ufl.instructure.com/images/preview.png?w=980&amp;ssl=1" class="lazyload" src="data:image/gif;base64,R0lGODlhAQABAAAAACH5BAEKAAEALAAAAAABAAEAAAICTAEAOw==">

   <noscript>

    <img decoding="async" alt="Preview the document" data-recalc-dims="1" data-src="https://i0.wp.com/ufl.instructure.com/images/preview.png?w=980&amp;ssl=1" class="lazyload" src="data:image/gif;base64,R0lGODlhAQABAAAAACH5BAEKAAEALAAAAAABAAEAAAICTAEAOw==">

    <noscript>

     <img decoding="async" alt="Preview the document" data-recalc-dims="1" data-src="https://i0.wp.com/ufl.instructure.com/images/preview.png?w=980&amp;ssl=1" class="lazyload" src="data:image/gif;base64,R0lGODlhAQABAAAAACH5BAEKAAEALAAAAAABAAEAAAICTAEAOw==">

     <noscript>

      <img decoding="async" src="https://i0.wp.com/ufl.instructure.com/images/preview.png?w=980&amp;ssl=1" alt="Preview the document" data-recalc-dims="1">

     </noscript>

    </noscript>

   </noscript></a></span> programs for basic testing; these should compile without any special compiler directives or additional .o files or libraries.

That is, a line like

$ cc gettag.c -o gettag

should produce gettag, which can be run from the shell and allows the root user to get the tag value of an existing process (say, PID 123) using

$ ./gettag 123

0

Likewise, settag should compile as easily and if run by the root user should allow the tag value of an existing process to be changed (the new tag value is returned), e.g.,

$ ./gettag 123

0

$ ./settag 123 5

5

$ ./gettag 123

5

$

If a non-root user tries to do either, the call should fail. You will have to write some additional test code to check all cases required, but this should get you started.

If you have not modified the unistd.h file or the unix standard library, yet, then you can still test the calls by including your own .h file and adding your own .o file to the compile command (but DO fix this before submitting!). So if your .h file is p1.h and library file is p1.o, then

cc gettag.o p1.o -o gettag

after modifying gettag.c to have #include “p1.h” in it should also produce the command program gettag.

Only include text entry with submission if necessary.

Further details in <span class="instructure_file_holder link_holder"><a class="instructure_file_link" title="proj1sp19r1.txt" href="https://ufl.instructure.com/courses/389574/files/47444450/download?wrap=1" data-api-endpoint="https://ufl.instructure.com/api/v1/courses/363046/files/42082840" data-api-returntype="File" data-id="47444450">project 1 description</a><a class="file_preview_link" title="Preview the document" href="https://ufl.instructure.com/courses/389574/files/47444450/download?wrap=1" aria-hidden="true" data-id="47444450"><img decoding="async" alt="Preview the document" data-recalc-dims="1" data-src="https://i0.wp.com/ufl.instructure.com/images/preview.png?w=980&amp;ssl=1" class="lazyload" src="data:image/gif;base64,R0lGODlhAQABAAAAACH5BAEKAAEALAAAAAABAAEAAAICTAEAOw==">

   <noscript>

    <img decoding="async" alt="Preview the document" data-recalc-dims="1" data-src="https://i0.wp.com/ufl.instructure.com/images/preview.png?w=980&amp;ssl=1" class="lazyload" src="data:image/gif;base64,R0lGODlhAQABAAAAACH5BAEKAAEALAAAAAABAAEAAAICTAEAOw==">

    <noscript>

     <img decoding="async" alt="Preview the document" data-recalc-dims="1" data-src="https://i0.wp.com/ufl.instructure.com/images/preview.png?w=980&amp;ssl=1" class="lazyload" src="data:image/gif;base64,R0lGODlhAQABAAAAACH5BAEKAAEALAAAAAABAAEAAAICTAEAOw==">

     <noscript>

      <img decoding="async" src="https://i0.wp.com/ufl.instructure.com/images/preview.png?w=980&amp;ssl=1" alt="Preview the document" data-recalc-dims="1">

     </noscript>

    </noscript>

   </noscript></a></span>.

<strong>P1 – System Call Project </strong>










<h1>Overview</h1>

You will implement a system call in your OS along with two library functions in the system library API that allow the system call to be invoked from a C program. We will provide a program that exercises and demonstrates the new call. You will then create a short video to demonstrate your code and submit the project via Canvas.

<strong>NOTE: Take Snapshots in VirtualBox! You will most likely brick your machine at some point during this or other projects, and you will not want to start from scratch. <u>No, seriously – take snapshots!</u></strong>




<h1>Structure</h1>

The project is broken into four main parts:




<ul>

 <li>Create system calls that allow a process to “get” or “set” a tag for a process.</li>

 <li>Create system library wrapper functions that allow the system calls to be invoked from a C program.</li>

 <li>Add manual page entries for the system calls and the C library calls. 4) Create a report and a short screencast to explain what you did.</li>

</ul>




While exact implementation may vary the system library functions must match the signatures laid out in this document, and the system calls must get and set tags properly.




<h2>System Call</h2>

Each process in the modified system will have a 32-bit tag. A tag has a structure of two bits of level (the two LSBs) and 29 bits of bitmap (bits 2 through 30). The MSB shall be set to 0 always. Level ranges from zero (low) to three (high). Treated as an unsigned integer, tags can take values between 0 and 2<sup>31</sup>-1. Tags for this system will behave as follows:




<ul>

 <li>Any process that does not have a parent shall have a tag of 0x00000000.</li>

 <li>All child processes shall inherit the tag of their parent process (all 32 bits of it).</li>

 <li>A process running as the <u>superuser</u> may read and write the tag of any process (all 32 bits of it, but it still cannot set the MSB to 1).</li>

 <li>A user process has <u>read-only</u> access to the tag of any process.</li>

 <li>A user process may decrease its own level, but not increase it.</li>

 <li>A user process may reset a bit in its tag’s bitmap to zero but not set a bit.</li>

</ul>




The tag for each process must be stored in the process table. There must also be corresponding kernel system calls named get_tag and set_tag. Other aspects of their signatures may vary. The system calls are invoked from user space via syscall(call_number, param1, param2).<em> <strong>Your system call must be limited to no more than <u>two</u> parameters!</strong></em>




<h2>Static Library</h2>

You will create a static library that provides and API to invoke the system calls in a directory named <strong>tags</strong>. This will be composed of a header with name <strong>tags.h</strong> and a static library file named <strong>libtags.a</strong><em>.</em> You will also need to provide a Makefile for this library in the <strong>tags</strong> directory. All other sources must be contained within the <strong>tags</strong> directory. Please note, <em><u>these names of the files must match exactly!</u></em>




You will create a tarred gzip file of the <strong>tags</strong> directory with name <strong>tags.tar.gz</strong>. When testing your code, we will decompress the archive, enter the <strong>tags</strong> directory, and build. All functions enumerated below must be made available by including <strong>“tags.h”</strong>. See <em>Submission</em> for details.




In addition to the standard library functions, you will implement testing harness functions. The testing harness functions are used to verify the system calls from the system library (and are required for full credit on this assignment). We will call these functions to retrieve the information needed to make a system call. We will then call the system call within our own program. This ensures that the implementation is not being done in the user-level library.

<u>Library Functions</u>

These functions provide primary functionality to user programs. They should be made available by including &lt;tags.h&gt;.

<em> int set_tag(int pid, int new_tag)</em>

Invokes system call which attempts to change the tag of the process identified by <strong><sub>pid</sub></strong> to the new tag value <strong>new_tag</strong>. Returns <strong>new_level</strong> on success, and <strong>-1</strong> otherwise.




<em>int get_tag(int pid)</em>

Invokes system call which reads the tag of the process identified by <strong><sub>pid</sub></strong>. Returns the access level on success, and <strong><sub>-1</sub></strong> otherwise.




<u>Harness Functions</u>

These functions serve as a testing harness to verify the system calls and are required for full credit on this assignment. They shall be made available by including <sub>&lt;harness.h&gt;</sub>.

<em> </em>

System call parameter retrieval data shall be returned as a <u>pointer</u> to an <strong><sub>int</sub></strong> <u>array</u> of 2-4 values that can be used to make the system call. The array has this format:




{ call_number, num_parameters [, parameter1] [, parameter2] }




e.g.: { 42, 2, 867, 5309 } → syscall(42, 867, 5309)

<em> </em>

<em>int*</em> <strong>retrieve_set_tag_params</strong>(int pid, int new_tag)

Returns an <strong><sub>int</sub></strong> array of 2-4 values that can be used to make the set-tag system call.




<em>int*</em> <strong>retrieve_get_tag_params</strong>(int pid)

Returns an <strong><sub>int</sub></strong> array of 2-4 values that can be used to make the get-tag system call.




<em>int</em> <strong>interpret_set_tag_result</strong>(int ret_value)

After making the system call, we will pass the syscall return value to this function call. It should return <strong>set_tag</strong>’s interpretation of the system call completing with return value <strong>ret_value</strong> (i.e., what the library call should return to the user program).




<em>int</em> <strong>interpret_get_tag_result</strong>(int ret_value)

After making the system call, we will pass the syscall return value to this function call. It should return <strong>get_tag</strong>’s interpretation of the system call completing with return value <strong>ret_value</strong> (i.e., what the library call should return to the user program).




<h2>Revised Extra Credit</h2>

The system library is the means by which a process may invoke the system call in a program. For five points extra credit you may discover where the default library path and the default include path is. Make an addition to the makefile that when executed with `sudo make install` will install the project files (headers &amp; library) files into the proper paths. If done correctly, you should be able to compile the get_tag and set_tag sources to executables without any -I or -L flags in gcc.

(This is in lieu of the much more challenging former extra credit of adding system library functions to the standard C library for your system.)




<h2>Manual Pages</h2>

You are required to create manual pages detailing the two system calls and the four library function calls. These manual pages shall be in man page format and in the appropriate manual section; you may copy and modify an existing man page for this purpose.

You may also “double up” on the man pages by creating a single man page that handles a pair of calls (e.g., the library calls for both <strong>get_tag</strong> and <strong>set_tag</strong>). This can be accomplished by including both calls in the page, saving with the name of one of the calls, then making a hard link for the second call’s man page (e.g., if you created get_tag.2, then ln get_tag.2 set_tag.2 will allow that file to be accessed as either get_tag.2 or set_tag.2 – see for example fopen(3)). This way, you can create three manual pages instead of six (as long as each man page addresses two calls).

You must place each new man page in the proper location so that entering the command <strong>man &lt;S&gt; set_tag</strong> or <strong>man &lt;S&gt; get_tag</strong> will return the man page for these calls in section &lt;S&gt;. You may check the manual path using the <strong>manpath(1)</strong> command to see where the man pages are, and type “man man” to see how the sections are arranged. At a minimum, the man page must have proper header/footer, name, synopsis, description, errors, notes, see also, and author.

<strong> </strong>

<h1>Testing</h1>

You should test your code for all behavioral cases. You will include this information in your report and demonstrate the tests in your screencast video. You must also test that all your man pages display properly.

<h1>Submissions</h1>

You will submit the following at the end of this project:




<ul>

 <li>Report (<strong>txt</strong>) in man page format on Canvas, including link to <u>unlisted</u> screencast video</li>

 <li>Kernel Patch File (<strong>diff</strong>) on Canvas that includes sourcecode, makefile(s), and man pages</li>

 <li>Compressed tar archive (<strong>tar.gz</strong>) for <strong>tags</strong> library on Canvas</li>

</ul>




<h2>Report</h2>

Your report will explain how you implemented the new system calls, including what changes were made to which files and why each change was made.  It will include description of how testing was performed along with any known bugs. The report must be created using <strong>man</strong> format and be named <strong>p1.txt</strong>. The report should be no more than two pages and should cover all relevant aspects of the project. It must also include a link to an unlisted screencast video. The report must be organized and formatted professionally – <strong><em>this is not a memo!</em></strong>




<h2>Screencast</h2>

In addition to the written text report, you should submit a screencast (with audio) walking through the changes you make to the operating system to enable the system calls. Additionally, the screencast should include you showing/demonstrating your changes in action using your tests. (It should take no more than 5 minutes).




<h2>Patch File</h2>

The patch file will include all changes to all files in a single patch. Applying the patches and remaking the necessary parts of the OS, then rebooting and then building the test code (which we will also copy over) should compile the test program and link in the new library object code. Typing “man &lt;S&gt; set_tag” shall display the man page for set_tag in section &lt;S&gt;, and typing “man &lt;S&gt; get_tag” shall display the man page for get_tag in section &lt;S&gt;.


