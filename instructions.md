<p>There are four levels of increasing complexity for this example:
<ol>
<li> <b>Compare</b> the provided final output plot
   mass4l_combine.pdf
   or
   mass4l_combine.png
   to  <a href=\"https://inspirehep.net/record/1124338/files/H4l_mass_v3.png\">the published one</a>,
   keeping in mind the caveats mentioned in this record. </li>
<li><b>Reproduce</b> the final output plot from the predefined histogram files
   using a root macro
   (~few minutes - ~few hours, depending on setup and proficiency) </li>
<ul>
        <li> if a ROOT version on the local computer compatible with ROOT 5.32/00
        is running, use the local version (avoids installation of VM).
        Otherwise follow the instructions of the 2nd item of level 3
        in order to install the Virtualbox and CERNVM and run ROOT there
        (the validation step with the Demo example might be skipped)</li>
       <li>if not already proficient in ROOT, consider doing a brief ROOT
        introductory tutorial [link] in order to understand what the ROOT
        macro will do</li>
        <li>create a new directory, e.g. rootfiles <code>mkdir rootfiles</code></li>
        <li>switch to that directory <code>cd rootfiles</code>
        and download the preproduced *.root histogram files given in
        <a href=\"/record/FIXME\"> this record</a> for all relevant samples to this directory
        <li>download the ROOT macro
        <code>M4Lnormdatall.cc</code>
        from this record into the same directory</li>
        <li>on the linux prompt, type
<code>root -l M4Lnormdatall.cc</code></li>
        <li> you will get the output plot on the screen</li>
      <li> either, on the ROOT canvas (picture) click
file->Quit ROOT</code>
        or, on the root [] prompt, type <code>.q</code></li>
        <li>you will exit ROOT and find the output plot in
           mass4l_combined_user.pdf</li>
      <li> you can compare this plot with the plots provided in 1.</li>

  <li>The root files are available in a separate  <a href=\"/record/FIXME\">record</a> and the necessary root macros are attached to this record.</li>
</ul>
<li>   <b>Produce</b> a root data input file from original data and MC files for one
   Higgs signal candidate and for the simulated Higgs signal with reduced
   statistics (for speed reasons) and reproduce the final output plot
   containing your own input using a root macro
   (~few minutes to ~1 hour if Virtual machine is already installed,
     depending on internet connection and computer performance, up to
     ~few hours otherwise) </li>
   <ul>
  <li>See detailed instructions in instructions.txt in this record.</li>
  </ul>
<li>Reproduce the full example analysis
   (up to ~1 month or more on single CPU with fast internet connection,
    depending on internet connection speed and computer performance) </li>
<ul>
  <li>See detailed instructions in instructions.txt in this record.</li>
  </ul>
</ol> 
</p>
