# Word-Embedding-w2vec-glove-fastext

Vector Semantics
Similar to language models, embeddings are trained directly from a large
collection of natural language text without being tied to a specific NLP
application or subtask. How can we measure the quality of learned
embeddings? Some of the commonly accepted extrinsic evaluation methods are
based on word similarity tasks, word analogies (e.g., “man is to woman as king is
to queen) In this part of the assignment, we will explore an analogy task.
The analogy prediction task is defined as follows. Given a pair of words
<a, b> and a third word c,
choose a fourth-word d
so that the analogy <a is to b> as <c is to d> holds.
NOTE: the system need not characterize this relationship or give it a name! The
relationship is taken to be implicit in the pair <a, b>
Mikolov et al. [2] proposed that simple algebraic operations could be applied to
embeddings to find an analogy prediction.
[2] Mikolov, T., Sutskever, I., Chen, K., Corrado, G. S., & Dean, J. (2013).
Distributed representations of words and phrases and their compositionality.
In Advances in neural information processing systems (pp. 3111-3119).
Let va be the vector for a, vb the vector for b, and so on. For the d such that the
analogy holds, we expect
(1)
We therefore seek
(2)
Analogy Dataset Mikolov’s analogy dataset [2] includes four semantic relations
and four syntactic relations. In the test files, each line represents one analogy
question, in the form of four words <a, b, c, d>.
For example: “Bangkok Thailand Cairo Egypt”
A question is counted as correctly answered only if the predicted word is the
same as the given word. For example, given the first three words “Bangkok
Thailand Cairo”, the task is to predict “Egypt”.
The full set of analogy questions can be found in the file word-test.v1.txt.
Available here: http://www.fit.vutbr.cz/~imikolov/rnnlm/word-test.v1.txt
The groups of relations are delimited by lines starting with a colon (:) and you
should only work with these groups: capital-world, currency, city-in-state, family,
gram1-adjective-to-adverb, gram2-opposite, gram3-comparative, and gram6-
nationality-adjective.
Word Embeddings “Pretrained” word embeddings are word embeddings that
are already constructed in advance of your NLP project (whether your project is
a neural language model, a text classifier, or a class assignment). The advantage
of pretraining is that it simplifies learning your model, because the embedding
parameters are fixed in advance. The disadvantage is that, if your embeddings
happen to be bad for your task, you’re stuck with them. For this part of the
assignment, you are free to use any pretrained word embeddings you can find,
as long as you cite their papers in the writeup.
Here are some popular choices:
• Word2vec: https://code.google.com/archive/p/word2vec/
• GloVe: http://nlp.stanford.edu/projects/glove/
• Dependency-based. embeddings:
https://levyomer.wordpress.com/2014/04/25/dependency-based-wordembeddings/
