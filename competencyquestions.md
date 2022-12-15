---
layout: default
title: Competency Questions
---
[Questions](#competencyquestions) | [SPARQL Queries](#sparql) 

<article class="mb-5" id="competencyquestions">
  
<h2>Example of Competency Questions</h2>
  <p>We have crafted a set of competency questions to demonstrate the use of our ontology for graduate students or someone who would want to use our system for exploring various STEM Career paths. We first present a table of our competency question list and the corresponding candidate responses. We then present SPARQL query implementations for these questions. Each query is exactly the one used on Blazegraph Workbench to retrieve the demonstrated results; screenshots from the platform.</p>
  <p>In our example, we will present a set of competency questions for a STEM degree student enrolled in an American institution. A student will want to understand the different careers available after a STEM doctorate. The student progresses to select careers based on skills and interests with the appropriate skills and passion level. The student is also curious about the skills and the level of competence required for a particular profession. The student will want to know some of the initial resources that will help them understand the bigger picture of the role. With a better understanding of preferred career paths, the student now wants to know what questions to ask during the informational interview to understand how the role will fit their values. </p>
  <table>
<thead>
  <tr>
    <th>Example Competency Question</th>
    <th>Candidate Response</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td><a href="#question1">(Q1).</a>Which are the different sectors that a &lt;domain&gt; doctorate could explore career in? For example, Which sectors can STEM doctorates could explore career in?</td>
    <td>Different available sectors that a STEM doctorate can explore career paths in.</td>
  </tr>
  <tr>
    <td><a href="#question2">(Q2).</a>What are the various &lt;domain&gt; career paths available to a &lt;domain&gt; doctorate? For example, What are the various scientific career paths available to a STEM doctorate?</td>
    <td>The twenty scientific career paths that the student can explore.</td>
  </tr>
  <tr>
	  <td><a href="#question3"></a>(Q3).I consider myself as an &lt;proficiency\_level&gt; in &lt;skill&gt;. Which scientific career paths can I explore that requires this &lt;skill&gt; with my &lt;proficiency\_level&gt;? For example, Which scientific career paths require an expert proficiency level in creativity/innovative thinking?</td>
    <td>The scientific career paths in the system that requires an individual to be an expert in creativity/innovative thinking.</td>
  </tr>
  <tr>
    <td><a href="#question4">(Q4).</a>How is &lt;scientific\_career&gt; defined as? For example, What does ``Principal investigator in a research-intensive institute" mean?</td>
    <td>Career name and how is the career defined.</td>
  </tr>
  <tr>
    <td><a href="#question5">(Q5).</a>What level of proficiency is required for the required skills in &lt;scientific career path&gt;? For example, what are the various skills with proficiency levels required for ``Principal investigator in a research-intensive institute"?</td>
	  <td>Various skills with corresponding proficiency level required for pursuing the career as "Principal investigator in a research-intensive insititute". </td>
  </tr>
  <tr>
    <td><a href="#question5">(Q6).</a>What interests does &lt;scientific\_career\_path&gt; requires that may help one to succeed? For example, What are the interests that someone can possess to do well in ``Principal investigator in a research-intensive institute"?</td>
	  <td>Various interests with corresponding passion level required for pursuing the career as "Principal investigator in a research-intensive insititute". </td>
  </tr>
  <tr>
    <td><a href="#question5">(Q7).</a>Which &lt;Resource\_type&gt; could be explored to get a better understanding regarding the career path &lt;scientific\_career&gt;? For example, What are some of the articles that could help me understand ``Principal investigator in a research-intensive institute" better?</td>
	  <td>Different articles along with web links is provided that could help understand the career path better.</td>
  </tr>
  <tr>
    <td><a href="#question5">(Q8).</a>What questions to ask at an interview to understand if the role imbibes my values? For example, What are some of the values that these roles support? What questions can I ask during an informative interview to understand if the ``Principal investigator in a research-intensive institute" role could support my values?</td>
	  <td>The different values present in the system that one could consider for a role and the corresponding questions.</td>
  </tr>
  <tr>
    <td><a href="#question5">(Q9).</a>What questions can I ask to understand if the role would help me in my specific &lt;value/s&gt;? For example, What questions could I ask to understand if the ``Principal investigator in a research-intensive institute" role would support me in having a `professional development', maintain a `work-life balance' while understanding the various `benefits available'?</td>
	  <td>Questions regarding the specific values provided that teh user could ask during the informative interview to acquire more information. </td>
  </tr>
</tbody>
</table>


<h3 id="sparql">SPARQL Queries</h3>
<ol>
  <li id="question1"><strong>Which sectors can STEM doctorates could explore career in?</strong>
  <ul type = "circle">
    <li> <strong>Query:</strong> <br/>
      <pre>
prefix scivo: <http://www.semanticweb.org/nehakeshan/2022/skivo#>
prefix scivokg: <http://www.semanticweb.org/nehakeshan/2022/scivokg#>

SELECT ?SectorsToExplore
WHERE{ ?s rdfs:subClassOf scivokg:Sector.
       ?s rdfs:label ?SectorsToExplore
      }

      </pre>
	 </li>
  </ul>
  <figure>
  <img src ="../QueryResults/sectors.png" style="width:100%; height:100%">  
  <figcaption>Fig 1. Blazegraph Workbench Output for the Query 1</figcaption>  
  </figure>
  </li>  
<br><br>
  
  <li id="question2"><strong>What are the various scientific career paths available to a STEM doctorate?</strong>
  <ul type = "circle">
    <li> <strong>Query:</strong> <br/>
      <pre>
prefix scivo: <http://www.semanticweb.org/nehakeshan/2022/skivo#>
prefix scivokg: <http://www.semanticweb.org/nehakeshan/2022/scivokg#>

SELECT ?ScientificCareerPaths
WHERE{ ?s rdfs:subClassOf scivokg:Scientific_Career.
       ?s rdfs:label ?ScientificCareerPaths
     }

      </pre>
	 </li>
  </ul>
 <figure>
 <img src ="../blazegraph/SPARQL/QueryResults/scientificCareerPaths_1.png" style="width:100%; height:100%">  
 <figcaption>Fig 2. Blazegraph Workbench Output for the Query 2</figcaption> 
 </figure>
  </li>  
  <br><br>
   
  <li id="question3"><strong>Which scientific career paths require an expert proficiency level in creativity/innovative thinking?</strong>
  <ul type = "circle">
    <li> <strong>Query:</strong> <br/>
      <pre>
prefix scivo: <http://www.semanticweb.org/nehakeshan/2022/skivo#>
prefix scivokg: <http://www.semanticweb.org/nehakeshan/2022/scivokg#>

SELECT ?ScientificCareerPaths
WHERE{ ?s rdfs:subClassOf scivokg:Scientific_Career.
       ?i rdf:type ?s.
       ?s rdfs:label ?ScientificCareerPaths.
       ?i scivo:requiresSkills ?sk.
       ?sk rdf:type scivokg:Creativity_innovative_thinking.
       ?sk scivo:withProficiencyLevel scivokg:Expert
      }
      </pre>
	 </li>
  </ul>
 <figure>
 <img src ="../blazegraph/SPARQL/QueryResults/sc_definition.png" style="width:100%; height:100%">  
 <figcaption>Fig 3. Blazegraph Workbench Output for the Query 3.</figcaption> 
 </figure>
  </li>  
<br><br>
   
  <li id="question4"><strong>What does ``Principal investigator in a research-intensive institute" mean?</strong>
  <ul type = "circle">
    <li> <strong>Query:</strong> <br/>
      <pre>
SELECT ?label ?Definition
WHERE{ ?s rdfs:subClassOf scivokg:Scientific_Career.
       ?s rdfs:label ?label.
       ?s rdfs:isDefinedBy ?Definition.
     
      FILTER(?label = "Principal investigator in a research-intensive institution")
       
     }

      </pre>
	 </li>
  </ul>
 <figure>
 <img src ="../blazegraph/SPARQL/QueryResults/sc_specificSkill_profInSkill.png" style="width:100%; height:100%">  
 <figcaption>Fig 4. Blazegraph Workbench Output for the Query 4.</figcaption>
 </figure>

  </li>  
  <br><br>
    
  <li id="question5"><strong>What are the various skills with proficiency levels required for ``Principal investigator in a research-intensive institute"?</strong>
  <ul type = "circle">
    <li> <strong>Query:</strong> <br/>
      <pre>
prefix scivo: <http://www.semanticweb.org/nehakeshan/2022/skivo#>
prefix scivokg: <http://www.semanticweb.org/nehakeshan/2022/scivokg#>

SELECT ?Skill ?SkillProficiencyLevel
WHERE{ ?s rdf:type scivokg:Principal_investigator_in_a_research-intensive_institution .
       ?s scivo:requiresSkills ?o.
       ?o scivo:withProficiencyLevel ?p.
       ?p rdfs:label ?SkillProficiencyLevel.
       ?o rdf:type ?type.
       ?type rdfs:label ?Skill
      } ORDER BY ?SkillProficiencyLevel

      </pre>
	 </li>
  </ul>
 <figure>
 <img src ="../blazegraph/SPARQL/QueryResults/zoomed_skill_prof_principalInvestigator.png" style="width:100%; height:100%">  
 <figcaption>Fig 5. Blazegraph Workbench Output for the Query 5. </figcaption> 
 </figure>
  </li> 
  <br><br>
   
  <li id="question6"><strong>What are the interests that someone can possess to do well in ``Principal investigator in a research-intensive institute"?</strong>
  <ul type = "circle">
    <li> <strong>Query:</strong> <br/>
      <pre>
prefix scivo: <http://www.semanticweb.org/nehakeshan/2022/skivo#>
prefix scivokg: <http://www.semanticweb.org/nehakeshan/2022/scivokg#>

SELECT ?Interest ?InterestLevel
WHERE{ ?s rdf:type scivokg:Principal_investigator_in_a_research-intensive_institution .
       ?s scivo:requiresInterests ?o.
       ?o scivo:withInterestLevel ?p.
       ?p rdfs:label ?InterestLevel.
       ?o rdf:type ?type.
       ?type rdfs:label ?Interest
      } ORDER BY ?InterestLevel

      </pre>
	 </li>
  </ul>
 <figure>
 <img src ="../blazegraph/SPARQL/QueryResults/zoomed_Interest_level_principalInvest.png" style="width:100%; height:100%">  
 <figcaption>Fig 6. Blazegraph Workbench Output for the Query 6.</figcaption>
 </figure>

  </li>  
  <br><br> 

  <li id="question7"><strong>What are some of the articles that could help me understand ``Principal investigator in a research-intensive institute" better?</strong>
  <ul type = "circle">
    <li> <strong>Query:</strong> <br/>
      <pre>
prefix scivo: <http://www.semanticweb.org/nehakeshan/2022/skivo#>
prefix scivokg: <http://www.semanticweb.org/nehakeshan/2022/scivokg#>

SELECT ?Resources ?Link
WHERE{ ?s rdf:type scivokg:Principal_investigator_in_a_research-intensive_institution .
       ?s scivo:hasResource ?o.
       ?o rdfs:label ?Resources.
       ?o rdf:type scivokg:Articles.
       ?o scivokg:hasLink ?Link
      } ORDER BY ?Resources

      </pre>
	 </li>
  </ul>
 <figure>
 <img src ="../blazegraph/SPARQL/QueryResults/articles_principalInvestigator.png" style="width:100%; height:100%">  
 <figcaption>Fig 7. Blazegraph Workbench Output for the Query 7.</figcaption>
 </figure>

  </li>  
  <br><br>

  <li id="question8"><strong>What are some of the values that these roles support? What questions can I ask during an informative interview to understand if the ``Principal investigator in a research-intensive institute" role could support my values?</strong>
  <ul type = "circle">
    <li> <strong>Query:</strong> <br/>
      <pre>
prefix scivo: <http://www.semanticweb.org/nehakeshan/2022/skivo#>
prefix scivokg: <http://www.semanticweb.org/nehakeshan/2022/scivokg#>

SELECT ?Values ?QuestionsToConsider
WHERE{ ?s rdf:type scivo:Values.
       ?s rdfs:label ?Values.
       ?s scivokg:correspondingQuestion ?QuestionsToConsider
     }

      </pre>
	 </li>
  </ul>
 <figure>
 <img src ="../blazegraph/SPARQL/QueryResults/values1.png" style="width:100%; height:100%">  
 <figcaption>Fig 8. Blazegraph Workbench Output for the Query 8.</figcaption>
 </figure>

  </li>  
  <br><br>
  
  <li id="question9"><strong>What questions could I ask to understand if the ``Principal investigator in a research-intensive institute" role would support me in having a `professional development', maintain a `work-life balance' while understanding the various `benefits available'?</strong>
  <ul type = "circle">
    <li> <strong>Query:</strong> <br/>
      <pre>
prefix scivo: <http://www.semanticweb.org/nehakeshan/2022/skivo#>
prefix scivokg: <http://www.semanticweb.org/nehakeshan/2022/scivokg#>

SELECT ?Values ?QuestionsToConsider
WHERE{ ?s rdf:type scivo:Values.
       ?s rdfs:label ?Values.
       ?s scivokg:correspondingQuestion ?QuestionsToConsider.
      FILTER (?Values = "Benefits Available" || ?Values = "Professional Development" || ?Values = "Work_Life Balance") .
     }

      </pre>
	 </li>
  </ul>
 <figure>
 <img src ="../blazegraph/SPARQL/QueryResults/chosenValueQuestions.png" style="width:100%; height:100%">  
 <figcaption>Fig 9. Blazegraph Workbench Output for the Query 9. </figcaption>
 </figure>

  </li>  

</ol>
