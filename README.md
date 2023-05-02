Download Link: https://assignmentchef.com/product/solved-cpsc-331-hw3-code-solved
<br>
This assignment consists of two parts. The first part consists of problems that will give you more practice working with binary trees. The second part consists of a coding exercise that explores the use of trees in parsing and evaluating arithmetic expressions.

<h1>Part I</h1>

<ol>

 <li>(5 points)</li>

</ol>

Prove the following:

<ul>

 <li>A <em>binary </em>tree with <em>n </em>nodes has <em>n </em>+ 1 null</li>

 <li>In a non-empty binary tree, the number of full nodes plus one is equal to the number of leaves. (A <em>full node </em>is a node that has two children.)</li>

</ul>

<ol start="2">

 <li>(5 points)</li>

</ol>

Design a linear time algorithm to test whether a binary tree is a binary search tree. Provide pseudocode for your algorithm and justify that your algorithm is linear in the number of nodes.

<ol start="3">

 <li>(5 points)</li>

</ol>

Analyze the worst case and best case running times of inserting <em>n </em>elements into an initially empty binary search tree. For each case, provide details of your analysis starting from counting relevant operations to an accurate asymptotic characterization.

<h1>Part II</h1>

Write a parser that parses an arithmetic expression given in infix notation into a binary expression tree. Your parser should support infix expressions consisting of binary operators {‘+’, ‘-’, ‘*’, ‘/’ }, numbers (in integer format), as well as parentheses (which may be nested). Once an expression has been parsed into an expression tree, your program will additionally be able to perform preorder and postorder traversals on the tree, and evaluate the expression.

You can perform the parsing either using a stack (worth 15 points) or via recursive descent (worth 15 points + 5 bonus) using an expression grammar for infix expressions. Both strategies will be discussed in class and tutorials.

<h2>Stack-based Parsing (15 points)</h2>

Please review Section 4.2.2 in Weiss which presents a stack-based algorithm for parsing parenthesesfree expressions given in postfix notation. Note that you will first need to apply Dijkstra’s shunting yard algorithm to convert the given infix expression to postfix.

<ul>

 <li>You may use the Stack class from the Java Collections Framework.</li>

 <li>Implementation of Dijkstra’s shunting yard algorithm and the subsequent stack-based parsing algorithm must be your own. You are also <em>required </em>to use the provided ExpressionTree and ExpressionTreeNode classes (see below).</li>

 <li>Your implementation should check for errors and throw an exception if there are any syntax problems in the input expression.</li>

</ul>

<h2>Recursive Descent (15 + 5 points)</h2>

An expression grammar for infix expressions is given below.

E –&gt; T { ( “+” | “-” ) T }

T –&gt; F { ( “*” | “/” ) F }

F –&gt; num | “(” E “)”

This grammar generates expressions consisting of the binary operators +, -, * and / as well as parenthetical expressions.

<strong>Notation: </strong>In the above grammar, braces {} are used to indicate productions that may repeat 0 or more times, | separate alternatives, while parentheses () are used for grouping. The only terminal symbol is a num. <em>For this assignment, you can assume that </em>num∈Z.

Note that * and / have higher precedence compared to + and -. Operators with the same precedence are associated left-to-right (left-associativity), e.g. the expression “2 – 3 + 4” yields the following tree.


2 3

Before proceeding with your implementation, please make sure you understand the rules of the grammar and know how to apply them for parsing via recursive descent.

<h2>Implementation</h2>

Write a Java class called ExpressionTree that parses expressions either using a stack or by recursive descent. In either case, your class should have the following public methods.

public class ExpressionTree { private ExpTreeNode root = null;

// Builds empty tree public ExpressionTree() {

}

// Parse an expression from a string

public void parse( String line ) throws ParseException {

}

// Evaluate an expression public int evaluate() {

return 0;

}

// Return a postfix version of the expression public String postfix() {

return “”;

}

// Return a prefix version of the expression public String prefix() {

return “”;

}

}

A skeleton of this class as well as the class ExpTreeNode are available on D2L.

<h3>Additional Requirements</h3>

Include as many private methods as necessary to parse a given expression. You can assume that properly formatted input expressions will have tokens separated by whitespace. However, you should check for expressions that have syntax issues. If an input expression contains a syntax error, the parse method should throw a ParseException. In the thrown exception, include a description of the nature of the error as well as the location of the error in the input string.

When converting expressions to prefix or postfix, please separate tokens using whitespace. Prefix and postfix expressions should be parentheses free.

<h3>Documentation and Testing</h3>

For all private methods that you add, please provide Javadoc comments to explain what the methods are doing.

Write a program to test your parser. Test with both small size expressions as well as expressions with mixed operators, nested parentheses etc. A test program that is compatible with your implementation will be made available closer to the due date.


