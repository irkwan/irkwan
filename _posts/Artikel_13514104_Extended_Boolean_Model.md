<hr />
<h1>The Extended Boolean Model</h1>
<hr />
<h2>Chapter 1, An Introduction to Information Retrieval</h2>
<p>Starting from the basic; Information Retrieval is a broad term that can be summarized as &quot;taking  thing(s) that fullfill criteria(s) from collection&quot;. Even deciding which cereal box your little cousin Billy will like most for his 6th birthday party can be considered as a form of IR; however as an actual academic field of study its more formal definition is:</p>
<p>&quot;The act of finding material (usually documents) of an unstructured nature (usually text) that satisfies an information need from within large collections (usually stored on computers)&quot;</p>
<p>The most visible aplication for this field can be seen at Web Search Engine such as Bing, Yahoo, Baidu, AOL, Ask,  and of course.. Lycos. </p>
<p><img src="http://1.bp.blogspot.com/-3WZ9sDYsdQs/T6Dw1jDl2cI/AAAAAAAAARg/Efimh6W5MDU/s1600/Lycos-580x321.jpg" /></p>
<p>The way this sites work is fairly simple to understand yet hard to implements:</p>
<ul>
<li>The sites ask for &quot;the criteria(s)&quot; of the webpage we want in form of a Query.</li>
<li>It then proceeds to traverse &quot;the collection&quot; of webpages, and give each one &quot;relevance point&quot; on how well this webpage fullfill the Query</li>
<li>Finally, the sites display the result in form of a list of page with the most relevant page on top, descending according to relevance point.</li>
</ul>
<p>Due to the unstructured nature of a webpage, it would be very difficult to process a user query on its raw form. That is why IR usually pre-process each website into a suitable model; think of it as the website cover, it gives the system a sense of what the sites contain without needing to read the whole thing. There are all sort of model already developed for IR system, each whith its own query format, advantages, and disadvantages. One of such model is The Extended Boolean Model.</p>
<h2>Chapter 2, The Boolean Model</h2>
<p>As the name would explicitly imply, Extended Boolean Model is an Extended version of the Boolean Model. So understanding the basic of Boolean Model first before going ahead might not be a terrible idea. This particular IR model works by storing the information of a document content in form of terms/words list that exist in said document. For example, consider the following picture:</p>
<p><img src="https://alaathoughts.files.wordpress.com/2012/08/vec1.jpg" /></p>
<p>The matrix above is used to store a boolean model of six documents. From there, we can clearly see what terms d1 contained. Or, more practically, we can use this matrix to get a list of documents that contain certain terms like &quot;Voyage&quot;, or &quot;Trip&quot; during certain queries. </p>
<p>You might notice that there are only five terms that are listed above, which is weird because there are not that many 5 word article; this is strongly implied by the fact the query &quot;5 word article&quot; gave an empty result on Lycos. This is mainly because the picture above is just an example, but since you're already reading this pointless paragraph we can now smoothly transition over to the next topic. Indexing.</p>
<p>As the paragraph above proved, not all parts of a documents should be viewed as a reflection of its content. Certain words like &quot;is&quot;, &quot;and&quot;, and &quot;not&quot; not really important when trying to figure out what is an article about, and can be safely omited to safe space and processing time. Some &quot;technique&quot; that can be used to achieve this are as follow:</p>
<ul>
<li>Manually supply a list of words that can be safely omited</li>
<li>Ignore word with a fairly low, or high, use rate in a document</li>
</ul>
<p>Next topic; Query of a boolean model is expressed in form of a boolean expression (using operator AND ,OR, and NOT) about terms that's required to be present(or not) at the results. During query processing, there are only 2 posible relevance point for this model: satisfy the query and not satisfy the query. Naturally, only the satisfying one will be shown at the final result. </p>
<p>*<em>starting from now, the writer will assume that reader have basic set and boolean operation knowledge.</em></p>
<p>For example, using the picture above, the query &quot;voyage AND trip&quot; would return the intersection of voyage array and trip array, resulting in 000100, which mean that only the 4th document met that query criteria. The query ((NOT voyage) OR ocean) would return the union of ocean array and the complement of voyage array, resulting in 000000, which mean that none of the documents match the query. Simple.</p>
