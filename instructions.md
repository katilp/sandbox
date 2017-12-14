<p>If you do not have the CERN Virtual Machine for 2011 CMS data installed, follow the instructions in step 1 at <a href=\"/docs/cms-virtual-machine-2011\">How to install a CERN Virtual Machine</a>.</p> <p>You can setup the example with the detailed instructions below, if you want to get insight on how to build your own analysis and what are the files needed. Install and run the Demo (demo analyzer) program as instructed in <a href=\"/docs/cms-virtual-machine-2011#test\">step 2 at 'How to install a CERN Virtual Machine'</a>. Then <ol> <li>Create directory <code>datasets</code> under <code>Demo/DemoAnalyzer</code></li>\n <li>Download the index files for the <a href=\"/record/17\">/DoubleMu/Run2011A-12Oct2013-v1/AOD</a> primary dataset (default) to the <code>Demo/DemoAnalyzer/datasets</code> directory</li>. Only the first index file is actually needed for initial running. You can also use other primary datasets containing muons from 2011 or 2012 as listed under "Use With" above.</li>\n <li>Download <a href=\"/record/1001\">the 2011 JSON validation file</a> (default) or <a href=\"/record/1002\">the 2012 JSON validation file</a> (if needed) to the <code>Demo/DemoAnalyzer/datasets</code> directory</li>.\n <li>Replace the three files <code>BuildFile.xml</code>, <code>demoanalyzer_cfg.py</code>, <code>src/DemoAnalyzer.cc</code> with the ones from this record and read the comments in <code>DemoAnalyzer.cc</code> for more details.</li>\n <li>Recompile (<kbd>scram b</kbd>) and run (<kbd>cmsRun ...</kbd>).</ol></p>  <p>You should get an output file <kbd>DoubleMu.root</kbd>, which contains histograms for 10000 input events (a small subset of the data). These can be looked at using a ROOT Browser. The most interesting histogram is <kbd>GM_mass_log</kbd>. In order to compare it with the invariant-mass spectrum of di-muons in <a href=\"https://inspirehep.net/record/1118729/plots\">MUO-10-004</a>, it should be viewed with the <kbd>logy</kbd> option. With 10000 events the comparison is poor, but the J/&psi; (at log10(mass)=0.5), &Upsilon; (at log10(mass=0.98)) and Z (at log10(mass)=1.95, one event only) peaks should be visible. Furthermore, since the triggers for 2010 and 2011, as well as SingleMu and DoubleMu are different, the general shape of the distributions will differ somewhat depending on input.</p> <p>To run over more or even the full statistics, edit the relevant parts of the Python file <kbd>demoanalyzer_cfg.py</kbd> (see comments therein, change max. number of events and/or insert the proper index and JSON files for 2011/2012 single/dimuon) and rerun. Add up the output histograms from different (nonoverlapping, i.e. use either DoubleMu or SingleMu, not both) input index files using Root tools\n</p><p>In addition to these instructions, which guide you through the example in detail, a github repository (<a href=\"https://github.com/cms-opendata-analyses/DimuonSpectrum2011\">https://github.com/cms-opendata-analyses/DimuonSpectrum2011</a>) based on this original code with minor modifications for direct download is available. </p> 



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
        <a href=\"/record/5501\"> this record</a> for all relevant samples to this directory
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
     <li>if not already done, follow instructions for steps 1 and 2 in <a href=\"/docs/cms-virtual-machine-2011\"> CMS 2011 Virtual Machines: How to install</a></li>\n
      <li> in the <code>Demo/DemoAnalyzer/</code> which is created in Step 2: How to test and validate, replace <code>BuildFile.xml</code> by the version downloaded from this record</li>\n
      <li> download <code>HiggsDemoAnalyzer.cc</code> from this record to the <code>/src</code> subdirectory</li>
      <li> recompile <code>scram b</code></li>\n
      <li> download <code>demoanalyzer_cfg_level3data.py</code> (data example) and
        <code>demoanalyzer_cfg_level3MC.py</code> (Higgs simulation example)</li>\n
      <li> create datasets directory <code>mkdir datasets</code> and change to this directory <code>cd datasets</code></li>\n
      <li> download <a href=\"/record/1002\">the 2012 JSON validation file</a> to this directory</li>\n
      <li>if not yet done at level 2, create the directory <code>rootfiles</code> and
        download all the level 2 root files to this directory (see level 2)</li>\n
      <li>run the two analysis jobs (one on data, one on MC, the input files
        are already predefined)</li>\n
    <ul>       
        <li><code>cmsRun demoanalyzer_cfg_level3data.py</code>
        will produce output file <code>DoubleMuParked2012C_10000_Higgs.root</code>
        containing 1 Higgs candidate from the data</li>\n
        <li><code>cmsRun demoanalyzer_cfg_level3MC.py</code>
         will produce output file <code>Higgs4L1file.root</code>
        containing the Higgs signal distributions with reduced statistics</li>
     </ul>\n
     <li> move the two .root files above to the <code>rootfiles</code> directory, together
        with the predefined files</li>\n
      <ul>     
       <li><code>mv DoubleMuParked2012C_10000_Higgs.root rootfiles/.</code></li>\n
       <li><code>mv Higgs4L1file.root rootfiles/.</code></li>
     </ul>\n
      <li> change directory <code>cd rootfiles</code> and download the macro <code>M4Lnormdatall_lvl3.cc</code> to this directory</li>\n
      <li> on the linux prompt, type <code>root -l M4Lnormdatall_lvl3.cc</code></li>\n
       <ul> 
        <li>you will get the output plot on the screen;
        the magenta Higgs signal histogram will now be the one you produced,
        and the one data event which you have selected will be shown as a blue
        triangle</li>
         </ul> \n
         <li> either, on the ROOT canvas (picture) click <code>file->Quit ROOT</code>
        or, on the root [] prompt, type <code>.q</code></li>\n
       <ul>
        <li>you will exit ROOT and find the output plot in
           mass4l_combined_user3.pdf </li>
        </ul>\n
  </ul>\n
   <li><b>Reproduce the full example analysis</b>
   (up to ~1 month or more on single CPU with fast internet connection,
    depending on internet connection speed and computer performance) </li>
