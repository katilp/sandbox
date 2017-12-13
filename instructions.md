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
        <li>on the linux prompt, type <code>root -l M4Lnormdatall.cc</code></li>
        <ul>
        <li> you will get the output plot on the screen</li>
      </ul>
      <li> either, on the ROOT canvas (picture) click <code>file->Quit ROOT</code>
        or, on the root [] prompt, type <code>.q</code></li>
       <ul>
        <li>you will exit ROOT and find the output plot in
           mass4l_combined_user.pdf</li>
         </ul>  
      <li> you can compare this plot with the plots provided in 1.</li>
</ul>
<li>   <b>Produce</b> a ROOT data input file from original data and MC files for one
   Higgs signal candidate and for the simulated Higgs signal with reduced
   statistics (for speed reasons) and reproduce the final output plot
   containing your own input using a ROOT macro
   (~few minutes to ~1 hour if Virtual machine is already installed,
     depending on internet connection and computer performance, up to
     ~few hours otherwise)</li>
   <ul>
     <li>if not already done follow instructions  for steps 1 and 2 in <a href=\"/docs/cms-virtual-machine-2011\"> CMS 2011 Virtual Machines: How to install</a></li>
      <li> in the <code>Demo/DemoAnalyzer/</code> which is created in Step 2: How to test and validate, replace <code>BuildFile.xml</code> by the version downloaded from this record</li>
      <li> download <code>HiggsDemoAnalyzer.cc</code> from this record to the <code>/src</code> subdirectory</li>
      <li> recompile <code>scram b</code></li>
      <li> download <code>demoanalyzer_cfg_level3data.py</code> (data example) and
        <code>demoanalyzer_cfg_level3MC.py</code> (Higgs simulation example)</li>
      <li> create datasets directory  <code>mkdir datasets</code></li>
      <li> change to this directory <li> <code>cd datasets</code></li>
      <li> download the 2012 JSON validation file from [http://opendata.web.cern.ch/record/1002] to this directory</li>
      <li>if not yet done at level 2, create the directory rootfiles and
        download all the level 2 root files to this directory (see level 2)</li>
      <li>run the two analysis jobs (one on data, one on MC, the input files
        are already predefined)
    <ul>       
        <li><code>cmsRun demoanalyzer_cfg_level3data.py</code>
        will produce output file <code>DoubleMuParked2012C_10000_Higgs.root</code>
        containing 1 Higgs candidate from the data</li>
        <li><code>cmsRun demoanalyzer_cfg_level3MC.py</code>
         will produce output file <code>Higgs4L1file.root</code>
        containing the Higgs signal distributions with reduced statistics</li>
     </ul>
     <li> move the two .root files above to the rootfiles directory, together
        with the predefined files</li>
      <ul>     
       <li><code>mv DoubleMuParked2012C_10000_Higgs.root rootfiles/.</code></li>
       <li><code>mv Higgs4L1file.root rootfiles/.</code></li>
     </ul>
         
      <li> change directory <code>cd rootfiles</code></li>
      <li> download the macro<code> M4Lnormdatall_lvl3.cc</code> to this directory</li>
      <li> on the linux prompt, type <code>root -l M4Lnormdatall_lvl3.cc</code></li>
       <ul> 
        <li>you will get the output plot on the screen;
        the magenta Higgs signal histogram will now be the one you produced,
        and the one data event which you have selected will be shown as a blue
        triangle</li>
         </ul> 
         <li> either, on the ROOT canvas (picture) click <code>file->Quit ROOT</code>
        or, on the root [] prompt, type <code>.q</code></li>
       <ul>
        <li>you will exit ROOT and find the output plot in
           mass4l_combined_user3.pdf </li>
  </ul>
<li>Reproduce the full example analysis
   (up to ~1 month or more on single CPU with fast internet connection,
    depending on internet connection speed and computer performance) </li>
<ul>
  <li>See detailed instructions in instructions.txt in this record.</li>
  </ul>
</ol> 
</p>
