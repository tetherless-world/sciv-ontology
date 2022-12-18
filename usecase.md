---
layout: default
title: Use cases
---

[Science myIDP](#myidp) | [NSF SED 2019](#nsf)  

<article class="mb-5" id="Use Case">
<content>
  
  
<h2 id="myidp"> Science Individual Development Plan tool - myIDP </h2>
 <p> We demonstrate the use of SCIVO by designing and ingesting Science Individual Development Plan tool - myIDP data (henceforth refered to as myIDP). The individual development plan, a method to help students in choosing their future employment, was proposed by the Federation of American Societies for Experimental Biology (FASEB) for postdoctoral fellows in sciences. AAAS/Science, with the help of FASEB and other experts, expanded on this framework to create myIDP for doctoral students in science. Anyone can create a free account and take different tests to get the percentage skill and interest match with the twenty scientific careers (<a href="#fig2">Figure. 2</a>) that graduate students typically pursue. The match is done with expert average ratings from one to five for the various skills and interests each of these career path require. </p>
 
<img src="../images/myIDP_snippet.png" style="width:100%; height:100%"/>  
 <caption id="fig2">Figure 2. A snippet of myIDP frame. (a) The image depicts the screenshot of how the pop up looks after the test is taken. Each cell under skills, interests and values column opens a new pop up window. Image (b), (c) and (d) are parts of the screenshots demonstrating the interests match, skill match and values to consider for career path 'Principal Investigator at a research intensive institute'.</caption>

 <br>

 <p>We assume that this information could be beneficial for graduate student to explore scientific career paths from the known twenty career paths provided on myIDP. <a href="#fig3">Figure. 3</a> represents an overview of how SCIVO has been extended to incorporate the required classes for myIDP data. As a proof of concept, we have integrated one-thousand seven-hundred and forty data points from myIDP as below by extending and intantiating the SCIVO classes.
    <ul>
		<li> Twenty Scientific Career Paths available for Science, Technology, Engineering, and Math (STEM) doctorates with their definitions. </li>
		<li> Broad and fine skills possessed by one </li>
        <li> Interests that one may have </li>
		<li> The proficiency and passion levels of skills and interests required for the twenty scientific career paths as based on the experts avaerage scores.</li>
	</ul>
</p>

 
<img src="../images/myIDP_scivo1.png" style="width:100%; height:100%"/>  
<caption id="fig3">Figure 3. A conceptual diagram representing a part of SCIVOKG created by extending the SCIVO ontology for the myIDP use case. Light blue boxes represent classes added for the knowledge graph as subclasses of SCIVO.</caption>
  <br>

<h3 id="careerpath">Mapping myIDP Scietific Career Path to "scivo:CareerPath"</h3>

The myIDP is built for scientific careers, hence, the scivokg:ScientificCareer class is added as a subclass of scivo:CareerPath, to which all twenty proposed careers are added as subclasses (<a href="#fig3">Figure. 3</a>).

<h3 id="skills">Mapping myIDP Skills to "scivo:Skills"</h3>

<p>The myIDP skills are added hierarchically. Five broad skills become subclasses of "scivo:Skills" (<a href="#fig3">Figure. 3</a>). The finer skill-sets then become the subclass of these broad skillsets.</p>

<h3 id="proficiency">Mapping myIDP skills proficiency to "scivo:Proficiency"</h3>

<p>In myIDP, participants must rate each skill on a scale of one to five. The comparison is based on the expert's average score for each skill relative to  the participant's score. However, in reality, students are required to provide their skill proficiency levels. Therefore, for compatibility with many existing systems we mapped the myIDP five pointer to a four pointer skill levels (<a href="#fig3">Figure. 3</a>), as shown in <a href="#tab1">Table 1</a>.</p>

<table id="tab1">
<thead>
  <tr>
    <th>myIDP Scores</th>
    <th>Proficiency Levels</th>
	<th>Passion Levels</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>0-2</td>
    <td>Beginner</td>
	<td>Low</td>
  </tr>
  <tr>
    <td>2.1-3</td>
    <td>Intermediate</td>
	<td>Medium</td>
  </tr>
  <tr>
    <td>3.1-4</td>
    <td>Proficient</td>
	<td>High</td>
  </tr>
  <tr>
    <td>4.1-5</td>
    <td>Expert</td>
	<td>Very High</td>
  </tr>
</tbody>
</table>

<h3 id="resources">Mapping myIDP Resources to "scivo:Resources"</h3>

<p> The myIDP consists of various resources for students to learn more about a particular career. These resources include books/chapters, articles, and professional societies. These three become subclasses of "scivo:Resources" (<a href="#fig3">Figure. 3</a>) and a particular resource becomes an individual of the corresponding resource type. </p>
<p>We might end up having one resource that provides information for more than one career path. This could have been an issue if the system was not built using semantics. With the power of semantics we can now simply add these connections in a cleaner way during the creation of our knowledge graph. </p>


<h3 id="interests">Mapping myIDP Interests to "scivo:Interests"</h3>

All the thirty-five plus interests discussed in myIDP become direct subclasses of ``scivo:Interests" (<a href="#fig3">Figure. 3</a>). 


<h3 id="passion">Mapping myIDP Interests level to "scivo:Passion"</h3>

<p>Similar to the skill level, each participant is required to rate their interest level on a scale of one to five. This is then used to compare with the average expert values as a factor to calculate the percentage of career paths matching. We use the ``scivo:Passion" class to connect the interest level with the passion level using the <a href="#tab1">Table 1</a>.</p>


<h3 id="values">Mapping myIDP Values to "scivo:Values"</h3>

<p>The myIDP supports our argument that one should select a career based on one's skills, interests, and values. They provide more than thirty-five common values that PhDs look at while finding jobs. Since these values are  very personal,  they provide one example question  that could be asked during an interview to find out if the role matches their personal values. Each value becomes an individual of the "scivo:Values" (<a href="#fig3">Figure. 3</a>) having a data property of "correspondingQuestion". </p>


<br>
<h2 id="nsf"> NSF Doctoral Recipients Survey 2019 in Machine Readable form </h2>

 We demonstrated how two heterogeneous resource can be harmonized using SCIVO to help students get a better picture towards making an informed decision by adding sectors from NSF 2019 Doctoral Survey Recipients data (<a href="#fig4">Figure. 4</a>). 


<img src="../images/nsf_scivo.png" style="width:100%; height:100%"/>  
  <caption id="fig4">Figure 4. A conceptual diagram depicting the classes of our Skills to Career with Interests and Values Ontology.</caption>


</content>