<ul>
  <li>start by running level 3 and understand what you have done</li>\n
  <li> download <code>demoanalyzer_cfg_level4data.py</code> and
        <code>demoanalyzer_cfg_level4MC.py</code></li>\n
  <li>at this level, instead of running over a single file, you will run
        over so-called index files which contain chains of files</li>\n
   <li> download all the data index files for the datasets listed in
        <code>List_indexfile.txt</code> to the <code>datasets</code> directory</li>\n
   <li> download <a href=\"/record/1001\">the 2011 JSON validation file</a> to the <code>datasets</code> directory
        (in which you should already have the 2012 one)</li>\n
   <li> download all the MC index files for the MC sets listed in
        <code>List_indexfile.txt</code> to the <code>MCsets</code> directory (after having created it)</li>
   <li> edit the relevant demoanalyzer file and insert the index file you
        want; for data, make sure to use the correct JSON validation file
        in each case; set an outputfile name of your choice for each sample
        which you will recognise</li>\n
    <li> run the analysis job (<code>cmsRun demoanalyzer_cfg_level4...</code>) sequentially
        on all the input samples listed in <code>List_indexfile.txt</code>, i.e. produce
        all root output files yourself.
        If you have access to a computer farm with local support for the
        installation of the CMS software (the Open Data team can only provide
        support for the single virtual machine mode), you may also run
        the analysis in parallel on different CPUs, correspondingly speeding
        up the result.</li>\n
     <li> merge all the files from different index files of a dataset by using
        ROOT tools</li>\n
     <li> go to 2., using your own Root output files instead of the predefined
        ones</li>\n
   
  </ul>\n
</ol> 
</p>
