# NetBeansMvnGwt2.7SDM
Set up: NetBeans + Maven + Gwt 2.7 + SDM

<h3>Run NetBeans as Administrator</h3>

<h3>Install the GWT Plugin in your Browser (Chrome for me in Windows 8)</h3>

<h3>Create New Project</h3>

<code>Maven > Web Application</code>

<code>Any Name, Any WebServer, Java EE 7 Web</code>

<ul>
<li><code>I don´t use the Gwt4nb plugin because it supports until Gwt 2.6 and it doesn't use Maven</code></li>
<li><code>For me, the stuff goes better with Maven/Web App wizard plus Gwt Framework 
instead to use directly the Gwt Maven Plugin artifact</code></li>
</ul>

<h3>Add GWT Framework</h3>

<code>Project > Properties > Frameworks > Add > Google Web Toolkit</code>

<h3>Modify POM</h3>
<code>Fisrt, very important. The version of gwt-maven-plugin must be updated to the last one. In this case, from 1.2 to 2.7.0.</code>

<code>Add dependency to gwt-dev. With provided scope.</code>

<h3>Add Action To Debug</h3>

<code>Project > Properties > Actions > Add Custom... </code>

<code> Any name. In my case: ToDebug</code>

<code> In Execute Goals >> gwt:debug</code>

<code> or gwt:debug -e -X to see full debug trace</code>

<code>Set properties >> </code>
<ul>
<li><code>runTarget=welcomeGWT.html</code></li>
<li><code>superDevMode=false     > if you want to avoid the SDM as in my case</code></li>
</ul>

<h3>Reload POM and Build the project</h3>

<h3>Run your new action</h3>
<code>Project > Custom > ToDebug</code>

<h3>Attach Debbuger to port 8000</h3>
<code>Ones gwt:debug action is running (you see this msg: Listening for transport dt_socket at address: 8000)

<code>Debug > Attach Debugger... > Select default values (port 8000) > Ok </code>

<code>Wait a moment and launch your browser from the GWT Development Mode window</code>

<code>In your browser you will see: http://127.0.0.1:8888/welcomeGWT.html?gwt.codesvr=127.0.0.1:9997 </code>

<h3>That is all</h3>
<ul>
<li><code>Add Breakpoints</code></li>
<li><code>Make changes in the code and refresh to see the magic of the Incremental Compilation</code></li>
<li><code>With System.out.println() you see the msgs in NetBeans' console</code></li>
<li><code>With GWT.logs() you see the msgs in the GWT Development Mode </code></li>
<li><strong>SuperDevMode: </strong><code>I prefer to debug in NetBeans. Change superDevMode to true in the action and in the POM file in order to active the SDM</code></li>
<li><code>Open Developer Tools in Chrome to see the SDM magic</code></li>
</ul>

<h3>Don´t forget to check POM.XML</h3>
