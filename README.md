Download Link: https://assignmentchef.com/product/solved-cpts-540-artificial-intelligence-homework-6
<br>












<strong>General Instructions</strong>: Put your answers to the following problems into a PDF document and submit as an attachment under Content  Homework 6 for the course CptS 440 Pullman (all sections of CptS 440 and 540 are merged under the CptS 440 Pullman section) on the Blackboard Learn system by the above deadline. Note that you may submit multiple times, but we will only grade the most recent entry submitted before the deadline.




<ol>

 <li>Convert the following English statements to first-order logic using the following predicates.</li>

</ol>




<ul>

 <li>Breeze(x,y): there is a breeze in location (x,y)</li>

 <li>Pit(x,y): there is a pit in location (x,y)</li>

 <li>Stench(x,y): there is a stench in location (x,y)</li>

 <li>Wumpus(x,y): the Wumpus is in location (x,y)</li>

 <li>Agent(x,y): the agent is in location (x,y)</li>

 <li>Alive(o): the object o is alive, where o {Agent,Wumpus}</li>

</ul>




<ol>

 <li>There is a pit in location (3,1).</li>

 <li>There is a breeze in the world, if and only if, there is a pit in the world.</li>

 <li>If the agent and a live Wumpus are in the same location, then the agent is not alive.</li>

 <li>There are at least two stenches in the world.</li>

 <li>There is a breeze in location (2,2) and a pit in location (2,3).</li>

</ol>




<ol start="2">

 <li>Convert the following first-order logic sentences to conjunctive normal form (CNF). There is no need to show the intermediate steps.</li>

</ol>




<ol>

 <li>Wumpus(2,3)</li>

 <li>x,y Pit(x,y)</li>

 <li>t Action(Shoot,t)  a Arrow(a,t)</li>

 <li>x,y,t<sub>1</sub>,t<sub>2</sub> Agent(x,y,t<sub>1</sub>)  Orientation(Right,t<sub>1</sub>)  Action(TurnLeft,t<sub>1</sub>)  (Agent(x,y,t<sub>2</sub>)  Orientation(Up,t<sub>2</sub>) )</li>

</ol>




<ol start="3">

 <li>Use resolution proof by refutation to prove the query below is true given the knowledge base.</li>

</ol>

Specifically,

<ol>

 <li>Convert the knowledge base and negated query to CNF. Again, no need to show intermediate steps of the conversion. Give each clause a number.</li>

 <li>Show each resolution step by indicated the two clauses being resolved (be sure to use unique variable names for each clause), the resulting clause (give it a new number),</li>

</ol>

1 and any necessary variable substitutions. Also be sure to conclude your proof with a statement of what was proven.




<strong>Knowledge Base</strong>:

<ul>

 <li>t<sub>1</sub>,t<sub>2</sub> Orientation(Right,t<sub>1</sub>)  Action(TurnLeft,t<sub>1</sub>)  Inc(t<sub>1</sub>,t<sub>2</sub>)  Orientation(Up,t<sub>2</sub>)</li>

 <li>t<sub>1</sub>,t<sub>2</sub> Alive(Agent,t<sub>1</sub>)  Action(GoForward,t<sub>1</sub>)  Inc(t<sub>1</sub>,t<sub>2</sub>)  Alive(Agent,t<sub>2</sub>)</li>

 <li>t Action(TurnLeft,t)  Action(GoForward,t)</li>

 <li>Alive(Agent,1)</li>

 <li>Orientation(Right,1)</li>

 <li>Action(TurnLeft,1)</li>

 <li>Inc(1,2)</li>

 <li>Inc(2,3)</li>

</ul>




<strong>Query</strong>: t Alive(Agent,t)  Orientation(Up,t)




<ol start="4">

 <li><em>CptS 540 Students Only</em>. Create an input file for the Vampire theorem prover that can be used to solve Problem 3. You should run Vampire using the command:</li>

</ol>




vampire –avatar off &lt;<em>input_file&gt;</em>




Include your input file and the Vampire output in the PDF document for your Homework 6 solution. You can download the Vampire theorem prover from <u>https://vprover.github.io/</u>. There is a Linux binary available there or you can compile from source on other platforms. For your reference, below is the Vampire input file for the “criminal(west)” proof demonstrated in class.




fof(a1, axiom,

! [X,Y,Z] : ((american(X) &amp; weapon(Y) &amp; sells(X,Y,Z) &amp; hostile(Z))     =&gt; criminal(X))).

fof(a2, axiom,     enemy(nono,america)).

fof(a3, axiom,

? [X] : (owns(nono,X) &amp; missle(X))). fof(a4, axiom,

! [X] : ((missle(X) &amp; owns(nono,X)) =&gt; sells(west,X,nono))). fof(a5, axiom,     american(west)).

fof(a6, axiom,

! [X] : (missle(X) =&gt; weapon(X))). fof(a7, axiom,

! [X] : (enemy(X,america) =&gt; hostile(X))).

fof(c1, conjecture, criminal(west)).




2