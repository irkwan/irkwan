<hr />
<h1>The Extended Boolean Model</h1>
<hr />
<h2>Chapter 1, An Introduction to Information Retrieval</h2>
<p>Information Retrieval is a broad term that can be summarized as &quot;taking  <strong>thing</strong>(s) that fullfill <strong>criteria</strong>(s) from <strong>collection</strong>&quot;. Even deciding which cereal box your little cousin Billy will like most for his 6th birthday party breakfast can be considered as a form of IR; however as an actual academic field of study its more formal definition is:</p>
<p>&quot;The act of <strong>finding material</strong> (usually documents) of an <strong>unstructured nature</strong> (usually text) that <strong>satisfies an information need</strong> from within <strong>large collections</strong> (usually stored on computers)&quot;</p>
<p>The most visible aplication for this field can be seen at Web Search Engine such as Bing, Yahoo, Baidu, AOL, Ask,  and Lycos. </p>
<blockquote>
<p><img src="http://1.bp.blogspot.com/-3WZ9sDYsdQs/T6Dw1jDl2cI/AAAAAAAAARg/Efimh6W5MDU/s1600/Lycos-580x321.jpg" /></p>
</blockquote>
<p>The way this sites work is fairly simple to understand yet hard to implements:</p>
<ul>
<li>The sites ask for &quot;the criteria(s)&quot; of the webpage we want in form of a <strong>Query</strong>.</li>
<li>It then proceeds to traverse &quot;the collection&quot; of webpages, and give each one &quot;<strong>relevance point</strong>&quot; on how well this webpage fullfill the given <strong>Query</strong></li>
<li>Finally, the sites display the result in form of a list of page with the most relevant page on top, descending according to <strong>relevance</strong> or likeliness to the query.</li>
</ul>
<p>Due to the unstructured nature of a webpage, it would be very difficult to process a user query on every webpages raw form. That is why IR system usually <strong>pre-process</strong> each website into a suitable model first; think of it as the website cover, it gives the system a sense of what the sites contain without needing to read the whole thing. There are all sort of model already developed for IR system, each whith its own query format, advantages, and disadvantages. One of such model which we will elaborate later is <strong>The Extended Boolean Model</strong>.</p>
<h2>Chapter 2, The Boolean Model</h2>
<p>As the name would imply, Extended Boolean Model is an <strong>Extended</strong> version of the <strong>Boolean Model</strong>. So it might be good to try to understand the basic of Boolean Model first before going ahead (of course, if you disagree, feel free to skip this chapter). Basically this particular IR model works by storing the information of a document content in form of a <strong>list</strong> containing <strong>words/terms</strong> that exist in said document. For example, consider the following picture:</p>
<p><img src="https://alaathoughts.files.wordpress.com/2012/08/vec1.jpg" /></p>
<p>The matrix above is used to store a boolean model of six documents. From there, we can clearly see what terms d1 contained. Or, more practically, we can use this matrix to get a <strong>list of documents</strong> that contain certain terms like &quot;Voyage&quot;, or &quot;Trip&quot; during certain queries. </p>
<p><br>
You might notice that there are only five terms that are listed above. Articles usually have many more words inside them, even though most of them are not really that important at reflecting the article's content, so why are there only five words listed above? This is because a concept most IR system use called <strong>Indexing</strong>.</p>
<p>Certain words like &quot;is&quot;, &quot;and&quot;, and &quot;not&quot; not important when trying to figure out what is an article about, and can be <strong>safely omited</strong> to safe <strong>space</strong> and <strong>processing time</strong>. This is called <strong>indexing</strong>. A couple of &quot;technique&quot; that can be used to achieve this are as follow:</p>
<ul>
<li>Manually supply a list of words that can be safely omited, and skip these words at creating the documents model</li>
<li>Ignore word with a fairly low, or high, use rate in a document. Statistically these words have the lowest chance to reflect the documents content, so they should be safe to be ignored. </li>
</ul>
<p><br>
On to the next topic; <strong>Query</strong> of a boolean model is expressed in form of a <strong>boolean expression</strong> (using operator AND ,OR, and NOT) about terms that's required to be present(or not) at the results. During query processing, there are only 2 posible <strong>relevance point</strong> for this model: satisfy the query and not satisfy the query. Naturally, only 
the satisfying one will be shown at the final result. </p>
<blockquote>
<p>starting from now, writer will assume that reader have basic set and boolean operation knowledge</p>
</blockquote>
<p>For example, using the picture above, query &quot;voyage AND trip&quot; would return the intersection of voyage array and trip array, resulting in array 000100, which mean that only the 4th document met that query criteria. The query ((NOT voyage) OR ocean) would return the union of ocean array and the complement of voyage array, resulting in 000000, which mean that none of the documents match the query. Simple.</p>
<p><br>
<img src="http://flylib.com/books/3/55/1/html/2/images/03fig17.gif" /></p>
<blockquote>
<p>In the implementation of the Boolean Model, it is common practice to have an <strong>indexed lists</strong> containing terms/words in the vocabullary, and on each one have a <strong>list of documents ID</strong> that contains such terms. So processing a query can be summarized as:</p>
<ol>
<li>X AND Y, return document IDs that occur in both X list and Y list</li>
<li>X OR Y, return document IDs that occur in either X list or Y list</li>
<li>NOT X, return document IDs that do not occur in X list</li>
<li>(X AND (NOT Y)) OR Z, return document IDs that occur in either Z list or IDs that occur in X list but not in Y</li>
</ol>
</blockquote>
<p><br>
And that is the basic of the standard Boolean Model, it is fairly easy to implement and understand but not without its <strong>weaknesses</strong>:</p>
<ul>
<li>
With only 2 possible relevance point, there are <strong>no way to rank documents</strong> in order of relevance. 
<ul>
<li>The model only concern itself with wether or not a term exist, not it's frequency of use and relevance in the document. </li>
<li>A user might find the term he/she wants only mentioned once in one of the query result and not that relevant in said document</li>
</ul>
</li>
<li>
There are some results which might be <strong>counterintuitive to user</strong> due to this model strict use of boolean operator.
<ul>
<li>For example the query W AND X AND Y AND Z, will not result in a document which contain the term W, X, and Y; even though the user might be interested in this document if no others fullfill this query. </li>
<li>Also, in the query A OR B OR C, a document which mention only A is considered as important as a document mentioning all  terms.</li>
</ul>
</li>
<li>There are <strong>no way to assign importance factor to parts of query</strong>, which my be desired by advanced user.</li>
</ul>
<p>Which is why <strong>several models had been proposed</strong> to improve upon this basic model, with an attempt to address the issues above...</p>
<h2>Chapter 3, The Extended Boolean Model</h2>
<p>As previously explained, the <strong>Extended Boolean Model</strong> refer to all IR model that <strong>improve upon</strong> the <strong>Standard Boolean Model</strong> in order to deal with its weakness. There had been proposed many such model, such as the <strong>MMM</strong> model, the <strong>Paice</strong> model and <strong>P-norm</strong> model. This article will mainly focus its discussion around the <strong>P-Norm</strong> model (the more feature complete from the three), and if interested, the explanation of the other model can be found here: 
<a href="http://orion.lcg.ufrj.br/Dr.Dobbs/books/book5/chap15.htm">http://orion.lcg.ufrj.br/Dr.Dobbs/books/book5/chap15.htm</a></p>
<p><br>
The concept of the P-Norm model is similar to its predecessor, but it also made some changes into it; to add more features and capability. One of the most important changes are the addition of term weights for every term appearance in a document. This concept is called <strong>term weighting</strong>, it is basically a way to measure and note how relevant is a term in a document. </p>
<p>For example, in this article, the term &quot;Query&quot; should receive a higher score than the term &quot;voyage&quot;. Even though both of them appeared, the term &quot;Query&quot; is more relevant in this document; it can be seen from the fact that the term &quot;Query&quot; is mentioned way more often than &quot;voyage&quot;. There are all sort of way to weight terms. One of them, namely the <strong>TF-IDF</strong>, take these factors into account:</p>
<ol>
<li><strong>How often</strong> is the term used in the document.</li>
<li><strong>How long</strong> is the document.</li>
<li><strong>How many</strong> other document use the same term.</li>
</ol>
<blockquote>
<p>And transform these idea into a simple yet effective term weighting formula:</p>
<ul>
<li><strong>TF(t)</strong>     = (Number of Times Term t Appears) / (Total Number of Terms)</li>
<li><strong>IDF(t)</strong>    = log_e(Total Number of Documents / Number of Documents with Term t in it)</li>
<li><strong>TF.IDF(t)</strong> = TF(t) x IDF(t)</li>
</ul>
</blockquote>
<p>With this formula (or using other method you prefer), each term appearance in a document can be given an <strong>appropriate weight</strong>. This way, the system can diferentiate between a document that mention the term &quot;voyage&quot; as an example and the one that actually contains voyage advisory content. Moreover, the P-Norm model also allows for <strong>term weighting in queries</strong> as well. This'll allow advanced user to gain more spesific documents by using a more spesific query. </p>
<p><br>
With all of these changes, of course, the <strong>query processing</strong> process must be changed as well. P-Norm had a very different query processing method compared to the Standard Boolean Model, where the model can only give a binary result, either a document fullfills the query or it didn't. </p>
<p>The P-Norm model change this into a formula that resulted in an arbitrary number, which portray the document <strong>likeliness</strong> to the query. The value of this number vary largely between system depend on the weighting method used on the document and query; but it doesn't matter since all we need to do is sort the result according to this value. A high likeliness value document should be put above a low one, this way we can <strong>rank the result</strong> according to how well it fullfill the query. The followings are the formula used in the P-Norm model:</p>
<p><img src="https://upload.wikimedia.org/math/1/8/5/1857c3ae9fa7b748b4e5a9061c1fe058.png" /></p>
<blockquote>
<p>The picture above is the formula used to calculate the similarity of the query <strong>q-and</strong> ( &quot;a-1 AND a-2 AND ... AND a-t&quot; where <strong>a-n</strong> is the <strong>nth</strong> term ) and the document <strong>d-j</strong> where the weight of term <strong>a-n</strong> is <strong>w-n</strong> (if the term doesn't exist then the weight is 0). The formula will yield the highest result when the weight of the terms desired is highest (for example w-n = 1), and will decrease as the weight of terms desired get lower.</p>
</blockquote>
<p><img src="https://upload.wikimedia.org/math/0/8/e/08eda2e93607ee59eb7b77dc60e63cf3.png" /></p>
<blockquote>
<p>The picture above is the formula used to calculate the similarity of the query <strong>q-or</strong> (&quot;a-1 OR a-2 OR ... OR a-t&quot;) and the document <strong>d-j</strong>. The formula will yield the lowest result when the weight of the terms desired is lowest (for example w-n = 0), and will increase as the weight of terms desired get higher.</p>
</blockquote>
<p><strong>SIM(q-not,dj) = 1 - SIM(q,dj)</strong></p>
<blockquote>
<p>The p used in the formulas above is called the <strong>degree of strictness</strong>, usually implemented as a system defined constant like 2. At p-value of 1, both <strong>q-or</strong> and <strong>q-and</strong> will yield the same result. </p>
<p>When t=1 (a query with only one term), both q-and and q-or provide in the same result, <strong>SIM(q,dj) = w1</strong></p>
</blockquote>
<p>With the three basic formulas above, we can easily count the similarity of more complex query; for example, The similarity formula between q = &quot;(a-1 AND a-2) OR a-3&quot; is:</p>
<p><img src="https://upload.wikimedia.org/math/0/b/1/0b113f74dd86c03eca1d317ff7a727b5.png" /></p>
<blockquote>
<p>Observe that the sub-query &quot;a1 AND a2&quot; is treated as a term weight, this concept will prove usefull during implementation</p>
</blockquote>
<p><br></p>
<blockquote>
<p>As briefly mentioned above, the P-Norm method also enable term weighting in query. This can be achieved by slightly alter the formula above to consider the query term weight. To calculate the similarity of the query <strong>q</strong> = &quot;a-1 k-1 AND/OR a-2 k-2 AND/OR ... a-n k-n&quot; (<strong>k-n</strong> is the n-th term and <strong>a-n</strong> is the weight of term k-n) and the document <strong>D</strong> where the weight of term k-n is da-n, are as such:</p>
</blockquote>
<p><img src="http://orion.lcg.ufrj.br/Dr.Dobbs/books/book5/398_a.gif" /></p>
<p>And with that, we can now easily calculate the similarities between any boolean query and a documents model. </p>
<h2>Chapter 4, Implementation</h2>
<p>Implementation of the Extended Boolean Model can be done in all sort of different way. One example is as such:</p>
<ul>
<li>
<strong>Document Model</strong> Implementation:
<ul>
<li>Rather than imitate the Standard Boolean model and have a list of terms each containing document id of all the documents that contains such term, it is better to do the opposite.</li>
<li>Because query processing will be done per-document it will make more sense to create a <strong>list of document</strong> each containing <strong>list of term</strong> ids of terms that contained within. </li>
<li>This way, we can <strong>process query sequentially</strong> down the <strong>document list</strong> and see the terms contained within and its weight relative to the document.</li>
</ul>
</li>
<li>
<strong>Query Implementation</strong>:
<ul>
<li>One the best way to implement a boolean query is to store them in form of an <strong>n-ary Tree</strong></li>
<li><strong>Each leaf is a term</strong> (and it's weight), and <strong>each internal node is the operator</strong> linking it's children together</li>
<li>For example, the query ((A OR B OR C) AND (D OR E)) will be represented as:</li>
<li><img src="http://orion.lcg.ufrj.br/Dr.Dobbs/books/book5/399_a.gif" /></li>
<li>To read the query from a tree do so by using the <strong>Inorder Tree Transversal</strong> method</li>
</ul>
</li>
<li>
<strong>Query Processing</strong>:
<ul>
<li>Query processing can be done <strong>recursively by self-call</strong> (let's just call the method Query(Node) for now)</li>
<li><strong>Basis</strong>, If the node is a <strong>leaf</strong> node, return the node weight</li>
<li>
<strong>Recurrent</strong>:
<ul>
<li>Identify which kind of query this is (AND/OR/NOT), </li>
<li>Calculate the weight of <strong>every sub-tree below</strong> this node by <strong>calling Query(Node-i)</strong></li>
<li>Return the value of this query tree by using the <strong>appropriate formula</strong></li>
</ul>
</li>
<li>
For example, using the picture above:
<ul>
<li>The process for node <strong>AND</strong> will call the Query method for both node <strong>OR</strong> </li>
<li>Each node OR will call the Query method for each of their sons, and return the similarity between its  subquery and the document</li>
<li>The method called to the AND node will return the result of using the <strong>qand</strong> formula with t=2 where <strong>w1</strong> is the result of <strong>subquery OR1</strong> and <strong>w2</strong> is the result of <strong>subquery OR2</strong>.</li>
</ul>
</li>
<li>This way, document ranking can be done sequentially down the document list by assigning similarity value to each of the document then sorting it from highest similarity to the lowest one.</li>
</ul>
</li>
</ul>
<h2>Reference</h2>
<p><a href="http://orion.lcg.ufrj.br/Dr.Dobbs/books/book5/chap15.htm" title="Extended Boolean Model by E. Fox, S. Betrabet, M. Koushik and W. Lee">Extended Boolean Model by E. Fox, S. Betrabet, M. Koushik and W. Lee</a></p>
<p><a href="http://nlp.stanford.edu/IR-book/html/htmledition/term-frequency-and-weighting-1.html" title="Term frequency and weighting from Cambridge University Press">Term frequency and weighting from Cambridge University Press</a></p>
<p><a href="http://nlp.stanford.edu/IR-book/html/htmledition/boolean-retrieval-1.html" title="Boolean retrieval from Cambridge University Press">Boolean retrieval from Cambridge University Press</a></p>
<p><a href="http://www.cs.cityu.edu.hk/~lwang/ccs4485/lecture8.ppt" title="Information Retrieval Lecture from The Department of Computer Science">Information Retrieval Lecture from The Department of Computer Science</a></p>
<p><a href="https://en.wikipedia.org/wiki/Extended_Boolean_model#Generalizing_the_idea_and_P-norms" title="Pictures from Wikipedia Extended Boolean Model Article">Pictures from Wikipedia Extended Boolean Model Article</a></p>
