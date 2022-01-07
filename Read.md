<div class="application-main " data-commit-hovercards-enabled="" data-discussion-hovercards-enabled="" data-issue-and-pr-hovercards-enabled="">
<div class="container-lg px-3 new-discussion-timeline">
<div class="repository-content gist-content">
<div class="js-gist-file-update-container js-task-list-container file-box">
<div id="file-kotlin-interview-questions-md" class="file my-2">
<div id="file-kotlin-interview-questions-md-readme" class="Box-body readme blob js-code-block-container p-5 p-xl-6 gist-border-0">
<article class="markdown-body entry-content container-lg">
<h2 dir="auto">Kotlin</h2>
<h3 dir="auto"><a id="user-content-q1-what-is-a-primary-constructor-in-kotlin-" class="anchor" href="https://gist.github.com/paulfranco/4453383cc6df064d03087ce7aa5a0c8c#q1-what-is-a-primary-constructor-in-kotlin-"></a>Q1: What is a primary constructor in Kotlin? ☆☆</h3>
<p dir="auto"><strong>Answer:</strong>&nbsp;The&nbsp;<strong>primary constructor</strong>&nbsp;is part of the class header. Unlike Java, you don't need to declare a constructor in the body of the class. Here's an example:</p>
<div class="highlight highlight-source-kotlin">
<pre><span class="pl-k">class</span> <span class="pl-en">Person</span>(<span class="pl-k">val</span> <span class="pl-smi">firstName</span><span class="pl-k">:</span> <span class="pl-c1">String</span>, <span class="pl-k">var</span> <span class="pl-smi">age</span><span class="pl-k">:</span> <span class="pl-c1">Int</span>) {
    <span class="pl-c"><span class="pl-c">//</span> class body</span>
}</pre>
</div>
<p dir="auto">The main idea is by removing the constructor keyword, our code gets simplified and easy to understand.</p>
<p dir="auto"><strong>Source:</strong>&nbsp;<em><a href="http://www.programiz.com/" rel="nofollow">www.programiz.com</a></em></p>
<h3 dir="auto"><a id="user-content-q2-what-is-a-data-class-in-kotlin-" class="anchor" href="https://gist.github.com/paulfranco/4453383cc6df064d03087ce7aa5a0c8c#q2-what-is-a-data-class-in-kotlin-"></a>Q2: What is a data class in Kotlin? ☆☆</h3>
<p dir="auto"><strong>Answer:</strong>&nbsp;We frequently create classes whose main purpose is to hold data. In Kotlin, this is called a data class and is marked as&nbsp;<code>data</code>:</p>
<div class="highlight highlight-source-kotlin">
<pre><span class="pl-k">data class</span> <span class="pl-en">User</span>(<span class="pl-k">val</span> <span class="pl-smi">name</span><span class="pl-k">:</span> <span class="pl-c1">String</span>, <span class="pl-k">val</span> <span class="pl-smi">age</span><span class="pl-k">:</span> <span class="pl-c1">Int</span>)</pre>
</div>
<p dir="auto">To ensure consistency and meaningful behavior of the generated code, data classes have to fulfill the following requirements:</p>
<ul dir="auto">
<li>The primary constructor needs to have at least one parameter;</li>
<li>All primary constructor parameters need to be marked as val or var;</li>
<li>Data classes cannot be abstract, open, sealed or inner;</li>
</ul>
<p dir="auto"><strong>Source:</strong>&nbsp;<em>kotlinlang.org</em></p>
<h3 dir="auto"><a id="user-content-q3-explain-the-null-safety-in-kotlin-" class="anchor" href="https://gist.github.com/paulfranco/4453383cc6df064d03087ce7aa5a0c8c#q3-explain-the-null-safety-in-kotlin-"></a>Q3: Explain the Null safety in Kotlin ☆☆☆</h3>
<p dir="auto"><strong>Answer:</strong>&nbsp;Kotlin's type system is aimed at eliminating the danger of null references from code, also known as the The Billion Dollar Mistake.</p>
<p dir="auto">One of the most common pitfalls in many programming languages, including Java, is that accessing a member of a null reference will result in a null reference exception. In Java this would be the equivalent of a&nbsp;<code>NullPointerException</code>&nbsp;or NPE for short.</p>
<p dir="auto">In Kotlin, the type system distinguishes between references that can hold&nbsp;<code>null</code>&nbsp;(nullable references) and those that can not (<code>non-null</code>&nbsp;references). For example, a regular variable of type String can not hold null:</p>
<div class="highlight highlight-source-kotlin">
<pre><span class="pl-k">var</span> a<span class="pl-k">:</span> <span class="pl-c1">String</span> <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">"</span>abc<span class="pl-pds">"</span></span>
a <span class="pl-k">=</span> <span class="pl-c1">null</span> <span class="pl-c"><span class="pl-c">//</span> compilation error</span></pre>
</div>
<p dir="auto">To allow nulls, we can declare a variable as nullable string, written&nbsp;<code>String?</code>:</p>
<div class="highlight highlight-source-kotlin">
<pre><span class="pl-k">var</span> b<span class="pl-k">:</span> <span class="pl-c1">String?</span> <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">"</span>abc<span class="pl-pds">"</span></span>
b <span class="pl-k">=</span> <span class="pl-c1">null</span> <span class="pl-c"><span class="pl-c">//</span> ok</span>
<span class="pl-c1">print</span>(b)</pre>
</div>
<p dir="auto"><strong>Source:</strong>&nbsp;<em>kotlinlang.org</em></p>
<h3 dir="auto"><a id="user-content-q4-how-are-extensions-resolved-in-kotlin-and-what-doest-it-mean-" class="anchor" href="https://gist.github.com/paulfranco/4453383cc6df064d03087ce7aa5a0c8c#q4-how-are-extensions-resolved-in-kotlin-and-what-doest-it-mean-"></a>Q4: How are extensions resolved in Kotlin and what doest it mean? ☆☆☆</h3>
<p dir="auto"><strong>Answer:</strong>&nbsp;Extensions do not actually modify classes they extend. By defining an extension, you do not insert new members into a class, but merely make new functions callable with the dot-notation on variables of this type.</p>
<p dir="auto">The extension functions dispatched&nbsp;<strong>statically</strong>. That means the extension function which will be called is determined by the type of the expression on which the function is invoked, not by the type of the result of evaluating that expression at runtime. In short, they are not virtual by receiver type.</p>
<p dir="auto">Consider:</p>
<div class="highlight highlight-source-kotlin">
<pre><span class="pl-k">open</span> <span class="pl-k">class</span> <span class="pl-en">BaseClass</span>

<span class="pl-k">class</span> <span class="pl-en">DerivedClass</span> : <span class="pl-en">BaseClass</span>()

<span class="pl-k">fun</span> BaseClass.<span class="pl-en">someMethod</span>(){
    <span class="pl-c1">print</span>(<span class="pl-s"><span class="pl-pds">"</span>BaseClass.someMethod<span class="pl-pds">"</span></span>)
}

<span class="pl-k">fun</span> DerivedClass.<span class="pl-en">someMethod</span>(){
    <span class="pl-c1">print</span>(<span class="pl-s"><span class="pl-pds">"</span>DerivedClass.someMethod<span class="pl-pds">"</span></span>)
}

<span class="pl-k">fun</span> <span class="pl-en">printMessage</span>(<span class="pl-smi">base</span> <span class="pl-k">:</span> <span class="pl-en">BaseClass</span>){
    base.someMethod()
}

printMessage(<span class="pl-en">DerivedClass</span>())</pre>
</div>
<p dir="auto">This will print</p>
<div class="highlight highlight-source-shell">
<pre>BaseClass.someMethod</pre>
</div>
<p dir="auto">because the extension function being called depends only on the declared type of the parameter&nbsp;<code>base</code>&nbsp;in&nbsp;<code>printMessage</code>&nbsp;method, which is the&nbsp;<code>BaseClass</code>&nbsp;class. This is different from runtime polymorphism as here it is resolved&nbsp;<strong>statically</strong>&nbsp;but not at the runtime.</p>
<p dir="auto"><strong>Source:</strong>&nbsp;<em>medium.com</em></p>
<h3 dir="auto"><a id="user-content-q5-what-is-a-purpose-of-companion-objects-in-kotlin-" class="anchor" href="https://gist.github.com/paulfranco/4453383cc6df064d03087ce7aa5a0c8c#q5-what-is-a-purpose-of-companion-objects-in-kotlin-"></a>Q5: What is a purpose of Companion Objects in Kotlin? ☆☆☆</h3>
<p dir="auto"><strong>Answer:</strong>&nbsp;Unlike Java or C#, Kotlin doesn&rsquo;t have&nbsp;<code>static</code>&nbsp;members or member functions. If you need to write a function that can be called without having a class instance but needs access to the internals of a class, you can write it as a member of a&nbsp;<strong>companion object</strong>&nbsp;declaration inside that class.</p>
<div class="highlight highlight-source-kotlin">
<pre><span class="pl-k">class</span> <span class="pl-en">EventManager</span> {

    <span class="pl-k">companion</span> <span class="pl-k">object</span> <span class="pl-en">FirebaseManager</span> {
    }  
}

<span class="pl-k">val</span> firebaseManager <span class="pl-k">=</span> <span class="pl-en">EventManager</span>.<span class="pl-en">FirebaseManager</span></pre>
</div>
<p dir="auto">The companion object is a singleton. The companion object is a&nbsp;<strong>proper object</strong>&nbsp;on its own, and can have its own supertypes - and you can assign it to a variable and pass it around. If you're integrating with Java code and need a true static member, you can annotate a member inside a companion object with&nbsp;<code>@JvmStatic</code>.</p>
<p dir="auto"><strong>Source:</strong>&nbsp;<em>kotlinlang.org</em></p>
<h3 dir="auto"><a id="user-content-q6-what-is-lateinit-in-kotlin-and-when-would-you-use-it-" class="anchor" href="https://gist.github.com/paulfranco/4453383cc6df064d03087ce7aa5a0c8c#q6-what-is-lateinit-in-kotlin-and-when-would-you-use-it-"></a>Q6: What is Lateinit in Kotlin and when would you use it? ☆☆☆</h3>
<p dir="auto"><strong>Answer:</strong>&nbsp;<strong>lateinit</strong>&nbsp;means&nbsp;<em>late initialization</em>. If you do not want to initialize a variable in the constructor instead you want to initialize it later on and if you can guarantee the initialization before using it, then declare that variable with lateinit keyword. It will not allocate memory until initialized. You cannot use lateinit for primitive type properties like Int, Long etc.</p>
<div class="highlight highlight-source-kotlin">
<pre><span class="pl-k">lateinit</span> <span class="pl-k">var</span> test<span class="pl-k">:</span> <span class="pl-c1">String</span>

<span class="pl-k">fun</span> <span class="pl-en">doSomething</span>() {
    test <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">"</span>Some value<span class="pl-pds">"</span></span>
    <span class="pl-c1">println</span>(<span class="pl-s"><span class="pl-pds">"</span>Length of string is <span class="pl-pds">"</span></span><span class="pl-k">+</span>test.length)
    test <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">"</span>change value<span class="pl-pds">"</span></span>
}</pre>
</div>
<p dir="auto">There are a handful of use cases where this is extremely helpful, for example:</p>
<ul dir="auto">
<li>Android: variables that get initialized in lifecycle methods;</li>
<li>Using Dagger for DI: injected class variables are initialized outside and independently from the constructor;</li>
<li>Setup for unit tests: test environment variables are initialized in a&nbsp;<code>@Before</code>&nbsp;- annotated method;</li>
<li>Spring Boot annotations (eg.&nbsp;<code>@Autowired</code>).</li>
</ul>
<p dir="auto"><strong>Source:</strong>&nbsp;<em>medium.com</em></p>
<h3 dir="auto"><a id="user-content-q7-explain-lazy-initialization-in-kotlin-" class="anchor" href="https://gist.github.com/paulfranco/4453383cc6df064d03087ce7aa5a0c8c#q7-explain-lazy-initialization-in-kotlin-"></a>Q7: Explain lazy initialization in Kotlin ☆☆☆</h3>
<p dir="auto"><strong>Answer:</strong>&nbsp;<strong>lazy</strong>&nbsp;means lazy initialization. Your variable will not be initialized unless you use that variable in your code. It will be initialized only once after that we always use the same value.</p>
<p dir="auto"><code>lazy()</code>&nbsp;is a function that takes a lambda and returns an instance of lazy which can serve as a delegate for implementing a lazy property: the first call to&nbsp;<code>get()</code>&nbsp;executes the lambda passed to&nbsp;<code>lazy()</code>&nbsp;and remembers the result, subsequent calls to&nbsp;<code>get()&nbsp;</code>simply return the remembered result.</p>
<div class="highlight highlight-source-kotlin">
<pre><span class="pl-k">val</span> test<span class="pl-k">:</span> <span class="pl-c1">String</span> by lazy {
    <span class="pl-k">val</span> testString <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">"</span>some value<span class="pl-pds">"</span></span>
}</pre>
</div>
<p dir="auto"><strong>Source:</strong>&nbsp;<em>blog.mindorks.com</em></p>
<h3 dir="auto"><a id="user-content-q8-when-to-use-lateinit-over-lazy-initialization-in-kotlin-" class="anchor" href="https://gist.github.com/paulfranco/4453383cc6df064d03087ce7aa5a0c8c#q8-when-to-use-lateinit-over-lazy-initialization-in-kotlin-"></a>Q8: When to use lateinit over lazy initialization in Kotlin? ☆☆☆</h3>
<p dir="auto"><strong>Answer:</strong></p>
<p dir="auto">There are some simple rules to determined if you should use one or the other for properties initialisation:</p>
<ul dir="auto">
<li>If properties are mutable (i.e. might change at a later stage) use&nbsp;<strong>lateInit</strong></li>
<li>If properties are set externally (e.g. need to pass in some external variable to set it), use&nbsp;<strong>lateinit</strong>. There&rsquo;s still workaround to use lazy but not as direct.</li>
<li>If they are only meant to initialized once and shared by all, and it&rsquo;s more internally set (dependent on variable internal to the class), then use&nbsp;<strong>lazy</strong>. Tactically, you could still use lateinit, but using** lazy** would better encapsulate your initialization code.</li>
</ul>
<p dir="auto">Also compare:</p>
<table>
<thead>
<tr>
<th>&nbsp;</th>
<th>&nbsp;</th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>lateinit</strong>&nbsp;var</td>
<td>by&nbsp;<strong>lazy</strong></td>
</tr>
<tr>
<td>Can be initialized from anywhere the object seen from.</td>
<td>Can only be initialized from the initializer lambda.</td>
</tr>
<tr>
<td>Multiple initialization possible.</td>
<td>Only initialize single time.</td>
</tr>
<tr>
<td>Non-thread safe. It&rsquo;s up to user to initialize correctly in a multi-threaded environment.</td>
<td>Thread-safety by default and guarntees that the initializer is invoked by once.</td>
</tr>
<tr>
<td>Can only be used for var.</td>
<td>Can only be used for val.</td>
</tr>
<tr>
<td>Not eligible for nonnull properties.</td>
<td>Not eligible for nonnull properties.</td>
</tr>
<tr>
<td>An isInitialized method added to check whether the value has been initialized before.</td>
<td>Property never able to un-initialized.</td>
</tr>
<tr>
<td>Not allowed on properties of primitive types.</td>
<td>Allowed on properties of primitive types.</td>
</tr>
</tbody>
</table>
<p dir="auto"><strong>Source:</strong>&nbsp;<em>ahsensaeed.com</em></p>
<h3 dir="auto"><a id="user-content-q9-may-you-briefly-compare-kotlin-vs-java-" class="anchor" href="https://gist.github.com/paulfranco/4453383cc6df064d03087ce7aa5a0c8c#q9-may-you-briefly-compare-kotlin-vs-java-"></a>Q9: May you briefly compare Kotlin vs Java? ☆☆☆</h3>
<p dir="auto"><strong>Answer:</strong></p>
<table>
<thead>
<tr>
<th>&nbsp;</th>
<th>&nbsp;</th>
<th>&nbsp;</th>
</tr>
</thead>
<tbody>
<tr>
<td>Java vs Kotlin</td>
<td>Java</td>
<td>Kotlin</td>
</tr>
<tr>
<td>Null Safe</td>
<td>In Java,&nbsp;<code>NullPointerExceptions</code>&nbsp;causes huge frustration for developers. It allows users to assign null to any variables but while accessing an object reference having null value raises a null pointer exception which user needs to handle.</td>
<td>In Kotlin, By default, all types of variables are non-null able (i.e. we can&rsquo;t assign null values to any type of variables/objects). If we try to assign or return null values, Kotlin code will fail during compile-time. If we really want a variable to have a null value, we can declare as follows:&nbsp;<code>value num: Int? = null</code></td>
</tr>
<tr>
<td>Extension Functions</td>
<td>In Java, If we want to extend the functionality of existing class we need to create a new class and inherit the parent class. So Extension functions are not available in Java</td>
<td>Kotlin provides developers the ability to extend an existing class with new functionality. We can create extend functions by prefixing the name of a class to name of the new function.</td>
</tr>
<tr>
<td>Coroutines&nbsp;Support</td>
<td>In Java, whenever if we initiate a long-running network I/0 or CPU Intensive operations, the corresponding thread will be blocked. As Android is a single-threaded by default. Java provides the ability to create multiple threads in the background and run but managing them is a complex task.</td>
<td>In Kotlin, We can create multiple threads to run these long-running intensive operations but we have coroutines support, which will suspend execution at a certain point without blocking threads while executing long-running intensive operations.</td>
</tr>
<tr>
<td>No checked exceptions</td>
<td>In Java, We have checked exceptions support which makes developers declare and catch the exception which ultimately leads to robust code with good error handling.</td>
<td>In Kotlin, we don&rsquo;t have checked exceptions. So developers don&rsquo;t need to declare or catch the exceptions, which have advantages and disadvantages.</td>
</tr>
<tr>
<td>Data classes</td>
<td>In Java, suppose we need to have a class which needs to hold data but nothing else. For this we need to define constructors, variables to store data, getter and setter methods, hashcode(), toString(), and equals() functions</td>
<td>In Kotlin, If we need to have classes which need to hold data we can declare a class with keyword &ldquo;data&rdquo; in the class definition then the compiler will take care of all of this work such as creating constructors, getter, setter methods for different fields.</td>
</tr>
<tr>
<td>Smart casts</td>
<td>In Java, We need to check the type of variables and cast according to our operation.</td>
<td>In Kotlin, smart casts will handle these casting checks with keyword &ldquo;is-checks&rdquo; which will check for immutable values and performs implicit casting.</td>
</tr>
<tr>
<td>Type inference</td>
<td>In Java, we need to specify a type of each variable explicitly while declaring.</td>
<td>In Kotlin, we don&rsquo;t need to specify the type of each variable explicitly based on assignment it will handle. If we want to specify explicitly we can do.</td>
</tr>
<tr>
<td>Functional Programming</td>
<td>Java doesn&rsquo;t have functional programming support till Java 8 but while developing Android applications it supports the only subset of Java 8 features.</td>
<td>Kotlin is a mix of procedural and functional programming language which consists of many useful methods such as lambda, operator overloading, higher-order functions, and lazy evaluation, etc.</td>
</tr>
</tbody>
</table>
<p dir="auto"><strong>Source:</strong>&nbsp;<em><a href="http://www.educba.com/" rel="nofollow">www.educba.com</a></em></p>
<h3 dir="auto"><a id="user-content-q10-what-are-coroutines-in-kotlin-" class="anchor" href="https://gist.github.com/paulfranco/4453383cc6df064d03087ce7aa5a0c8c#q10-what-are-coroutines-in-kotlin-"></a>Q10: What are coroutines in Kotlin? ☆☆☆</h3>
<p dir="auto"><strong>Answer:</strong>&nbsp;Unlike many other languages with similar capabilities, async and await are not keywords in Kotlin and are not even part of its standard library.</p>
<p dir="auto"><code>kotlinx.coroutines</code>&nbsp;is a rich library for coroutines developed by JetBrains. It contains a number of high-level coroutine-enabled primitives, including&nbsp;<code>launch</code>,&nbsp;<code>async</code>&nbsp;and others. Kotlin Coroutines give you an API to write your asynchronous code sequentially.</p>
<p dir="auto">The documentation says Kotlin Coroutines are like lightweight threads. They are lightweight because creating coroutines doesn&rsquo;t allocate new threads. Instead, they use predefined thread pools, and smart scheduling. Scheduling is the process of determining which piece of work you will execute next.</p>
<p dir="auto">Additionally, coroutines can be&nbsp;<strong>suspended</strong>&nbsp;and&nbsp;<strong>resumed</strong>&nbsp;mid-execution. This means you can have a long-running task, which you can execute little-by-little. You can pause it any number of times, and resume it when you&rsquo;re ready again.</p>
<p dir="auto"><strong>Source:</strong>&nbsp;<em><a href="http://www.raywenderlich.com/" rel="nofollow">www.raywenderlich.com</a></em></p>
<h3 dir="auto"><a id="user-content-q11-how-to-initialize-an-array-in-kotlin-with-values-" class="anchor" href="https://gist.github.com/paulfranco/4453383cc6df064d03087ce7aa5a0c8c#q11-how-to-initialize-an-array-in-kotlin-with-values-"></a>Q11: How to initialize an array in Kotlin with values? ☆☆</h3>
<p dir="auto"><strong>Details:</strong>&nbsp;In Java an array can be initialized such as:</p>
<div class="highlight highlight-source-java">
<pre> <span class="pl-k">int</span> numbers[] <span class="pl-k">=</span> <span class="pl-k">new</span> <span class="pl-smi">int</span>[] {<span class="pl-c1">10</span>, <span class="pl-c1">20</span>, <span class="pl-c1">30</span>, <span class="pl-c1">40</span>, <span class="pl-c1">50</span>}</pre>
</div>
<p dir="auto">How does Kotlin's array initialization look like?</p>
<p dir="auto"><strong>Answer:</strong></p>
<div class="highlight highlight-source-kotlin">
<pre><span class="pl-k">val</span> numbers<span class="pl-k">:</span> <span class="pl-c1">IntArray</span> <span class="pl-k">=</span> intArrayOf(<span class="pl-c1">10</span>, <span class="pl-c1">20</span>, <span class="pl-c1">30</span>, <span class="pl-c1">40</span>, <span class="pl-c1">50</span>)</pre>
</div>
<p dir="auto"><strong>Source:</strong>&nbsp;<em>stackoverflow.com</em></p>
<h3 dir="auto"><a id="user-content-q12-what-is-the-difference-between-var-and-val-in-kotlin-" class="anchor" href="https://gist.github.com/paulfranco/4453383cc6df064d03087ce7aa5a0c8c#q12-what-is-the-difference-between-var-and-val-in-kotlin-"></a>Q12: What is the difference between var and val in Kotlin? ☆☆</h3>
<p dir="auto"><strong>Answer:</strong></p>
<ul dir="auto">
<li>
<p dir="auto"><strong>var</strong>&nbsp;is like&nbsp;<code>general</code>&nbsp;variable and it's known as a&nbsp;<em>mutable</em>&nbsp;variable in kotlin and can be assigned multiple times.</p>
</li>
<li>
<p dir="auto"><strong>val</strong>&nbsp;is like&nbsp;<code>Final</code>&nbsp;variable and it's known as&nbsp;<em>immutable</em>&nbsp;in Kotlin and can be initialized only single time.</p>
</li>
</ul>
<div class="highlight highlight-source-shell">
<pre>+----------------+-----------------------------+---------------------------+
<span class="pl-k">|</span>                <span class="pl-k">|</span>             val             <span class="pl-k">|</span>            var            <span class="pl-k">|</span>
+----------------+-----------------------------+---------------------------+
<span class="pl-k">|</span> Reference <span class="pl-c1">type</span> <span class="pl-k">|</span> Immutable(once initialized  <span class="pl-k">|</span> Mutable(can able to change<span class="pl-k">|</span>
<span class="pl-k">|</span>                <span class="pl-k">|</span> can<span class="pl-s"><span class="pl-pds">'</span>t be reassigned)        | value)                    |</span>
<span class="pl-s">+----------------+-----------------------------+---------------------------+</span>
<span class="pl-s">| Example        | val n = 20                  | var n = 20                |</span>
<span class="pl-s">+----------------+-----------------------------+---------------------------+</span>
<span class="pl-s">| In Java        | final int n = 20;           | int n = 20;               |</span>
<span class="pl-s">+----------------+-----------------------------+---------------------------+</span></pre>
</div>
<p dir="auto"><strong>Source:</strong>&nbsp;<em>stackoverflow.com</em></p>
<h3 dir="auto"><a id="user-content-q13-how-to-correctly-concatenate-a-string-in-kotlin-" class="anchor" href="https://gist.github.com/paulfranco/4453383cc6df064d03087ce7aa5a0c8c#q13-how-to-correctly-concatenate-a-string-in-kotlin-"></a>Q13: How to correctly concatenate a String in Kotlin? ☆☆</h3>
<p dir="auto"><strong>Answer:</strong>&nbsp;In Kotlin, you can concatenate</p>
<ol dir="auto">
<li>using string interpolation / templates</li>
</ol>
<div class="highlight highlight-source-kotlin">
<pre><span class="pl-k">val</span> a <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">"</span>Hello<span class="pl-pds">"</span></span>
<span class="pl-k">val</span> b <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">"</span>World<span class="pl-pds">"</span></span>
<span class="pl-k">val</span> c <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">"</span><span class="pl-e">$a</span> <span class="pl-e">$b</span><span class="pl-pds">"</span></span></pre>
</div>
<ol dir="auto" start="2">
<li>using the + /&nbsp;<code>plus()</code>&nbsp;operator</li>
</ol>
<div class="highlight highlight-source-kotlin">
<pre><span class="pl-k">val</span> a <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">"</span>Hello<span class="pl-pds">"</span></span>
<span class="pl-k">val</span> b <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">"</span>World<span class="pl-pds">"</span></span> 
<span class="pl-k">val</span> c <span class="pl-k">=</span> a <span class="pl-k">+</span> b   <span class="pl-c"><span class="pl-c">//</span> same as calling operator function a.plus(b)</span>
<span class="pl-k">val</span> c <span class="pl-k">=</span> a.plus(b)

<span class="pl-c1">print</span>(c)</pre>
</div>
<ol dir="auto" start="3">
<li>using the&nbsp;<code>StringBuilder</code></li>
</ol>
<div class="highlight highlight-source-kotlin">
<pre><span class="pl-k">val</span> a <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">"</span>Hello<span class="pl-pds">"</span></span>
<span class="pl-k">val</span> b <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">"</span>World<span class="pl-pds">"</span></span>

<span class="pl-k">val</span> sb <span class="pl-k">=</span> <span class="pl-en">StringBuilder</span>()
sb.append(a).append(b)
<span class="pl-k">val</span> c <span class="pl-k">=</span> sb.toString()

<span class="pl-c1">print</span>(c)</pre>
</div>
<p dir="auto"><strong>Source:</strong>&nbsp;<em>stackoverflow.com</em></p>
<h3 dir="auto"><a id="user-content-q14-what-is-basic-difference-between-fold-and-reduce-in-kotlin-when-to-use-which-" class="anchor" href="https://gist.github.com/paulfranco/4453383cc6df064d03087ce7aa5a0c8c#q14-what-is-basic-difference-between-fold-and-reduce-in-kotlin-when-to-use-which-"></a>Q14: What is basic difference between fold and reduce in Kotlin? When to use which? ☆☆</h3>
<p dir="auto"><strong>Answer:</strong></p>
<ul dir="auto">
<li><code>fold</code>&nbsp;takes an initial value, and the first invocation of the lambda you pass to it will receive that initial value and the first element of the collection as parameters.</li>
</ul>
<div class="highlight highlight-source-kotlin">
<pre><span class="pl-c1">listOf</span>(<span class="pl-c1">1</span>, <span class="pl-c1">2</span>, <span class="pl-c1">3</span>).fold(<span class="pl-c1">0</span>) { sum, element <span class="pl-k">-&gt;</span> sum <span class="pl-k">+</span> element }</pre>
</div>
<p dir="auto">The first call to the lambda will be with parameters&nbsp;<code>0</code>&nbsp;and&nbsp;<code>1</code>.</p>
<p dir="auto">Having the ability to pass in an initial value is useful&nbsp;<em>if you have to provide some sort of default value or parameter for your operation</em>.</p>
<ul dir="auto">
<li><code>reduce</code>&nbsp;doesn't take an initial value, but instead starts with the first element of the collection as the accumulator (called&nbsp;<code>sum</code>&nbsp;in the following example)</li>
</ul>
<div class="highlight highlight-source-kotlin">
<pre><span class="pl-c1">listOf</span>(<span class="pl-c1">1</span>, <span class="pl-c1">2</span>, <span class="pl-c1">3</span>).reduce { sum, element <span class="pl-k">-&gt;</span> sum <span class="pl-k">+</span> element }</pre>
</div>
<p dir="auto">The first call to the lambda here will be with parameters&nbsp;<code>1</code>&nbsp;and&nbsp;<code>2</code>.</p>
<p dir="auto"><strong>Source:</strong>&nbsp;<em>stackoverflow.com</em></p>
<h3 dir="auto"><a id="user-content-q15-what-is-the-idiomatic-way-to-remove-duplicate-strings-from-array-" class="anchor" href="https://gist.github.com/paulfranco/4453383cc6df064d03087ce7aa5a0c8c#q15-what-is-the-idiomatic-way-to-remove-duplicate-strings-from-array-"></a>Q15: What is the idiomatic way to remove duplicate strings from array? ☆☆</h3>
<p dir="auto"><strong>Details:</strong>&nbsp;How to remove duplicates from an&nbsp;<code>Array&lt;String?&gt;</code>&nbsp;in Kotlin?</p>
<p dir="auto"><strong>Answer:</strong>&nbsp;Use the&nbsp;<code>distinct</code>&nbsp;extension function:</p>
<div class="highlight highlight-source-kotlin">
<pre><span class="pl-k">val</span> a <span class="pl-k">=</span> arrayOf(<span class="pl-s"><span class="pl-pds">"</span>a<span class="pl-pds">"</span></span>, <span class="pl-s"><span class="pl-pds">"</span>a<span class="pl-pds">"</span></span>, <span class="pl-s"><span class="pl-pds">"</span>b<span class="pl-pds">"</span></span>, <span class="pl-s"><span class="pl-pds">"</span>c<span class="pl-pds">"</span></span>, <span class="pl-s"><span class="pl-pds">"</span>c<span class="pl-pds">"</span></span>)
<span class="pl-k">val</span> b <span class="pl-k">=</span> a.distinct() <span class="pl-c"><span class="pl-c">//</span> ["a", "b", "c"]</span></pre>
</div>
<p dir="auto">You can also use:</p>
<ul dir="auto">
<li><code>toSet</code>,&nbsp;<code>toMutableSet</code></li>
<li><code>toHashSet</code>&nbsp;- if you don't need the original ordering to be preserved</li>
</ul>
<p dir="auto">These functions produce a&nbsp;<code>Set</code>&nbsp;instead of a&nbsp;<code>List</code>&nbsp;and should be a little bit more efficient than distinct.</p>
<p dir="auto"><strong>Source:</strong>&nbsp;<em>stackoverflow.com</em></p>
<h3 dir="auto"><a id="user-content-q16-how-to-create-singleton-in-kotlin-" class="anchor" href="https://gist.github.com/paulfranco/4453383cc6df064d03087ce7aa5a0c8c#q16-how-to-create-singleton-in-kotlin-"></a>Q16: How to create singleton in Kotlin? ☆☆</h3>
<p dir="auto"><strong>Answer:</strong>&nbsp;Just use&nbsp;<code>object</code>.</p>
<div class="highlight highlight-source-kotlin">
<pre><span class="pl-k">object</span> <span class="pl-en">SomeSingleton</span></pre>
</div>
<p dir="auto">The above Kotlin object will be compiled to the following equivalent Java code:</p>
<div class="highlight highlight-source-java">
<pre><span class="pl-k">public</span> <span class="pl-k">final</span> <span class="pl-k">class</span> <span class="pl-en">SomeSingleton</span> {
   <span class="pl-k">public</span> <span class="pl-k">static</span> <span class="pl-k">final</span> <span class="pl-smi">SomeSingleton</span> <span class="pl-c1">INSTANCE</span>;

   <span class="pl-k">private</span> <span class="pl-en">SomeSingleton</span>() {
      <span class="pl-c1">INSTANCE</span> <span class="pl-k">=</span> (<span class="pl-smi">SomeSingleton</span>)<span class="pl-c1">this</span>;
      <span class="pl-smi">System</span><span class="pl-k">.</span>out<span class="pl-k">.</span>println(<span class="pl-s"><span class="pl-pds">"</span>init complete<span class="pl-pds">"</span></span>);
   }

   <span class="pl-k">static</span> {
      <span class="pl-k">new</span> <span class="pl-smi">SomeSingleton</span>();
   }
}</pre>
</div>
<p dir="auto">This is the preferred way to implement singletons on a JVM because it enables thread-safe lazy initialization without having to rely on a locking algorithm like the complex double-checked locking.</p>
<p dir="auto"><strong>Source:</strong>&nbsp;<em>medium.com</em></p>
<h3 dir="auto"><a id="user-content-q17-where-should-i-use-var-and-where-val-" class="anchor" href="https://gist.github.com/paulfranco/4453383cc6df064d03087ce7aa5a0c8c#q17-where-should-i-use-var-and-where-val-"></a>Q17: Where should I use var and where val? ☆☆</h3>
<p dir="auto"><strong>Answer:</strong>&nbsp;Use&nbsp;<strong>var</strong>&nbsp;where value is changing&nbsp;<em>frequently</em>. For example while getting location of android device:</p>
<div class="highlight highlight-source-kotlin">
<pre><span class="pl-k">var</span> integerVariable <span class="pl-k">:</span> <span class="pl-c1">Int?</span> <span class="pl-k">=</span> <span class="pl-c1">null</span></pre>
</div>
<p dir="auto">Use&nbsp;<strong>val</strong>&nbsp;where there is&nbsp;<em>no change</em>&nbsp;in value in whole class. For example you want set textview or button's text programmatically.</p>
<div class="highlight highlight-source-kotlin">
<pre><span class="pl-k">val</span> stringVariables <span class="pl-k">:</span> <span class="pl-c1">String</span> <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">"</span>Button's Constant or final Text<span class="pl-pds">"</span></span></pre>
</div>
<p dir="auto"><strong>Source:</strong>&nbsp;<em>stackoverflow.com</em></p>
<h3 dir="auto"><a id="user-content-q18-explain-what-is-wrong-with-that-code-" class="anchor" href="https://gist.github.com/paulfranco/4453383cc6df064d03087ce7aa5a0c8c#q18-explain-what-is-wrong-with-that-code-"></a>Q18: Explain what is wrong with that code? ☆☆☆</h3>
<p dir="auto"><strong>Details:</strong>&nbsp;Why is this code wrong?</p>
<div class="highlight highlight-source-kotlin">
<pre><span class="pl-k">class</span> <span class="pl-en">Student</span> (<span class="pl-k">var</span> <span class="pl-smi">name</span><span class="pl-k">:</span> <span class="pl-c1">String</span>) {
    <span class="pl-en">init</span>() {
        <span class="pl-c1">println</span>(<span class="pl-s"><span class="pl-pds">"</span>Student has got a name as <span class="pl-e">$name</span><span class="pl-pds">"</span></span>)
    }

    <span class="pl-en">constructor</span>(sectionName<span class="pl-k">:</span> <span class="pl-c1">String</span>, <span class="pl-k">var</span> id<span class="pl-k">:</span> <span class="pl-c1">Int</span>) <span class="pl-c1">this</span>(sectionName) {
    }
}</pre>
</div>
<p dir="auto"><strong>Answer:</strong>&nbsp;The property of the class can&rsquo;t be declared inside the secondary constructor.. This will give an error because here we are declaring a property&nbsp;<code>id</code>&nbsp;of the class in the secondary constructor, which is not allowed.</p>
<p dir="auto">If you want to use some property inside the secondary constructor, then declare the property inside the class and use it in the&nbsp;<strong>secondary constructor</strong>:</p>
<div class="highlight highlight-source-kotlin">
<pre><span class="pl-k">class</span> <span class="pl-en">Student</span> (<span class="pl-k">var</span> <span class="pl-smi">name</span><span class="pl-k">:</span> <span class="pl-c1">String</span>) {

    <span class="pl-k">var</span> id<span class="pl-k">:</span> <span class="pl-c1">Int</span> <span class="pl-k">=</span> <span class="pl-k">-</span><span class="pl-c1">1</span>
    <span class="pl-en">init</span>() {
        <span class="pl-c1">println</span>(<span class="pl-s"><span class="pl-pds">"</span>Student has got a name as <span class="pl-e">$name</span><span class="pl-pds">"</span></span>)
    }
    
    <span class="pl-en">constructor</span>(secname<span class="pl-k">:</span> <span class="pl-c1">String</span>, id<span class="pl-k">:</span> <span class="pl-c1">Int</span>) <span class="pl-c1">this</span>(secname) {
        <span class="pl-c1">this</span>.id <span class="pl-k">=</span> id
    }
}</pre>
</div>
<p dir="auto"><strong>Source:</strong>&nbsp;<em><a href="http://www.programiz.com/" rel="nofollow">www.programiz.com</a></em></p>
<h3 dir="auto"><a id="user-content-q19-what-will-be-result-of-the-following-code-execution-" class="anchor" href="https://gist.github.com/paulfranco/4453383cc6df064d03087ce7aa5a0c8c#q19-what-will-be-result-of-the-following-code-execution-"></a>Q19: What will be result of the following code execution? ☆☆☆</h3>
<p dir="auto"><strong>Details:</strong>&nbsp;What will be the output?</p>
<div class="highlight highlight-source-kotlin">
<pre><span class="pl-k">val</span> aVar by lazy {
    <span class="pl-c1">println</span>(<span class="pl-s"><span class="pl-pds">"</span>I am computing this value<span class="pl-pds">"</span></span>)
    <span class="pl-s"><span class="pl-pds">"</span>Hola<span class="pl-pds">"</span></span>
}
<span class="pl-k">fun</span> <span class="pl-en">main</span>(<span class="pl-smi">args</span><span class="pl-k">:</span> <span class="pl-c1">Array</span>&lt;<span class="pl-en">String</span>&gt;) {
    <span class="pl-c1">println</span>(aVar)
    <span class="pl-c1">println</span>(aVar)
}</pre>
</div>
<p dir="auto"><strong>Answer:</strong>&nbsp;For&nbsp;<code>lazy</code>&nbsp;the first time you access the Lazy property, the initialisation (<code>lazy()</code>&nbsp;function invocation) takes place. The second time, this value is remembered and returned:</p>
<div class="highlight highlight-source-shell">
<pre>I am computing this value
Hola
Hola</pre>
</div>
<p dir="auto"><strong>Source:</strong>&nbsp;<em>dzone.com</em></p>
<h3 dir="auto"><a id="user-content-q20-what-is-the-difference-between-suspending-vs-blocking-" class="anchor" href="https://gist.github.com/paulfranco/4453383cc6df064d03087ce7aa5a0c8c#q20-what-is-the-difference-between-suspending-vs-blocking-"></a>Q20: What is the difference between suspending vs. blocking? ☆☆☆</h3>
<p dir="auto"><strong>Answer:</strong></p>
<ul dir="auto">
<li>
<p dir="auto">A&nbsp;<strong>blocking</strong>&nbsp;call to a function means that a call to any other function, from the same thread, will halt the parent&rsquo;s execution. Following up, this means that if you make a blocking call on the main thread&rsquo;s execution, you effectively freeze the UI. Until that blocking calls finishes, the user will see a static screen, which is not a good thing.</p>
</li>
<li>
<p dir="auto"><strong>Suspending</strong>&nbsp;doesn&rsquo;t necessarily block your parent function&rsquo;s execution. If you call a suspending function in some thread, you can easily push that function to a different thread. In case it is a heavy operation, it won&rsquo;t block the main thread. If the suspending function has to suspend, it will simply pause its execution. This way you free up its thread for other work. Once it&rsquo;s done suspending, it will get the next free thread from the pool, to finish its work.</p>
</li>
</ul>
<p dir="auto"><strong>Source:</strong>&nbsp;<em><a href="http://www.raywenderlich.com/" rel="nofollow">www.raywenderlich.com</a></em></p>
<h3 dir="auto"><a id="user-content-q1-what-is-the-equivalent-of-java-static-methods-in-kotlin-" class="anchor" href="https://gist.github.com/paulfranco/4453383cc6df064d03087ce7aa5a0c8c#q1-what-is-the-equivalent-of-java-static-methods-in-kotlin-"></a>Q1: What is the equivalent of Java static methods in Kotlin? ☆☆☆</h3>
<p dir="auto"><strong>Answer:</strong>&nbsp;Place the function in the&nbsp;<strong>companion object</strong>.</p>
<div class="highlight highlight-source-java">
<pre><span class="pl-k">class</span> <span class="pl-en">Foo</span> {
  <span class="pl-k">public</span> <span class="pl-k">static</span> <span class="pl-k">int</span> <span class="pl-en">a</span>() { <span class="pl-k">return</span> <span class="pl-c1">1</span>; }
}</pre>
</div>
<p dir="auto">will become:</p>
<div class="highlight highlight-source-kotlin">
<pre><span class="pl-k">class</span> <span class="pl-en">Foo</span> {
  <span class="pl-k">companion</span> <span class="pl-k">object</span> {
     <span class="pl-k">fun</span> <span class="pl-en">a</span>() : <span class="pl-c1">Int</span> <span class="pl-k">=</span> <span class="pl-c1">1</span>
  }
}

<span class="pl-c"><span class="pl-c">//</span> to run</span>
<span class="pl-en">Foo</span>.a();</pre>
</div>
<p dir="auto">Another way is to solve most of the needs for static functions with package-level functions. They are simply declared outside a class in a source code file. The package of a file can be specified at the beginning of a file with the package keyword. Under the hood these "top-level" or "package" functions are actually compiled into their own class. In the above example, the compiler would create a class FooPackage with all of the top-level properties and functions, and route all of your references to them appropriately.</p>
<p dir="auto">Consider:</p>
<div class="highlight highlight-source-kotlin">
<pre><span class="pl-k">package</span> <span class="pl-en">foo</span>

<span class="pl-k">fun</span> <span class="pl-en">bar</span>() <span class="pl-k">=</span> {}</pre>
</div>
<p dir="auto">usage:</p>
<div class="highlight highlight-source-kotlin">
<pre><span class="pl-k">import</span> <span class="pl-smi">foo.bar</span></pre>
</div>
<p dir="auto"><strong>Source:</strong>&nbsp;<em>stackoverflow.com</em></p>
<h3 dir="auto"><a id="user-content-q2-what-is-suspending-function-in-kotlin-" class="anchor" href="https://gist.github.com/paulfranco/4453383cc6df064d03087ce7aa5a0c8c#q2-what-is-suspending-function-in-kotlin-"></a>Q2: What is suspending function in Kotlin? ☆☆☆</h3>
<p dir="auto"><strong>Answer:</strong>&nbsp;A&nbsp;<strong>suspending function</strong>&nbsp;is just a regular Kotlin function with an additional suspend modifier which indicates that the function can suspend the execution of a coroutine without blocking the current thread. This means that the code you are looking at might stop executing at the moment it calls a suspending function, and will resume at some later time. However, it doesn&rsquo;t say anything about what the current thread will do in the meantime.</p>
<p dir="auto">Suspending functions can invoke any other regular functions, but to actually suspend the execution, it has to be another suspending function.A suspending function cannot be invoked from a regular function, therefore several so-called coroutine builders are provided, which allow calling a suspending function from a regular non-suspending scope like&nbsp;<code>launch</code>,&nbsp;<code>async</code>,&nbsp;<code>runBlocking</code>.</p>
<p dir="auto"><strong>Source:</strong>&nbsp;<em>proandroiddev.com</em></p>
<h3 dir="auto"><a id="user-content-q3-explain-advantages-of-when-vs-switch-in-kotlin-" class="anchor" href="https://gist.github.com/paulfranco/4453383cc6df064d03087ce7aa5a0c8c#q3-explain-advantages-of-when-vs-switch-in-kotlin-"></a>Q3: Explain advantages of "when" vs "switch" in Kotlin ☆☆☆</h3>
<p dir="auto"><strong>Answer:</strong></p>
<p dir="auto">In Java we use switch but in Kotlin, that switch gets converted to&nbsp;<strong>when</strong>. When has a better design. It is more concise and powerful than a traditional&nbsp;<strong>switch</strong>.&nbsp;<strong>when</strong>&nbsp;can be used either as an expression or as a statement.</p>
<p dir="auto">Some examples of&nbsp;<strong>when</strong>&nbsp;usage:</p>
<ul dir="auto">
<li>Two or more choices</li>
</ul>
<div class="highlight highlight-source-kotlin">
<pre><span class="pl-k">when</span>(number) {
    <span class="pl-c1">1</span> <span class="pl-k">-&gt;</span> <span class="pl-c1">println</span>(<span class="pl-s"><span class="pl-pds">"</span>One<span class="pl-pds">"</span></span>)
    <span class="pl-c1">2</span>, <span class="pl-c1">3</span> <span class="pl-k">-&gt;</span> <span class="pl-c1">println</span>(<span class="pl-s"><span class="pl-pds">"</span>Two or Three<span class="pl-pds">"</span></span>)
    <span class="pl-c1">4</span> <span class="pl-k">-&gt;</span> <span class="pl-c1">println</span>(<span class="pl-s"><span class="pl-pds">"</span>Four<span class="pl-pds">"</span></span>)
    <span class="pl-k">else</span> <span class="pl-k">-&gt;</span> <span class="pl-c1">println</span>(<span class="pl-s"><span class="pl-pds">"</span>Number is not between 1 and 4<span class="pl-pds">"</span></span>)
}</pre>
</div>
<ul dir="auto">
<li>"when" without arguments</li>
</ul>
<div class="highlight highlight-source-kotlin">
<pre><span class="pl-k">when</span> {
    number <span class="pl-k">&lt;</span> <span class="pl-c1">1</span> <span class="pl-k">-&gt;</span> <span class="pl-c1">print</span>(<span class="pl-s"><span class="pl-pds">"</span>Number is less than 1<span class="pl-pds">"</span></span>)
    number <span class="pl-k">&gt;</span> <span class="pl-c1">1</span> <span class="pl-k">-&gt;</span> <span class="pl-c1">print</span>(<span class="pl-s"><span class="pl-pds">"</span>Number is greater than 1<span class="pl-pds">"</span></span>)
}</pre>
</div>
<ul dir="auto">
<li>Any type passed in "when"</li>
</ul>
<div class="highlight highlight-source-kotlin">
<pre><span class="pl-k">fun</span> <span class="pl-en">describe</span>(<span class="pl-smi">obj</span><span class="pl-k">:</span> <span class="pl-c1">Any</span>): <span class="pl-c1">String</span> <span class="pl-k">=</span>
    <span class="pl-k">when</span> (obj) {
      <span class="pl-c1">1</span> <span class="pl-k">-&gt;</span> <span class="pl-s"><span class="pl-pds">"</span>One<span class="pl-pds">"</span></span>
      <span class="pl-s"><span class="pl-pds">"</span>Hello<span class="pl-pds">"</span></span> <span class="pl-k">-&gt;</span> <span class="pl-s"><span class="pl-pds">"</span>Greeting<span class="pl-pds">"</span></span>
      <span class="pl-k">is</span> <span class="pl-c1">Long</span> <span class="pl-k">-&gt;</span> <span class="pl-s"><span class="pl-pds">"</span>Long<span class="pl-pds">"</span></span>
      <span class="pl-k">!is</span> <span class="pl-c1">String</span> <span class="pl-k">-&gt;</span> <span class="pl-s"><span class="pl-pds">"</span>Not a string<span class="pl-pds">"</span></span>
      <span class="pl-k">else</span> <span class="pl-k">-&gt;</span> <span class="pl-s"><span class="pl-pds">"</span>Unknown<span class="pl-pds">"</span></span>
    }</pre>
</div>
<ul dir="auto">
<li>Smart casting</li>
</ul>
<div class="highlight highlight-source-kotlin">
<pre><span class="pl-k">when</span> (x) {
    <span class="pl-k">is</span> <span class="pl-c1">Int</span> <span class="pl-k">-&gt;</span> <span class="pl-c1">print</span>(<span class="pl-s"><span class="pl-pds">"</span>X is integer<span class="pl-pds">"</span></span>)
    <span class="pl-k">is</span> <span class="pl-c1">String</span> <span class="pl-k">-&gt;</span> <span class="pl-c1">print</span>(<span class="pl-s"><span class="pl-pds">"</span>X is string<span class="pl-pds">"</span></span>)
}</pre>
</div>
<ul dir="auto">
<li>Ranges</li>
</ul>
<div class="highlight highlight-source-kotlin">
<pre><span class="pl-k">when</span>(number) {
    <span class="pl-c1">1</span> <span class="pl-k">-&gt;</span> <span class="pl-c1">println</span>(<span class="pl-s"><span class="pl-pds">"</span>One<span class="pl-pds">"</span></span>) <span class="pl-c"><span class="pl-c">//</span>statement 1</span>
    <span class="pl-c1">2</span> <span class="pl-k">-&gt;</span> <span class="pl-c1">println</span>(<span class="pl-s"><span class="pl-pds">"</span>Two<span class="pl-pds">"</span></span>) <span class="pl-c"><span class="pl-c">//</span>statement 2</span>
    <span class="pl-c1">3</span> <span class="pl-k">-&gt;</span> <span class="pl-c1">println</span>(<span class="pl-s"><span class="pl-pds">"</span>Three<span class="pl-pds">"</span></span>) <span class="pl-c"><span class="pl-c">//</span>statement 3</span>
    <span class="pl-k">in</span> <span class="pl-c1">4</span><span class="pl-k">..</span><span class="pl-c1">8</span> <span class="pl-k">-&gt;</span> <span class="pl-c1">println</span>(<span class="pl-s"><span class="pl-pds">"</span>Number between 4 and 8<span class="pl-pds">"</span></span>) <span class="pl-c"><span class="pl-c">//</span>statement 4</span>
    <span class="pl-k">!in</span> <span class="pl-c1">9</span><span class="pl-k">..</span><span class="pl-c1">12</span> <span class="pl-k">-&gt;</span> <span class="pl-c1">println</span>(<span class="pl-s"><span class="pl-pds">"</span>Number not in between 9 and 12<span class="pl-pds">"</span></span>) <span class="pl-c"><span class="pl-c">//</span>statement 5</span>
    <span class="pl-k">else</span> <span class="pl-k">-&gt;</span> <span class="pl-c1">println</span>(<span class="pl-s"><span class="pl-pds">"</span>Number is not between 1 and 8<span class="pl-pds">"</span></span>) <span class="pl-c"><span class="pl-c">//</span>statement 6</span>
}</pre>
</div>
<p dir="auto"><strong>Source:</strong>&nbsp;<em>blog.mindorks.com</em></p>
<h3 dir="auto"><a id="user-content-q4-what-are-the-advantages-of-kotlin-over-java-" class="anchor" href="https://gist.github.com/paulfranco/4453383cc6df064d03087ce7aa5a0c8c#q4-what-are-the-advantages-of-kotlin-over-java-"></a>Q4: What are the advantages of Kotlin over Java? ☆☆☆</h3>
<p dir="auto"><strong>Answer:</strong>&nbsp;Basically for me less thinking required to write kotlin equivalent to most java code:</p>
<p dir="auto"><code>data class</code></p>
<ul dir="auto">
<li>java: you have to write getters and setters for each thing, you have to write&nbsp;<code>hashCode</code>&nbsp;properly (or let IDE auto generate, which you have to do again every time you change the class),&nbsp;<code>toString</code>&nbsp;(same problem as&nbsp;<code>hashcode</code>) and&nbsp;<code>equals</code>&nbsp;(same problem as&nbsp;<code>hashCode</code>). or you could use lombok, but that comes with some quirky problems of its own.&nbsp;<code>record</code>&nbsp;types are hopefully on the way. *kotlin:&nbsp;<code>data class</code>&nbsp;does it all for you.</li>
</ul>
<p dir="auto">getter and setter patterns</p>
<ul dir="auto">
<li>
<p dir="auto">java: rewrite the getter and setter for each variable you use it for</p>
</li>
<li>
<p dir="auto">kotlin: don't have to write getter and setter, and custom getter and setter take a lot less typing in kotlin if you do want to. also delegates exist for identical getters\setters</p>
</li>
</ul>
<p dir="auto"><code>abstract</code>&nbsp;vs&nbsp;<code>open</code>&nbsp;classes</p>
<ul dir="auto">
<li>
<p dir="auto">java: you have to make an abstract class implementation</p>
</li>
<li>
<p dir="auto">kotlin:&nbsp;<code>open class</code>&nbsp;lets you make an inheritable class while also being usable itself. nice mix of interface and regular class imo</p>
</li>
</ul>
<p dir="auto">extension functions</p>
<ul dir="auto">
<li>
<p dir="auto">java: doesnt exist</p>
</li>
<li>
<p dir="auto">kotlin: does exist, makes functions more clear in usage and feels more natural.</p>
</li>
</ul>
<p dir="auto">null</p>
<ul dir="auto">
<li>
<p dir="auto">java: Anything but primitives can be null at any time.</p>
</li>
<li>
<p dir="auto">kotlin: you get to decide what can and cant be null. allows for nice things like&nbsp;<code>inline class</code></p>
</li>
</ul>
<p dir="auto">singleton</p>
<ul dir="auto">
<li>
<p dir="auto">java: Memorize singleton pattern</p>
</li>
<li>
<p dir="auto">kotlin:&nbsp;<code>object</code>&nbsp;instead of&nbsp;<code>class</code></p>
</li>
</ul>
<p dir="auto">generics</p>
<ul dir="auto">
<li>
<p dir="auto">java: Theyre alright, nothing fancy</p>
</li>
<li>
<p dir="auto">kotlin: Reified generics (you can access the actual type),&nbsp;<code>in</code>&nbsp;and&nbsp;<code>out</code>&nbsp;for covariance</p>
</li>
</ul>
<p dir="auto">named parameters</p>
<ul dir="auto">
<li>
<p dir="auto">java: does not exist, easy to break api back-compatibility if you arent careful.</p>
</li>
<li>
<p dir="auto">kotlin: does exist, easy to preserve api back-compatiblity.</p>
</li>
</ul>
<p dir="auto">primary constructor</p>
<ul dir="auto">
<li>
<p dir="auto">java: does not have per-se, you still have to define everything inside the class</p>
</li>
<li>
<p dir="auto">kotlin: very nice to be able to quickly write a constructor without any constructor function or extra needless declarations</p>
</li>
</ul>
<p dir="auto"><strong>Source:</strong>&nbsp;<em><a href="http://www.reddit.com/" rel="nofollow">www.reddit.com</a></em></p>
<h3 dir="auto"><a id="user-content-q5-what-are-some-disadvantages-of-kotlin-" class="anchor" href="https://gist.github.com/paulfranco/4453383cc6df064d03087ce7aa5a0c8c#q5-what-are-some-disadvantages-of-kotlin-"></a>Q5: What are some disadvantages of Kotlin? ☆☆☆</h3>
<p dir="auto"><strong>Answer:</strong>&nbsp;Some think that Kotlin is a mess of extra syntax and keywords. Here are a few keywords which have non-obvious meanings: internal, crossinline, expect, reified, sealed, inner, open. Java has none of these. Kotlin is also amusingly inconsistent in its keywords: a function is is declared with &lsquo;fun&rsquo;, but an interface is declared with &lsquo;interface&rsquo; (not &lsquo;inter&rsquo;?). Kotlin also doesn&rsquo;t have checked exceptions. Checked exceptions have become unfashionable, yet many (including me) find them a powerful way to ensure that your code is robust. Finally, Kotlin hides a lot of what goes on. In Java, you can trace through almost every step of program logic. This can be vital for hunting down bugs. In Kotlin, if you define a data class, then getters, setters, equality testing, to string, and hash code are added for you invisibly. This can be a bad idea.</p>
<p dir="auto">Also according docs, what Java has that Kotlin does not:</p>
<ul dir="auto">
<li>Checked exceptions</li>
<li>Primitive types that are not classes</li>
<li>Static members</li>
<li>Non-private fields</li>
<li>Wildcard-types</li>
<li>Ternary-operator a ? b : c</li>
</ul>
<p dir="auto"><strong>Source:</strong>&nbsp;<em><a href="http://www.quora.com/" rel="nofollow">www.quora.com</a></em></p>
<h3 dir="auto"><a id="user-content-q6-what-is-the-difference-between-open-and-public-in-kotlin-" class="anchor" href="https://gist.github.com/paulfranco/4453383cc6df064d03087ce7aa5a0c8c#q6-what-is-the-difference-between-open-and-public-in-kotlin-"></a>Q6: What is the difference between "open" and "public" in Kotlin? ☆☆☆</h3>
<p dir="auto"><strong>Answer:</strong></p>
<ul dir="auto">
<li>The&nbsp;<strong>open</strong>&nbsp;keyword means &ldquo;open for extension&ldquo;. The open annotation on a class is the opposite of Java's&nbsp;<code>final</code>:&nbsp;<em>it allows others to inherit from this class</em>.</li>
<li>If you do not specify any visibility modifier,&nbsp;<strong>public</strong>&nbsp;is used by default, which means that your declarations will be visible everywhere.&nbsp;<strong>public</strong>&nbsp;is the default if nothing else is specified explicitly.</li>
</ul>
<p dir="auto"><strong>Source:</strong>&nbsp;<em>stackoverflow.com</em></p>
<h3 dir="auto"><a id="user-content-q7-what-is-the-difference-between-const-and-val-" class="anchor" href="https://gist.github.com/paulfranco/4453383cc6df064d03087ce7aa5a0c8c#q7-what-is-the-difference-between-const-and-val-"></a>Q7: What is the difference between &ldquo;const&rdquo; and &ldquo;val&rdquo;? ☆☆☆</h3>
<p dir="auto"><strong>Answer:</strong>&nbsp;<code>const</code>s are compile time constants. Meaning that their value has to be assigned during compile time, unlike&nbsp;<code>val</code>s, where it can be done at runtime.</p>
<p dir="auto">This means, that&nbsp;<code>const</code>s can never be assigned to a function or any class constructor, but only to a&nbsp;<code>String</code>&nbsp;or primitive.</p>
<p dir="auto">For example:</p>
<div class="highlight highlight-source-kotlin">
<pre><span class="pl-k">const</span> <span class="pl-k">val</span> foo <span class="pl-k">=</span> complexFunctionCall()   <span class="pl-c"><span class="pl-c">//</span>Not okay</span>
<span class="pl-k">val</span> fooVal <span class="pl-k">=</span> complexFunctionCall()      <span class="pl-c"><span class="pl-c">//</span>Okay</span>
 
<span class="pl-k">const</span> <span class="pl-k">val</span> bar <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">"</span>Hello world<span class="pl-pds">"</span></span>           <span class="pl-c"><span class="pl-c">//</span>Also okay</span></pre>
</div>
<p dir="auto"><strong>Source:</strong>&nbsp;<em>stackoverflow.com</em></p>
<h3 dir="auto"><a id="user-content-q8-how-to-convert-list-to-map-in-kotlin-" class="anchor" href="https://gist.github.com/paulfranco/4453383cc6df064d03087ce7aa5a0c8c#q8-how-to-convert-list-to-map-in-kotlin-"></a>Q8: How to convert List to Map in Kotlin? ☆☆☆</h3>
<p dir="auto"><strong>Answer:</strong>&nbsp;You have two choices:</p>
<ul dir="auto">
<li>The first and most performant is to use&nbsp;<code>associateBy</code>&nbsp;function that takes two lambdas for generating the key and value, and inlines the creation of the map:</li>
</ul>
<div class="highlight highlight-source-kotlin">
<pre><span class="pl-k">val</span> map <span class="pl-k">=</span> friends.associateBy({it.facebookId}, {it.points})</pre>
</div>
<ul dir="auto">
<li>The second, less performant, is to use the standard&nbsp;<code>map</code>&nbsp;function to create a list of&nbsp;<code>Pair</code>&nbsp;which can be used by&nbsp;<code>toMap</code>&nbsp;to generate the final map:</li>
</ul>
<div class="highlight highlight-source-kotlin">
<pre><span class="pl-k">val</span> map <span class="pl-k">=</span> friends.map { it.facebookId to it.points }.toMap()</pre>
</div>
<p dir="auto"><strong>Source:</strong>&nbsp;<em>stackoverflow.com</em></p>
<h3 dir="auto"><a id="user-content-q9-what-is-the-idiomatic-way-to-deal-with-nullable-values-referencing-or-converting-them-" class="anchor" href="https://gist.github.com/paulfranco/4453383cc6df064d03087ce7aa5a0c8c#q9-what-is-the-idiomatic-way-to-deal-with-nullable-values-referencing-or-converting-them-"></a>Q9: What is the idiomatic way to deal with nullable values, referencing or converting them? ☆☆☆</h3>
<p dir="auto"><strong>Details:</strong>&nbsp;If I have a nullable type&nbsp;<code>Xyz?</code>, I want to reference it or convert it to a non-nullable type&nbsp;<code>Xyz</code>. What is the idiomatic way of doing so in Kotlin?</p>
<p dir="auto"><strong>Answer:</strong>&nbsp;You have several options:</p>
<div class="highlight highlight-source-kotlin">
<pre><span class="pl-k">val</span> something<span class="pl-k">:</span> <span class="pl-en">Xyz</span><span class="pl-k">?</span> <span class="pl-k">=</span> createPossiblyNullXyz()

<span class="pl-c"><span class="pl-c">//</span> access it as non-null asserting that with a sure call</span>
<span class="pl-c"><span class="pl-c">//</span> throws an exception if the value is null</span>
<span class="pl-k">val</span> result1 <span class="pl-k">=</span> something<span class="pl-k">!!</span>.foo()

<span class="pl-c"><span class="pl-c">//</span> access it only if it is not null using safe operator, </span>
<span class="pl-c"><span class="pl-c">//</span> returning null otherwise</span>
<span class="pl-k">val</span> result2 <span class="pl-k">=</span> something?.foo()

<span class="pl-c"><span class="pl-c">//</span> access it only if it is not null using safe operator, </span>
<span class="pl-c"><span class="pl-c">//</span> otherwise a default value using the elvis operator</span>
<span class="pl-k">val</span> result3 <span class="pl-k">=</span> something?.foo() <span class="pl-k">?</span><span class="pl-k">:</span> differentValue

<span class="pl-c"><span class="pl-c">//</span> null check it with `if` expression and then use the value, </span>
<span class="pl-c"><span class="pl-c">//</span> similar to result3 but for more complex cases harder to do in one expression</span>
<span class="pl-k">val</span> result4 <span class="pl-k">=</span> <span class="pl-k">if</span> (something <span class="pl-k">!=</span> <span class="pl-c1">null</span>) {
                   something.foo() 
              } <span class="pl-k">else</span> { 
                   <span class="pl-k">..</span>.
                   differentValue 
              }

<span class="pl-c"><span class="pl-c">//</span> null check it with `if` statement doing a different action</span>
<span class="pl-k">if</span> (something <span class="pl-k">!=</span> <span class="pl-c1">null</span>) { 
    something.foo() 
} <span class="pl-k">else</span> { 
    someOtherAction() 
}</pre>
</div>
<p dir="auto"><strong>Source:</strong>&nbsp;<em>stackoverflow.com</em></p>
<h3 dir="auto"><a id="user-content-q10-what-is-the-difference-between-list-and-array-types-" class="anchor" href="https://gist.github.com/paulfranco/4453383cc6df064d03087ce7aa5a0c8c#q10-what-is-the-difference-between-list-and-array-types-"></a>Q10: What is the difference between List and Array types? ☆☆☆</h3>
<p dir="auto"><strong>Answer:</strong>&nbsp;The major difference from usage side is that&nbsp;<code>Arrays</code>&nbsp;have a fixed size while&nbsp;<code>(Mutable)List&nbsp;</code>can adjust their size dynamically. Moreover&nbsp;<code>Array</code>&nbsp;is mutable whereas&nbsp;<code>List</code>&nbsp;is not.</p>
<p dir="auto">Furthermore&nbsp;<code>kotlin.collections.List</code>&nbsp;is an interface implemented among others by&nbsp;<code>java.util.ArrayList</code>. It's also extended by&nbsp;<code>kotlin.collections.MutableList&nbsp;</code>to be used when a collections that allows for item modification is needed.</p>
<p dir="auto">On the jvm level&nbsp;<code>Array</code>&nbsp;is represented by arrays.&nbsp;<code>List</code>&nbsp;on the other hand is represented by&nbsp;<code>java.util.List</code>&nbsp;since there are no immutable collections equivalents available in Java.</p>
<p dir="auto"><strong>Source:</strong>&nbsp;<em>stackoverflow.com</em></p>
<h3 dir="auto"><a id="user-content-q11-val-mutablelist-vs-var-immutablelist-when-to-use-which-in-kotlin-" class="anchor" href="https://gist.github.com/paulfranco/4453383cc6df064d03087ce7aa5a0c8c#q11-val-mutablelist-vs-var-immutablelist-when-to-use-which-in-kotlin-"></a>Q11: val mutableList vs var immutableList. When to use which in Kotlin? ☆☆☆</h3>
<p dir="auto"><strong>Answer:</strong>&nbsp;Mutable and immutable list increase the design clarity of the model.<br />This is to force developer to think and clarify the purpose of collection.</p>
<ol dir="auto">
<li>If the collection will change as part of design, use mutable collection</li>
<li>If model is meant only for viewing, use immutable list</li>
</ol>
<p dir="auto">Purpose of&nbsp;<code>val</code>&nbsp;and&nbsp;<code>var</code>&nbsp;is different from immutable and mutable list.<br /><em><strong><code>val</code></strong></em>&nbsp;and&nbsp;<em><strong><code>var</code></strong></em>&nbsp;keyword talk about the how a value/reference of a variable should be treated.</p>
<ul dir="auto">
<li><em><strong><code>var</code></strong></em>&nbsp;- value/reference assigned to a variable can be changed at any point of time.</li>
<li><em><strong><code>val</code></strong></em>&nbsp;- value/reference can be assigned only once to a variable and can't be changed later point in the execution.</li>
</ul>
<p dir="auto">There are several reasons why immutable objects are often preferable:</p>
<ul dir="auto">
<li>They encourage functional programming, where state is not mutated, but passed on to the next function which creates a new state based on it. This is very well visible in the Kotlin collection methods such as map, filter, reduce, etc.</li>
<li>A program without side effects is often easier to understand and debug (you can be sure that the value of an object will always be the one at its definition).</li>
<li>In multithreaded programs, immutable resources cannot cause race conditions, as no write access is involved.</li>
</ul>
<p dir="auto">You have also some disadvantages:</p>
<ul dir="auto">
<li>Copying entire collections just to add/remove a single element is computationally expensive.</li>
<li>In some cases, immutability can make the code more complex, when you tediously need to change single fields. In Kotlin, data classes come with a built-in copy() method where you can copy an instance, while providing new values for only some of the fields.</li>
</ul>
<p dir="auto"><strong>Source:</strong>&nbsp;<em>stackoverflow.com</em></p>
<h3 dir="auto"><a id="user-content-q12-what-is-a-difference-between-a-class-and-object-in-kotlin-" class="anchor" href="https://gist.github.com/paulfranco/4453383cc6df064d03087ce7aa5a0c8c#q12-what-is-a-difference-between-a-class-and-object-in-kotlin-"></a>Q12: What is a difference between a class and object in Kotlin? ☆☆☆</h3>
<p dir="auto"><strong>Answer:</strong></p>
<ul dir="auto">
<li>An&nbsp;<strong>object</strong>&nbsp;is a singleton. You do not need to create an instance to use it.</li>
<li>A&nbsp;<strong>class</strong>&nbsp;needs to be instantiated to be used.</li>
</ul>
<p dir="auto">The primary use case of&nbsp;<code>object</code>&nbsp;in Kotlin is because Kotlin tries to do away with static, and primitives, leaving us with a purely object oriented language. Kotlin still uses&nbsp;<code>static</code>&nbsp;and primitives underneath the hood, but it discourages devs to use those concepts any more. Instead, now Kotlin replaces static with singleton object instances. Where you would previously use static field in Java, in Kotlin you will now create an&nbsp;<code>object</code>, and put that field in the&nbsp;<code>object</code>.</p>
<p dir="auto"><strong>Source:</strong>&nbsp;<em>stackoverflow.com</em></p>
<h3 dir="auto"><a id="user-content-q13-how-is-it-recommended-to-create-constants-in-kotlin-" class="anchor" href="https://gist.github.com/paulfranco/4453383cc6df064d03087ce7aa5a0c8c#q13-how-is-it-recommended-to-create-constants-in-kotlin-"></a>Q13: How is it recommended to create constants in Kotlin? ☆☆☆</h3>
<p dir="auto"><strong>Answer:</strong>&nbsp;In Kotlin, if you want to create the local constants which are supposed to be used with in the class then you can create it like below:</p>
<div class="highlight highlight-source-kotlin">
<pre><span class="pl-k">val</span> <span class="pl-en">MY_CONSTANT_1</span> <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">"</span>Constants1<span class="pl-pds">"</span></span>
<span class="pl-c"><span class="pl-c">//</span> or </span>
<span class="pl-k">const</span> <span class="pl-k">val</span> <span class="pl-en">MY_CONSTANT_2</span> <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">"</span>Constants2<span class="pl-pds">"</span></span></pre>
</div>
<p dir="auto">Like&nbsp;<code>val</code>, variables defined with the&nbsp;<code>const</code>&nbsp;keyword are immutable. The difference here is that&nbsp;<strong>const is used for variables that are known at compile-time</strong>.</p>
<p dir="auto">Also avoid using companion objects. Behind the hood, getter and setter instance methods are created for the fields to be accessible. Calling instance methods is technically more expensive than calling static methods. Instead define the constants in&nbsp;<code>object</code>:</p>
<div class="highlight highlight-source-kotlin">
<pre><span class="pl-k">object</span> <span class="pl-en">DbConstants</span> {
        <span class="pl-k">const</span> <span class="pl-k">val</span> <span class="pl-en">TABLE_USER_ATTRIBUTE_EMPID</span> <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">"</span>_id<span class="pl-pds">"</span></span>
        <span class="pl-k">const</span> <span class="pl-k">val</span> <span class="pl-en">TABLE_USER_ATTRIBUTE_DATA</span> <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">"</span>data<span class="pl-pds">"</span></span>
}</pre>
</div>
<p dir="auto"><strong>Source:</strong>&nbsp;<em>stackoverflow.com</em></p>
<h3 dir="auto"><a id="user-content-q14-may-you-use-intarray-and-an-array-is-in-kotlin-interchangeably-" class="anchor" href="https://gist.github.com/paulfranco/4453383cc6df064d03087ce7aa5a0c8c#q14-may-you-use-intarray-and-an-array-is-in-kotlin-interchangeably-"></a>Q14: May you use IntArray and an Array is in Kotlin interchangeably? ☆☆☆</h3>
<p dir="auto"><strong>Answer:</strong>&nbsp;<code>Array&lt;Int&gt;</code>&nbsp;is an&nbsp;<code>Integer[]</code>&nbsp;under the hood, while&nbsp;<code>IntArray</code>&nbsp;is an&nbsp;<code>int[]</code>.</p>
<p dir="auto">This means that when you put an&nbsp;<code>Int</code>&nbsp;in an&nbsp;<code>Array&lt;Int&gt;</code>, it will always be boxed (specifically, with an&nbsp;<code>Integer.valueOf()</code>&nbsp;call). In the case of&nbsp;<code>IntArray</code>, no boxing will occur, because it translates to a Java primitive array.</p>
<p dir="auto">So&nbsp;<strong>no</strong>, we can't use them interchangeably.</p>
<div dir="auto"><a href="https://camo.githubusercontent.com/f31a6f1696316631748929d85bf33164afc485753025719916f4f2f598efe891/68747470733a2f2f692e737461636b2e696d6775722e636f6d2f7277644d752e706e67" target="_blank" rel="noopener noreferrer"><img src="https://camo.githubusercontent.com/f31a6f1696316631748929d85bf33164afc485753025719916f4f2f598efe891/68747470733a2f2f692e737461636b2e696d6775722e636f6d2f7277644d752e706e67" alt="" data-canonical-src="https://i.stack.imgur.com/rwdMu.png" /></a></div>
<p dir="auto"><strong>Source:</strong>&nbsp;<em>stackoverflow.com</em></p>
<h3 dir="auto"><a id="user-content-q15-rewrite-this-code-in-kotlin-" class="anchor" href="https://gist.github.com/paulfranco/4453383cc6df064d03087ce7aa5a0c8c#q15-rewrite-this-code-in-kotlin-"></a>Q15: Rewrite this code in Kotlin ☆☆☆</h3>
<p dir="auto"><strong>Details:</strong>&nbsp;Can you rewrite this Java code in Kotlin?</p>
<div class="highlight highlight-source-java">
<pre><span class="pl-k">public</span> <span class="pl-k">class</span> <span class="pl-en">Singleton</span> {
    <span class="pl-k">private</span> <span class="pl-k">static</span> <span class="pl-smi">Singleton</span> instance <span class="pl-k">=</span> <span class="pl-c1">null</span>;
    <span class="pl-k">private</span> <span class="pl-en">Singleton</span>(){
    }
    <span class="pl-k">private</span> <span class="pl-k">synchronized</span> <span class="pl-k">static</span> <span class="pl-k">void</span> <span class="pl-en">createInstance</span>() {
        <span class="pl-k">if</span> (instance <span class="pl-k">==</span> <span class="pl-c1">null</span>) {
            instance <span class="pl-k">=</span> <span class="pl-k">new</span> <span class="pl-smi">Singleton</span>();
        }
    }
    <span class="pl-k">public</span> <span class="pl-k">static</span> <span class="pl-smi">Singleton</span> <span class="pl-en">getInstance</span>() {
        <span class="pl-k">if</span> (instance <span class="pl-k">==</span> <span class="pl-c1">null</span>) createInstance();
        <span class="pl-k">return</span> instance;
    }
</pre>
</div>
<p dir="auto"><strong>Answer:</strong>&nbsp;Using Kotlin:</p>
<div class="highlight highlight-source-kotlin">
<pre><span class="pl-k">object</span> <span class="pl-en">Singleton</span></pre>
</div>
<p dir="auto"><strong>Source:</strong>&nbsp;<em>antonioleiva.com</em></p>
<h3 dir="auto"><a id="user-content-q16-how-would-you-create-a-singleton-with-parameter-in-kotlin-" class="anchor" href="https://gist.github.com/paulfranco/4453383cc6df064d03087ce7aa5a0c8c#q16-how-would-you-create-a-singleton-with-parameter-in-kotlin-"></a>Q16: How would you create a singleton with parameter in Kotlin? ☆☆☆</h3>
<p dir="auto"><strong>Answer:</strong>&nbsp;Because a Kotlin&nbsp;<code>object</code>&nbsp;can&rsquo;t have any constructor, you can&rsquo;t pass any argument to it.</p>
<p dir="auto">So look at this code from Google's architecture components sample code, which uses the&nbsp;<code>also</code>&nbsp;function:</p>
<div class="highlight highlight-source-kotlin">
<pre><span class="pl-k">class</span> <span class="pl-en">UsersDatabase</span> : <span class="pl-en">RoomDatabase</span>() {

    <span class="pl-k">companion</span> <span class="pl-k">object</span> {

        @Volatile <span class="pl-k">private</span> <span class="pl-k">var</span> <span class="pl-en">INSTANCE</span><span class="pl-k">:</span> <span class="pl-en">UsersDatabase</span><span class="pl-k">?</span> <span class="pl-k">=</span> <span class="pl-c1">null</span>

        <span class="pl-k">fun</span> <span class="pl-en">getInstance</span>(<span class="pl-smi">context</span><span class="pl-k">:</span> <span class="pl-en">Context</span>): <span class="pl-en">UsersDatabase</span> <span class="pl-k">=</span>
            <span class="pl-en">INSTANCE</span> <span class="pl-k">?</span><span class="pl-k">:</span> synchronized(<span class="pl-c1">this</span>) {
                <span class="pl-en">INSTANCE</span> <span class="pl-k">?</span><span class="pl-k">:</span> buildDatabase(context).<span class="pl-c1">also</span> { <span class="pl-en">INSTANCE</span> <span class="pl-k">=</span> it }
            }

        <span class="pl-k">private</span> <span class="pl-k">fun</span> <span class="pl-en">buildDatabase</span>(<span class="pl-smi">context</span><span class="pl-k">:</span> <span class="pl-en">Context</span>) <span class="pl-k">=</span>
            <span class="pl-en">Room</span>.databaseBuilder(context.applicationContext,
                    <span class="pl-en">UsersDatabase</span>::<span class="pl-c1">class</span>.java, <span class="pl-s"><span class="pl-pds">"</span>Sample.db<span class="pl-pds">"</span></span>)
                    .build()
    }
}</pre>
</div>
<p dir="auto"><strong>Source:</strong>&nbsp;<em>stackoverflow.com</em></p>
<h3 dir="auto"><a id="user-content-q17-what-is-the-kotlin-double-bang--operator-" class="anchor" href="https://gist.github.com/paulfranco/4453383cc6df064d03087ce7aa5a0c8c#q17-what-is-the-kotlin-double-bang--operator-"></a>Q17: What is the Kotlin double-bang (!!) operator? ☆☆☆</h3>
<p dir="auto"><strong>Answer:</strong>&nbsp;The&nbsp;<strong>not-null assertion operator !!</strong>&nbsp;converts any value to a non-null type and throws a&nbsp;<code>KotlinNullPointerException</code>&nbsp;exception if the value is null.</p>
<p dir="auto">Consider:</p>
<div class="highlight highlight-source-kotlin">
<pre><span class="pl-k">fun</span> <span class="pl-en">main</span>(<span class="pl-smi">args</span><span class="pl-k">:</span> <span class="pl-c1">Array</span>&lt;<span class="pl-en">String</span>&gt;) {
    <span class="pl-k">var</span> email<span class="pl-k">:</span> <span class="pl-c1">String?</span>
    email <span class="pl-k">=</span> <span class="pl-c1">null</span>
    <span class="pl-c1">println</span>(email<span class="pl-k">!!</span>)
}</pre>
</div>
<p dir="auto">This operator should be used in cases where the developer is guaranteeing &ndash; it allows you to be 100% sure that its value is not null.</p>
<p dir="auto"><strong>Source:</strong>&nbsp;<em>stackoverflow.com</em></p>
<h3 dir="auto"><a id="user-content-q18-what-is-the-purpose-of-unit-returning-in-functions-why-is-value-there-what-is-this-value-" class="anchor" href="https://gist.github.com/paulfranco/4453383cc6df064d03087ce7aa5a0c8c#q18-what-is-the-purpose-of-unit-returning-in-functions-why-is-value-there-what-is-this-value-"></a>Q18: What is the purpose of Unit-returning in functions? Why is VALUE there? What is this VALUE? ☆☆☆</h3>
<p dir="auto"><strong>Details:</strong>&nbsp;Explain what is the purpose of Unit-returning in functions? Why is VALUE there? What is this VALUE?</p>
<div class="highlight highlight-source-kotlin">
<pre><span class="pl-k">fun</span> <span class="pl-en">printHello</span>(<span class="pl-smi">name</span> <span class="pl-k">:</span> <span class="pl-c1">String?</span>) : <span class="pl-c1">Unit</span> { 
   <span class="pl-k">if</span> (name <span class="pl-k">!=</span> <span class="pl-c1">null</span>) 
     <span class="pl-c1">print</span>(<span class="pl-s"><span class="pl-pds">"</span>Hello, <span class="pl-e">$name</span>!<span class="pl-pds">"</span></span>) 
   <span class="pl-k">else</span> 
     <span class="pl-c1">print</span>(<span class="pl-s"><span class="pl-pds">"</span>Hi there!<span class="pl-pds">"</span></span>) 
   <span class="pl-c"><span class="pl-c">//</span> We don't need to write 'return Unit.VALUE' or 'return', although we could </span>
}</pre>
</div>
<p dir="auto"><strong>Answer:</strong>&nbsp;The purpose is the same as C's or Java's&nbsp;<code>void</code>. Only Unit is a proper type, so it can be passed as a generic argument etc.</p>
<ol dir="auto">
<li>
<p dir="auto">Why we don't call it "Void": because the word "void" means "nothing", and there's another type,&nbsp;<code>Nothing</code>, that means just "no value at all", i.e. the computation did not complete normally (looped forever or threw an exception). We could not afford the clash of meanings.</p>
</li>
<li>
<p dir="auto">Why Unit has a value (i.e. is not the same as Nothing): because generic code can work smoothly then. If you pass Unit for a generic parameter T, the code written for any T will expect an object, and there must be an object, the sole value of Unit.</p>
</li>
<li>
<p dir="auto">How to access that value of Unit: since it's a singleton object, just say&nbsp;<code>Unit</code></p>
</li>
<li>
<p dir="auto"><code>UNIT</code>&nbsp;actually contains valuable information, it basically just means "DONE". It just returns the information to the caller, that the method has been finished.</p>
</li>
</ol>
<p dir="auto"><strong>Source:</strong>&nbsp;<em>stackoverflow.com</em></p>
<h3 dir="auto"><a id="user-content-q19-when-would-you-use-elvis-operator-in-kotlin-" class="anchor" href="https://gist.github.com/paulfranco/4453383cc6df064d03087ce7aa5a0c8c#q19-when-would-you-use-elvis-operator-in-kotlin-"></a>Q19: When would you use Elvis operator in Kotlin? ☆☆☆</h3>
<p dir="auto"><strong>Answer:</strong>&nbsp;The Elvis operator is part of many programming languages, e.g. Kotlin but also Groovy or C#. The Elvis operator is the ternary operator with its second operand omitted.</p>
<div class="highlight highlight-source-kotlin">
<pre>x <span class="pl-k">?</span><span class="pl-k">:</span> y <span class="pl-c"><span class="pl-c">//</span> yields `x` if `x` is not null, `y` otherwise.</span></pre>
</div>
<p dir="auto">If&nbsp;<code>x</code>&nbsp;isn't null, then it will be returned. If it is null, then the&nbsp;<code>y</code>&nbsp;will be returned.</p>
<p dir="auto"><strong>Source:</strong>&nbsp;<em>kotlinlang.org</em></p>
<h3 dir="auto"><a id="user-content-q40-what-are-scope-functions-in-kotlin-" class="anchor" href="https://gist.github.com/paulfranco/4453383cc6df064d03087ce7aa5a0c8c#q40-what-are-scope-functions-in-kotlin-"></a>Q40: What are scope functions in Kotlin? ☆☆☆</h3>
<p dir="auto"><strong>Answer:</strong>&nbsp;The Kotlin standard library contains several functions whose sole purpose is to execute a block of code within the context of an object. When you call such a function on an object with a lambda expression provided, it forms a temporary scope. In this scope, you can access the object without its name. Such functions are called&nbsp;<strong>scope functions</strong>.</p>
<p dir="auto">There are five of them:</p>
<ul dir="auto">
<li><code>let</code>,</li>
<li><code>run</code>,</li>
<li><code>with</code>,</li>
<li><code>apply</code>,</li>
<li><code>also</code>.</li>
</ul>
<p dir="auto"><strong>Source:</strong>&nbsp;<em>stackoverflow.com</em></p>
<h3 dir="auto"><a id="user-content-q1-why-is-there-no-static-keyword-in-kotlin-" class="anchor" href="https://gist.github.com/paulfranco/4453383cc6df064d03087ce7aa5a0c8c#q1-why-is-there-no-static-keyword-in-kotlin-"></a>Q1: Why is there no static keyword in Kotlin? ☆☆☆☆</h3>
<p dir="auto"><strong>Answer:</strong>&nbsp;<em>The main advantage of this is that everything is an object</em>. Companion objects can inherit from other classes or implement interfaces and generally behave like any other singleton.</p>
<p dir="auto">In Java, static members are treated very differently than object members. This means that you can't do things like implementing an interface or putting your class "instance" into a map or pass it as a parameter to a method that takes Object. Companion objects allow for these things. That's the advantage.</p>
<p dir="auto"><strong>Source:</strong>&nbsp;<em>softwareengineering.stackexchange.com</em></p>
<h3 dir="auto"><a id="user-content-q2-what-is-inline-class-in-kotlin-and-when-do-we-need-one-provide-an-example-" class="anchor" href="https://gist.github.com/paulfranco/4453383cc6df064d03087ce7aa5a0c8c#q2-what-is-inline-class-in-kotlin-and-when-do-we-need-one-provide-an-example-"></a>Q2: What is inline class in Kotlin and when do we need one? Provide an example. ☆☆☆☆</h3>
<p dir="auto"><strong>Answer:</strong>&nbsp;Sometimes it is necessary for business logic to create a wrapper around some type. However, it introduces runtime overhead due to additional heap allocations. Moreover, if the wrapped type is primitive, the performance hit is terrible, because primitive types are usually heavily optimized by the runtime.</p>
<p dir="auto"><strong>Inline classes</strong>&nbsp;provide us with a way to wrap a type, thus adding functionality and creating a new type by itself. As opposed to regular (non-inlined) wrappers, they will benefit from improved performance. This happens because the data is inlined into its usages, and object instantiation is skipped in the resulting compiled code.</p>
<div class="highlight highlight-source-kotlin">
<pre><span class="pl-k">inline</span> <span class="pl-k">class</span> <span class="pl-en">Name</span>(<span class="pl-k">val</span> <span class="pl-smi">s</span><span class="pl-k">:</span> <span class="pl-c1">String</span>) {
    <span class="pl-k">val</span> length<span class="pl-k">:</span> <span class="pl-c1">Int</span>
        get() <span class="pl-k">=</span> s.length

    <span class="pl-k">fun</span> <span class="pl-en">greet</span>() {
        <span class="pl-c1">println</span>(<span class="pl-s"><span class="pl-pds">"</span>Hello, <span class="pl-e">$s</span><span class="pl-pds">"</span></span>)
    }
}    

<span class="pl-k">fun</span> <span class="pl-en">main</span>() {
    <span class="pl-k">val</span> name <span class="pl-k">=</span> <span class="pl-en">Name</span>(<span class="pl-s"><span class="pl-pds">"</span>Kotlin<span class="pl-pds">"</span></span>)
    name.greet() <span class="pl-c"><span class="pl-c">//</span> method `greet` is called as a static method</span>
    <span class="pl-c1">println</span>(name.length) <span class="pl-c"><span class="pl-c">//</span> property getter is called as a static method</span>
}</pre>
</div>
<p dir="auto">Some notes about inline classes:</p>
<ul dir="auto">
<li>A single property initialized in the primary constructor is the basic requirement of an inline class</li>
<li>Inline classes allow us to define properties and functions just like regular classes</li>
<li>Init blocks, inner classes, and backing fields are not allowed</li>
<li>Inline classes can inherit only from interfaces</li>
<li>Inline classes are also effectively final</li>
</ul>
<p dir="auto"><strong>Source:</strong>&nbsp;<em><a href="http://www.baeldung.com/" rel="nofollow">www.baeldung.com</a></em></p>
<h3 dir="auto"><a id="user-content-q3-explain-the-difference-between-inline-classes-vs-type-aliases-" class="anchor" href="https://gist.github.com/paulfranco/4453383cc6df064d03087ce7aa5a0c8c#q3-explain-the-difference-between-inline-classes-vs-type-aliases-"></a>Q3: Explain the difference between Inline classes vs type aliases ☆☆☆☆</h3>
<p dir="auto"><strong>Answer:</strong>&nbsp;The crucial difference is that type aliases are&nbsp;<strong>assignment-compatible</strong>&nbsp;with their underlying type (and with other type aliases with the same underlying type), while inline classes are not.</p>
<p dir="auto">In other words, inline classes introduce a truly new type, contrary to type aliases which only introduce an alternative name (alias) for an existing type:</p>
<div class="highlight highlight-source-kotlin">
<pre><span class="pl-k">typealias</span> <span class="pl-en">NameTypeAlias</span> <span class="pl-k">=</span> <span class="pl-c1">String</span>
<span class="pl-k">inline</span> <span class="pl-k">class</span> <span class="pl-en">NameInlineClass</span>(<span class="pl-k">val</span> <span class="pl-smi">s</span><span class="pl-k">:</span> <span class="pl-c1">String</span>)

<span class="pl-k">fun</span> <span class="pl-en">acceptString</span>(<span class="pl-smi">s</span><span class="pl-k">:</span> <span class="pl-c1">String</span>) {}
<span class="pl-k">fun</span> <span class="pl-en">acceptNameTypeAlias</span>(<span class="pl-smi">n</span><span class="pl-k">:</span> <span class="pl-en">NameTypeAlias</span>) {}
<span class="pl-k">fun</span> <span class="pl-en">acceptNameInlineClass</span>(<span class="pl-smi">p</span><span class="pl-k">:</span> <span class="pl-en">NameInlineClass</span>) {}

<span class="pl-k">fun</span> <span class="pl-en">main</span>() {
    <span class="pl-k">val</span> nameAlias<span class="pl-k">:</span> <span class="pl-en">NameTypeAlias</span> <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">"</span><span class="pl-pds">"</span></span>
    <span class="pl-k">val</span> nameInlineClass<span class="pl-k">:</span> <span class="pl-en">NameInlineClass</span> <span class="pl-k">=</span> <span class="pl-en">NameInlineClass</span>(<span class="pl-s"><span class="pl-pds">"</span><span class="pl-pds">"</span></span>)
    <span class="pl-k">val</span> string<span class="pl-k">:</span> <span class="pl-c1">String</span> <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">"</span><span class="pl-pds">"</span></span>

    acceptString(nameAlias) <span class="pl-c"><span class="pl-c">//</span> OK: pass alias instead of underlying type</span>
    acceptString(nameInlineClass) <span class="pl-c"><span class="pl-c">//</span> Not OK: can't pass inline class instead of underlying type</span>

    <span class="pl-c"><span class="pl-c">//</span> And vice versa:</span>
    acceptNameTypeAlias(string) <span class="pl-c"><span class="pl-c">//</span> OK: pass underlying type instead of alias</span>
    acceptNameInlineClass(string) <span class="pl-c"><span class="pl-c">//</span> Not OK: can't pass underlying type instead of inline class</span>
}</pre>
</div>
<p dir="auto"><strong>Source:</strong>&nbsp;<em>blog.mindorks.com</em></p>
<h3 dir="auto"><a id="user-content-q4-what-is-coroutine-scope-and-how-is-that-different-from-coroutine-context-" class="anchor" href="https://gist.github.com/paulfranco/4453383cc6df064d03087ce7aa5a0c8c#q4-what-is-coroutine-scope-and-how-is-that-different-from-coroutine-context-"></a>Q4: What is Coroutine Scope and how is that different from Coroutine Context? ☆☆☆☆</h3>
<p dir="auto"><strong>Answer:</strong></p>
<ul dir="auto">
<li>
<p dir="auto">Coroutines always execute in some context represented by a value of the&nbsp;<strong>CoroutineContext</strong>&nbsp;type, defined in the Kotlin standard library. The coroutine context is a set of various elements. The main elements are the&nbsp;<strong>Job</strong>&nbsp;of the coroutine.</p>
</li>
<li>
<p dir="auto"><strong>CoroutineScope</strong>&nbsp;has no data on its own, it just holds a&nbsp;<strong>CoroutineContext</strong>. Its key role is as the implicit receiver of the block you pass to&nbsp;<code>launch</code>,&nbsp;<code>async</code>&nbsp;etc.</p>
</li>
</ul>
<div class="highlight highlight-source-kotlin">
<pre>runBlocking {
   <span class="pl-k">val</span> scope0 <span class="pl-k">=</span> <span class="pl-c1">this</span>
   <span class="pl-c"><span class="pl-c">//</span> scope0 is the top-level coroutine scope.</span>
   scope0.launch {
       <span class="pl-k">val</span> scope1 <span class="pl-k">=</span> <span class="pl-c1">this</span>
       <span class="pl-c"><span class="pl-c">//</span> scope1 inherits its context from scope0. It replaces the Job field</span>
       <span class="pl-c"><span class="pl-c">//</span> with its own job, which is a child of the job in scope0.</span>
       <span class="pl-c"><span class="pl-c">//</span> It retains the Dispatcher field so the launched coroutine uses</span>
       <span class="pl-c"><span class="pl-c">//</span> the dispatcher created by runBlocking.</span>
       scope1.launch {
           <span class="pl-k">val</span> scope2 <span class="pl-k">=</span> <span class="pl-c1">this</span>
           <span class="pl-c"><span class="pl-c">//</span> scope2 inherits from scope1</span>
       }
   }
}</pre>
</div>
<p dir="auto">You might say that&nbsp;<strong>CoroutineScope</strong>&nbsp;formalizes the way the&nbsp;<strong>CoroutineContext</strong>&nbsp;is inherited. You can see how the&nbsp;<strong>CoroutineScope</strong>&nbsp;mediates the inheritance of coroutine contexts. If you cancel the job in&nbsp;<code>scope1</code>, this will propagate to&nbsp;<code>scope2</code>&nbsp;and will cancel the launched job as well.</p>
<p dir="auto"><strong>Source:</strong>&nbsp;<em>stackoverflow.com</em></p>
<h3 dir="auto"><a id="user-content-q5-imagine-you-moving-your-code-from-java-to-kotlin-how-would-you-rewrite-this-code-in-kotlin-" class="anchor" href="https://gist.github.com/paulfranco/4453383cc6df064d03087ce7aa5a0c8c#q5-imagine-you-moving-your-code-from-java-to-kotlin-how-would-you-rewrite-this-code-in-kotlin-"></a>Q5: Imagine you moving your code from Java to Kotlin. How would you rewrite this code in Kotlin? ☆☆☆☆☆</h3>
<p dir="auto"><strong>Details:</strong></p>
<div class="highlight highlight-source-java">
<pre><span class="pl-k">public</span> <span class="pl-k">class</span> <span class="pl-en">Foo</span> {
    <span class="pl-k">private</span> <span class="pl-k">static</span> <span class="pl-k">final</span> <span class="pl-smi">Logger</span> <span class="pl-c1">LOG</span> <span class="pl-k">=</span> <span class="pl-smi">LoggerFactory</span><span class="pl-k">.</span>getLogger(<span class="pl-smi">Foo</span><span class="pl-k">.</span>class);
}</pre>
</div>
<p dir="auto"><strong>Answer:</strong>&nbsp;Use&nbsp;<strong>Static-like</strong>&nbsp;approach:</p>
<div class="highlight highlight-source-kotlin">
<pre><span class="pl-k">class</span> <span class="pl-en">MyClass</span> {
    <span class="pl-k">companion</span> <span class="pl-k">object</span> {
        <span class="pl-k">val</span> <span class="pl-en">LOG</span> <span class="pl-k">=</span> <span class="pl-en">Logger</span>.getLogger(<span class="pl-en">MyClass</span>::<span class="pl-c1">class</span>.java.name) 
    }

    <span class="pl-k">fun</span> <span class="pl-en">foo</span>() {
        <span class="pl-en">LOG</span>.warning(<span class="pl-s"><span class="pl-pds">"</span>Hello from MyClass<span class="pl-pds">"</span></span>)
    }
}  </pre>
</div>
<p dir="auto"><strong>Source:</strong>&nbsp;<em>stackoverflow.com</em></p>
<h3 dir="auto"><a id="user-content-q6-how-would-you-override-default-getter-for-kotlin-data-class-" class="anchor" href="https://gist.github.com/paulfranco/4453383cc6df064d03087ce7aa5a0c8c#q6-how-would-you-override-default-getter-for-kotlin-data-class-"></a>Q6: How would you override default getter for Kotlin data class? ☆☆☆☆</h3>
<p dir="auto"><strong>Details:</strong>&nbsp;Given the following Kotlin class:</p>
<div class="highlight highlight-source-kotlin">
<pre><span class="pl-k">data class</span> <span class="pl-en">Test</span>(<span class="pl-k">val</span> <span class="pl-smi">value</span><span class="pl-k">:</span> <span class="pl-c1">Int</span>)</pre>
</div>
<p dir="auto">How would I override the Int getter so that it returns&nbsp;<code>0</code>&nbsp;if the value negative?</p>
<p dir="auto"><strong>Answer:</strong></p>
<ol dir="auto">
<li>Have your business logic that creates the data class alter the value to be 0 or greater before calling the constructor with the bad value. This is probably the best approach for most cases.</li>
<li>Don't use a&nbsp;<code>data class</code>. Use a regular&nbsp;<code>class</code>.</li>
</ol>
<div class="highlight highlight-source-kotlin">
<pre><span class="pl-k">class</span> <span class="pl-en">Test</span>(<span class="pl-smi">value</span><span class="pl-k">:</span> <span class="pl-c1">Int</span>) {
   <span class="pl-k">val</span> value<span class="pl-k">:</span> <span class="pl-c1">Int</span> <span class="pl-k">=</span> value
    get() <span class="pl-k">=</span> <span class="pl-k">if</span> (field <span class="pl-k">&lt;</span> <span class="pl-c1">0</span>) <span class="pl-c1">0</span> <span class="pl-k">else</span> field

    <span class="pl-k">override</span> <span class="pl-k">fun</span> <span class="pl-en">equals</span>(<span class="pl-smi">other</span><span class="pl-k">:</span> <span class="pl-c1">Any?</span>): <span class="pl-c1">Boolean</span> {
     <span class="pl-k">if</span> (<span class="pl-c1">this</span> <span class="pl-k">==</span><span class="pl-k">=</span> other) <span class="pl-k">return</span> <span class="pl-c1">true</span>
     <span class="pl-k">if</span> (other <span class="pl-k">!is</span> <span class="pl-en">Test</span>) <span class="pl-k">return</span> <span class="pl-c1">false</span>
     <span class="pl-k">return</span> <span class="pl-c1">true</span>
   }

   <span class="pl-k">override</span> <span class="pl-k">fun</span> <span class="pl-en">hashCode</span>(): <span class="pl-c1">Int</span> {
     <span class="pl-k">return</span> javaClass.hashCode()
   }
}</pre>
</div>
<ol dir="auto" start="3">
<li>Create an additional safe property on the object that does what you want instead of having a private value that's effectively overriden.</li>
</ol>
<div class="highlight highlight-source-kotlin">
<pre><span class="pl-k">data class</span> <span class="pl-en">Test</span>(<span class="pl-k">val</span> <span class="pl-smi">value</span><span class="pl-k">:</span> <span class="pl-c1">Int</span>) {
  <span class="pl-k">val</span> safeValue<span class="pl-k">:</span> <span class="pl-c1">Int</span>
    get() <span class="pl-k">=</span> <span class="pl-k">if</span> (value <span class="pl-k">&lt;</span> <span class="pl-c1">0</span>) <span class="pl-c1">0</span> <span class="pl-k">else</span> value
}</pre>
</div>
<p dir="auto"><strong>Source:</strong>&nbsp;<em>stackoverflow.com</em></p>
<h3 dir="auto"><a id="user-content-q7-what-is-kotlin-backing-field-is-used-for-" class="anchor" href="https://gist.github.com/paulfranco/4453383cc6df064d03087ce7aa5a0c8c#q7-what-is-kotlin-backing-field-is-used-for-"></a>Q7: What is Kotlin backing field is used for? ☆☆☆☆</h3>
<p dir="auto"><strong>Answer:</strong>&nbsp;Backing field is an autogenerated field for any property which can only be used inside the accessors(getter or setter) and will be present only if it uses the default implementation of at least one of the accessors, or if a custom accessor references it through the&nbsp;<code>field</code>&nbsp;identifier.&nbsp;<em>This backing field is used to avoid the recursive call of an accessor which ultimately prevents the StackOverflowError.</em></p>
<p dir="auto">Classes in Kotlin cannot have&nbsp;<strong>fields</strong>. However, sometimes it is necessary to have a backing field when using custom accessors. For these purposes, Kotlin provides an automatic backing field which can be accessed using the field identifier.</p>
<div class="highlight highlight-source-kotlin">
<pre><span class="pl-k">var</span> selectedColor<span class="pl-k">:</span> <span class="pl-c1">Int</span> <span class="pl-k">=</span> someDefaultValue
        get() <span class="pl-k">=</span> field
        set(value) {
            field <span class="pl-k">=</span> value
        }</pre>
</div>
<p dir="auto"><strong>Source:</strong>&nbsp;<em>stackoverflow.com</em></p>
<h3 dir="auto"><a id="user-content-q8-what-are-object-expressions-in-kotlin-and-when-to-use-them-" class="anchor" href="https://gist.github.com/paulfranco/4453383cc6df064d03087ce7aa5a0c8c#q8-what-are-object-expressions-in-kotlin-and-when-to-use-them-"></a>Q8: What are Object expressions in Kotlin and when to use them? ☆☆☆☆</h3>
<p dir="auto"><strong>Answer:</strong>&nbsp;Sometimes we need to create an object of some class with slight modification, without explicitly declaring a new subclass for it. Java handles this case with anonymous inner classes. Kotlin uses&nbsp;<strong>object expression</strong>&nbsp;to achieve the same functionality. We can even create an object expression for an interface or abstract class by just implementing their abstract methods.</p>
<p dir="auto">It is often used as a substitution to a Java anonymous class:</p>
<div class="highlight highlight-source-kotlin">
<pre>window.addMouseListener(<span class="pl-k">object</span> <span class="pl-k">:</span> <span class="pl-en">MouseAdapter</span>() {
    <span class="pl-k">override</span> <span class="pl-k">fun</span> <span class="pl-en">mouseClicked</span>(<span class="pl-smi">e</span><span class="pl-k">:</span> <span class="pl-en">MouseEvent</span>) {
        <span class="pl-c"><span class="pl-c">//</span> ...</span>
    }

    <span class="pl-k">override</span> <span class="pl-k">fun</span> <span class="pl-en">mouseEntered</span>(<span class="pl-smi">e</span><span class="pl-k">:</span> <span class="pl-en">MouseEvent</span>) {
        <span class="pl-c"><span class="pl-c">//</span> ...</span>
    }
})</pre>
</div>
<p dir="auto"><strong>Source:</strong>&nbsp;<em>kotlinlang.org</em></p>
<h3 dir="auto"><a id="user-content-q9-how-to-create-empty-constructor-for-data-class-in-kotlin-" class="anchor" href="https://gist.github.com/paulfranco/4453383cc6df064d03087ce7aa5a0c8c#q9-how-to-create-empty-constructor-for-data-class-in-kotlin-"></a>Q9: How to create empty constructor for data class in Kotlin? ☆☆☆☆</h3>
<p dir="auto"><strong>Answer:</strong>&nbsp;If you give&nbsp;<strong>default values to all the fields</strong>&nbsp;- empty constructor is generated automatically by Kotlin.</p>
<div class="highlight highlight-source-kotlin">
<pre><span class="pl-k">data class</span> <span class="pl-en">User</span>(<span class="pl-k">var</span> <span class="pl-smi">id</span><span class="pl-k">:</span> <span class="pl-c1">Long</span> = -1,
               <span class="pl-k">var</span> <span class="pl-smi">uniqueIdentifier</span><span class="pl-k">:</span> <span class="pl-c1">String?</span> = null)</pre>
</div>
<p dir="auto">and you can simply call:</p>
<div class="highlight highlight-source-kotlin">
<pre><span class="pl-k">val</span> user <span class="pl-k">=</span> <span class="pl-en">User</span>()</pre>
</div>
<p dir="auto">Another option is to declare a secondary constructor that has no parameters:</p>
<div class="highlight highlight-source-kotlin">
<pre><span class="pl-k">data class</span> <span class="pl-en">User</span>(<span class="pl-k">var</span> <span class="pl-smi">id</span><span class="pl-k">:</span> <span class="pl-c1">Long</span>,
               <span class="pl-k">var</span> <span class="pl-smi">uniqueIdentifier</span><span class="pl-k">:</span> <span class="pl-c1">String?</span>){
    <span class="pl-en">constructor</span>() <span class="pl-k">:</span> <span class="pl-c1">this</span>(<span class="pl-k">-</span><span class="pl-c1">1</span>, <span class="pl-c1">null</span>)
}</pre>
</div>
<p dir="auto"><strong>Source:</strong>&nbsp;<em>stackoverflow.com</em></p>
<h3 dir="auto"><a id="user-content-q10-how-to-create-an-instance-of-anonymous-class-of-abstract-class-in-kotlin-" class="anchor" href="https://gist.github.com/paulfranco/4453383cc6df064d03087ce7aa5a0c8c#q10-how-to-create-an-instance-of-anonymous-class-of-abstract-class-in-kotlin-"></a>Q10: How to create an instance of anonymous class of abstract class in Kotlin? ☆☆☆☆</h3>
<p dir="auto"><strong>Details:</strong>&nbsp;Assume that&nbsp;<code>KeyAdapter</code>&nbsp;is an abstract class with several methods that can be overridden.</p>
<p dir="auto">In java I can do:</p>
<div class="highlight highlight-source-kotlin">
<pre><span class="pl-en">KeyListener</span> keyListener <span class="pl-k">=</span> new <span class="pl-en">KeyAdapter</span>() {
    @Override <span class="pl-k">public</span> void keyPressed(<span class="pl-en">KeyEvent</span> keyEvent) {
        <span class="pl-c"><span class="pl-c">//</span> ...</span>
    }
};</pre>
</div>
<p dir="auto">How to do the same in Kotlin?</p>
<p dir="auto"><strong>Answer:</strong>&nbsp;Sometimes we need to create an object of a slight modification of some class, without explicitly declaring a new subclass for it. Kotlin handles this case with&nbsp;<em>object expressions</em>&nbsp;and&nbsp;<em>object declarations</em>.</p>
<div class="highlight highlight-source-kotlin">
<pre><span class="pl-k">val</span> keyListener <span class="pl-k">=</span> <span class="pl-k">object</span> <span class="pl-k">:</span> <span class="pl-en">KeyAdapter</span>() { 
    <span class="pl-k">override</span> <span class="pl-k">fun</span> <span class="pl-en">keyPressed</span>(<span class="pl-smi">keyEvent</span> <span class="pl-k">:</span> <span class="pl-en">KeyEvent</span>) { 
    <span class="pl-c"><span class="pl-c">//</span> ... </span>
} </pre>
</div>
<p dir="auto"><strong>Source:</strong>&nbsp;<em>stackoverflow.com</em></p>
<h3 dir="auto"><a id="user-content-q11-why-do-we-use-companion-object-as-a-kind-of-replacement-for-java-static-fields-in-kotlin-" class="anchor" href="https://gist.github.com/paulfranco/4453383cc6df064d03087ce7aa5a0c8c#q11-why-do-we-use-companion-object-as-a-kind-of-replacement-for-java-static-fields-in-kotlin-"></a>Q11: Why do we use &ldquo;companion object&rdquo; as a kind of replacement for Java static fields in Kotlin? ☆☆☆☆☆</h3>
<p dir="auto"><strong>Answer:</strong>&nbsp;Because&nbsp;<code>static</code>s are not object-oriented. Kotlin does, however, have globals, which function similarly, and objects, which provide static functionality but remain object-oriented.</p>
<p dir="auto">Java&nbsp;<code>static</code>&nbsp;part of a class can be elegantly expressed in terms of singleton: it's a singleton object that can be called by the class' name. Hence the naming: it's an object that comes with a class.</p>
<p dir="auto">Apart from naming, it is more powerful than Java static members: it can extend classes and interfaces, and you can reference and pass it around just like other objects.</p>
<p dir="auto"><strong>Source:</strong>&nbsp;<em>stackoverflow.com</em></p>
<h3 dir="auto"><a id="user-content-q12-what-is-the-difference-between--and-any-in-kotlin-generics-" class="anchor" href="https://gist.github.com/paulfranco/4453383cc6df064d03087ce7aa5a0c8c#q12-what-is-the-difference-between--and-any-in-kotlin-generics-"></a>Q12: What is the difference between &ldquo;*&rdquo; and &ldquo;Any&rdquo; in Kotlin generics? ☆☆☆☆☆</h3>
<p dir="auto"><strong>Answer:</strong></p>
<ul dir="auto">
<li><code>List&lt;*&gt;</code>&nbsp;can contain objects of any type, but&nbsp;<em>only that type</em>, so it can contain&nbsp;<code>Strings</code>&nbsp;(but only&nbsp;<code>Strings</code>)</li>
<li>while&nbsp;<code>List&lt;Any&gt;</code>&nbsp;can contain&nbsp;<code>Strings</code>&nbsp;and&nbsp;<code>Integers</code>&nbsp;and whatnot, all in the same list</li>
</ul>
<p dir="auto"><strong>Source:</strong>&nbsp;<em>stackoverflow.com</em></p>
<h3 dir="auto"><a id="user-content-q13-how-can-i-create-static-method-for-enum-in-kotiln-" class="anchor" href="https://gist.github.com/paulfranco/4453383cc6df064d03087ce7aa5a0c8c#q13-how-can-i-create-static-method-for-enum-in-kotiln-"></a>Q13: How can I create &ldquo;static&rdquo; method for enum in Kotiln? ☆☆☆☆</h3>
<p dir="auto"><strong>Answer:</strong>&nbsp;Just like with any other class, you can define a class object in an enum class:</p>
<div class="highlight highlight-source-kotlin">
<pre><span class="pl-k">enum</span> <span class="pl-k">class</span> <span class="pl-en">CircleType</span> {
  <span class="pl-en">FIRST</span>,
  <span class="pl-en">SECOND</span>,
  <span class="pl-en">THIRD</span>;
  <span class="pl-k">companion</span> <span class="pl-k">object</span> {
     <span class="pl-k">fun</span> <span class="pl-en">random</span>(): <span class="pl-en">CircleType</span> <span class="pl-k">=</span> <span class="pl-en">FIRST</span>
  }
}</pre>
</div>
<p dir="auto">Then you'll be able to call this function as&nbsp;<code>CircleType.random()</code>.</p>
<p dir="auto"><strong>Source:</strong>&nbsp;<em>stackoverflow.com</em></p>
<h3 dir="auto"><a id="user-content-q14-what-is-sam-conversion-in-kotlin-" class="anchor" href="https://gist.github.com/paulfranco/4453383cc6df064d03087ce7aa5a0c8c#q14-what-is-sam-conversion-in-kotlin-"></a>Q14: What is SAM Conversion in Kotlin? ☆☆☆☆☆</h3>
<p dir="auto"><strong>Answer:</strong>&nbsp;"SAM" stands for "single abstract method", and "SAM-type" refers to interfaces like Runnable, Callable.</p>
<p dir="auto">Just like Java 8, Kotlin supports SAM conversions. This means that Kotlin function literals can be automatically converted into implementations of Java interfaces with a single non-default method, as long as the parameter types of the interface method match the parameter types of the Kotlin function.</p>
<p dir="auto">That means that when you call some Java method from Kotlin, and that method satisfies conditions described above, you can pass lambda or method reference instead.</p>
<p dir="auto"><strong>Source:</strong>&nbsp;<em>kotlinlang.org</em></p>
<h3 dir="auto"><a id="user-content-q15-explain-the-difference-between-lateinit-and-lazy-in-details-" class="anchor" href="https://gist.github.com/paulfranco/4453383cc6df064d03087ce7aa5a0c8c#q15-explain-the-difference-between-lateinit-and-lazy-in-details-"></a>Q15: Explain the difference between lateinit and lazy in details ☆☆☆☆☆</h3>
<p dir="auto"><strong>Answer:</strong>&nbsp;Here are the significant differences between&nbsp;<code>lateinit var</code>&nbsp;and&nbsp;<code>by lazy { ... }</code>&nbsp;delegated property:</p>
<ul dir="auto">
<li>
<p dir="auto"><code>lazy { ... }</code>&nbsp;delegate can only be used for&nbsp;<code>val</code>&nbsp;properties, whereas&nbsp;<code>lateinit</code>&nbsp;can only be applied to&nbsp;<code>var</code>s, because it can't be compiled to a&nbsp;<code>final</code>&nbsp;field, thus no immutability can be guaranteed;</p>
</li>
<li>
<p dir="auto"><code>lateinit var</code>&nbsp;has a backing field which stores the value, and&nbsp;<code>by lazy { ... }</code>&nbsp;creates a delegate object in which the value is stored once calculated, stores the reference to the delegate instance in the class object and generates the getter for the property that works with the delegate instance. So if you need the backing field present in the class, use&nbsp;<code>lateinit</code>;</p>
</li>
<li>
<p dir="auto">In addition to&nbsp;<code>val</code>s,&nbsp;<code>lateinit</code>&nbsp;cannot be used for nullable properties and Java primitive types (this is because of&nbsp;<code>null</code>&nbsp;used for uninitialized value);</p>
</li>
<li>
<p dir="auto"><code>lateinit var</code>&nbsp;can be initialized from anywhere the object is seen from, e.g. from inside a framework code, and multiple initialization scenarios are possible for different objects of a single class.&nbsp;<code>by lazy { ... }</code>, in turn, defines the only initializer for the property, which can be altered only by overriding the property in a subclass. If you want your property to be initialized from outside in a way probably unknown beforehand, use&nbsp;<code>lateinit</code>.</p>
</li>
<li>
<p dir="auto">Initialization&nbsp;<code>by lazy { ... }</code>&nbsp;is thread-safe by default and guarantees that the initializer is invoked at most once (but this can be altered by using [another&nbsp;<code>lazy</code>&nbsp;overload][1]). In the case of&nbsp;<code>lateinit var</code>, it's up to the user's code to initialize the property correctly in multi-threaded environments.</p>
</li>
<li>
<p dir="auto">A&nbsp;<code>Lazy</code>&nbsp;instance can be saved, passed around and even used for multiple properties. On contrary,&nbsp;<code>lateinit var</code>s do not store any additional runtime state (only&nbsp;<code>null</code>&nbsp;in the field for uninitialized value).</p>
</li>
<li>
<p dir="auto">If you hold a reference to an instance of&nbsp;<code>Lazy</code>, [<code>isInitialized()</code>][2] allows you to check whether it has already been initialized (and you can [obtain such instance with reflection][3] from a delegated property). To check whether a lateinit property has been initialized, you can [use&nbsp;<code>property::isInitialized</code>&nbsp;since Kotlin 1.2][4].</p>
</li>
<li>
<p dir="auto">A lambda passed to&nbsp;<code>by lazy { ... }</code>&nbsp;may capture references from the context where it is used into its [closure][5].. It will then store the references and release them only once the property has been initialized. This may lead to object hierarchies, such as Android activities, not being released for too long (or ever, if the property remains accessible and is never accessed), so you should be careful about what you use inside the initializer lambda.</p>
</li>
</ul>
<p dir="auto"><strong>Source:</strong>&nbsp;<em>stackoverflow.com</em></p>
<h3 dir="auto"><a id="user-content-q16-provide-a-real-use-case-when-inline-classes-may-be-useful-" class="anchor" href="https://gist.github.com/paulfranco/4453383cc6df064d03087ce7aa5a0c8c#q16-provide-a-real-use-case-when-inline-classes-may-be-useful-"></a>Q16: Provide a real use case when inline classes may be useful ☆☆☆☆</h3>
<p dir="auto"><strong>Answer:</strong>&nbsp;Imagine an authentication method in an API that looks as follows:</p>
<div class="highlight highlight-source-kotlin">
<pre><span class="pl-k">fun</span> <span class="pl-en">auth</span>(<span class="pl-smi">userName</span><span class="pl-k">:</span> <span class="pl-c1">String</span>, <span class="pl-smi">password</span><span class="pl-k">:</span> <span class="pl-c1">String</span>) { <span class="pl-c1">println</span>(<span class="pl-s"><span class="pl-pds">"</span>authenticating <span class="pl-e">$userName</span>.<span class="pl-pds">"</span></span>) }</pre>
</div>
<p dir="auto">Since both parameters are of type String, you may mess up their order which gets even more likely with an increasing number of arguments.</p>
<p dir="auto">Inline class wrappers around these types can help you mitigate that risk and give you simple, type-safe wrappers without introducing additional heap allocations:</p>
<div class="highlight highlight-source-kotlin">
<pre><span class="pl-k">inline</span> <span class="pl-k">class</span> <span class="pl-en">Password</span>(<span class="pl-k">val</span> <span class="pl-smi">value</span><span class="pl-k">:</span> <span class="pl-c1">String</span>)
<span class="pl-k">inline</span> <span class="pl-k">class</span> <span class="pl-en">UserName</span>(<span class="pl-k">val</span> <span class="pl-smi">value</span><span class="pl-k">:</span> <span class="pl-c1">String</span>)

<span class="pl-k">fun</span> <span class="pl-en">auth</span>(<span class="pl-smi">userName</span><span class="pl-k">:</span> <span class="pl-en">UserName</span>, <span class="pl-smi">password</span><span class="pl-k">:</span> <span class="pl-en">Password</span>) { <span class="pl-c1">println</span>(<span class="pl-s"><span class="pl-pds">"</span>authenticating <span class="pl-e">$userName</span>.<span class="pl-pds">"</span></span>)}

<span class="pl-k">fun</span> <span class="pl-en">main</span>() {
    auth(<span class="pl-en">UserName</span>(<span class="pl-s"><span class="pl-pds">"</span>user1<span class="pl-pds">"</span></span>), <span class="pl-en">Password</span>(<span class="pl-s"><span class="pl-pds">"</span>12345<span class="pl-pds">"</span></span>))
    <span class="pl-c"><span class="pl-c">//</span>does not compile due to type mismatch</span>
    auth(<span class="pl-en">Password</span>(<span class="pl-s"><span class="pl-pds">"</span>12345<span class="pl-pds">"</span></span>), <span class="pl-en">UserName</span>(<span class="pl-s"><span class="pl-pds">"</span>user1<span class="pl-pds">"</span></span>))
}</pre>
</div>
<p dir="auto"><strong>Source:</strong>&nbsp;<em>kotlinexpertise.com</em></p>
<h3 dir="auto"><a id="user-content-q17-whats-wrong-with-that-code-" class="anchor" href="https://gist.github.com/paulfranco/4453383cc6df064d03087ce7aa5a0c8c#q17-whats-wrong-with-that-code-"></a>Q17: What's wrong with that code? ☆☆☆☆☆</h3>
<p dir="auto"><strong>Details:</strong>&nbsp;Let's say I want to override the Int getter so that it returns 0 if the value negative for the data class. What's bad with that approach?</p>
<div class="highlight highlight-source-kotlin">
<pre><span class="pl-k">data class</span> <span class="pl-en">Test</span>(<span class="pl-k">private</span> <span class="pl-k">val</span> <span class="pl-smi">_value</span><span class="pl-k">:</span> <span class="pl-c1">Int</span>) {
  <span class="pl-k">val</span> value<span class="pl-k">:</span> <span class="pl-c1">Int</span>
    get() <span class="pl-k">=</span> <span class="pl-k">if</span> (<span class="pl-en">_value</span> <span class="pl-k">&lt;</span> <span class="pl-c1">0</span>) <span class="pl-c1">0</span> <span class="pl-k">else</span> <span class="pl-en">_value</span>
}</pre>
</div>
<p dir="auto"><strong>Answer:</strong>&nbsp;The problem with this approach is that data classes aren't really meant for altering data like this. They are really just for&nbsp;<em>holding</em>&nbsp;data. Overriding the getter for a data class like this would mean that&nbsp;<code>Test(0)</code>&nbsp;and&nbsp;<code>Test(-1)</code>&nbsp;wouldn't equal one another and would have different&nbsp;<code>hashCodes</code>, but when you called&nbsp;<code>.value</code>, they would have the same result. This is inconsistent, and while it may work for you, other people on your team who see this is a data class, may accidentally misuse it.</p>
<p dir="auto"><strong>Source:</strong>&nbsp;<em>stackoverflow.com</em></p>
<h3 dir="auto"><a id="user-content-q18-why-would-you-use-apply-in-kotlin-" class="anchor" href="https://gist.github.com/paulfranco/4453383cc6df064d03087ce7aa5a0c8c#q18-why-would-you-use-apply-in-kotlin-"></a>Q18: Why would you use apply in Kotlin? ☆☆☆</h3>
<p dir="auto"><strong>Answer:</strong>&nbsp;Look at this code:</p>
<div class="highlight highlight-source-kotlin">
<pre>person.name <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">"</span>Tony Stark<span class="pl-pds">"</span></span>
person.age <span class="pl-k">=</span> <span class="pl-c1">52</span></pre>
</div>
<p dir="auto">and equivalent with apply will be:</p>
<div class="highlight highlight-source-kotlin">
<pre><span class="pl-k">val</span> person <span class="pl-k">=</span> <span class="pl-en">Person</span>().<span class="pl-c1">apply</span> {
    name <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">"</span>Tony Stark<span class="pl-pds">"</span></span> <span class="pl-c"><span class="pl-c">//</span> this. can be omitted</span>
    age <span class="pl-k">=</span> <span class="pl-c1">52</span> <span class="pl-c"><span class="pl-c">//</span> this. can be omitted</span>
    <span class="pl-c"><span class="pl-c">//</span> ...</span>
}</pre>
</div>
<p dir="auto">This way you don't have to repeat person several times. Apply is used to keep things that belong together in one place (mostly initializations).</p>
<p dir="auto"><strong>Source:</strong>&nbsp;<em>stackoverflow.com</em></p>
<h3 dir="auto"><a id="user-content-q19-rewrite-this-code-using-run-extension-function--" class="anchor" href="https://gist.github.com/paulfranco/4453383cc6df064d03087ce7aa5a0c8c#q19-rewrite-this-code-using-run-extension-function--"></a>Q19: Rewrite this code using "run" extension function ☆☆☆☆</h3>
<p dir="auto"><strong>Details:</strong>&nbsp;Consider:</p>
<div class="highlight highlight-source-kotlin">
<pre><span class="pl-k">val</span> generator <span class="pl-k">=</span> <span class="pl-en">PasswordGenerator</span>()
generator.seed <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">"</span>someString<span class="pl-pds">"</span></span>
generator.hash <span class="pl-k">=</span> {s <span class="pl-k">-&gt;</span> someHash(s)}
generator.hashRepititions <span class="pl-k">=</span> <span class="pl-c1">1000</span>

<span class="pl-k">val</span> password<span class="pl-k">:</span> <span class="pl-en">Password</span> <span class="pl-k">=</span> generator.generate()</pre>
</div>
<p dir="auto">How would you refactor this code using&nbsp;<code>run</code>&nbsp;extension function?</p>
<p dir="auto"><strong>Answer:</strong>&nbsp;Someone didn&rsquo;t quite think through the design of this password generator class. Its constructor does nothing, but it needs a lot of initialization. To use this class, I need to introduce a variable generator, set all necessary parameters and use&nbsp;<code>generate</code>&nbsp;to generate the actual password.</p>
<div class="highlight highlight-source-kotlin">
<pre><span class="pl-k">val</span> password<span class="pl-k">:</span> <span class="pl-en">Password</span> <span class="pl-k">=</span> <span class="pl-en">PasswordGenerator</span>().<span class="pl-c1">run</span> {
       seed <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">"</span>someString<span class="pl-pds">"</span></span>
       hash <span class="pl-k">=</span> {s <span class="pl-k">-&gt;</span> someHash(s)}
       hashRepetitions <span class="pl-k">=</span> <span class="pl-c1">1000</span>

       generate()
}</pre>
</div>
<p dir="auto">Lambdas in Kotlin implicitly return the result of the last line. That&rsquo;s why I can omit the temporary variable and store the password directly. Because an extension function is passed to&nbsp;<code>run</code>&nbsp;I can also access the password generator&rsquo;s properties like&nbsp;<code>seed</code>&nbsp;or&nbsp;<code>hash</code>&nbsp;directly.</p>
<p dir="auto"><strong>Source:</strong>&nbsp;<em>stackoverflow.com</em></p>
<h3 dir="auto"><a id="user-content-q20-how-would-you-refactor-this-code-using-apply-" class="anchor" href="https://gist.github.com/paulfranco/4453383cc6df064d03087ce7aa5a0c8c#q20-how-would-you-refactor-this-code-using-apply-"></a>Q20: How would you refactor this code using "apply"? ☆☆☆</h3>
<p dir="auto"><strong>Details:</strong>&nbsp;Consider:</p>
<div class="highlight highlight-source-kotlin">
<pre><span class="pl-k">class</span> <span class="pl-en">Message</span>(<span class="pl-smi">message</span><span class="pl-k">:</span> <span class="pl-c1">String</span>, <span class="pl-smi">signature</span><span class="pl-k">:</span> <span class="pl-c1">String</span>) {
  <span class="pl-k">val</span> body <span class="pl-k">=</span> <span class="pl-en">MessageBody</span>()
  
  <span class="pl-en">init</span> {
    body.text <span class="pl-k">=</span> message <span class="pl-k">+</span> <span class="pl-s"><span class="pl-pds">"</span><span class="pl-cce">\n</span><span class="pl-pds">"</span></span> <span class="pl-k">+</span> signature
  }
}</pre>
</div>
<p dir="auto">Do you see any refactoring that could be done?</p>
<p dir="auto"><strong>Answer:</strong>&nbsp;You can write:</p>
<div class="highlight highlight-source-kotlin">
<pre><span class="pl-k">class</span> <span class="pl-en">Message</span>(<span class="pl-smi">message</span><span class="pl-k">:</span> <span class="pl-c1">String</span>, <span class="pl-smi">signature</span><span class="pl-k">:</span> <span class="pl-c1">String</span>) {
  <span class="pl-k">val</span> body <span class="pl-k">=</span> <span class="pl-en">MessageBody</span>().<span class="pl-c1">apply</span> {
    text <span class="pl-k">=</span> message <span class="pl-k">+</span> <span class="pl-s"><span class="pl-pds">"</span><span class="pl-cce">\n</span><span class="pl-pds">"</span></span> <span class="pl-k">+</span> signature
  }
}</pre>
</div>
<p dir="auto"><strong>Source:</strong>&nbsp;<em>cargocult.dev</em></p>
<h3 dir="auto"><a id="user-content-q1-what-is-the-billion-dollar-mistake-" class="anchor" href="https://gist.github.com/paulfranco/4453383cc6df064d03087ce7aa5a0c8c#q1-what-is-the-billion-dollar-mistake-"></a>Q1: What is The Billion Dollar Mistake? ☆☆☆☆☆</h3>
<p dir="auto"><strong>Answer:</strong>&nbsp;Kotlin's type system is aimed at eliminating the danger of null references from code, also known as the The Billion Dollar Mistake.</p>
<p dir="auto">One of the most common pitfalls in many programming languages, including Java, is that accessing a member of a null reference will result in a null reference exception. In Kotlin, the type system distinguishes between references that can hold null (nullable references) and those that can not (non-null references).</p>
<p dir="auto"><em>I call it my billion-dollar mistake. It was the invention of the&nbsp;<strong>null reference</strong>&nbsp;in 1965. At that time, I was designing the first comprehensive type system for references in an object-oriented language (ALGOL W). My goal was to ensure that all use of references should be absolutely safe, with checking performed automatically by the compiler. But I couldn&rsquo;t resist the temptation to put in a null reference, simply because it was so easy to implement. This has led to innumerable errors, vulnerabilities, and system crashes, which have probably caused a billion dollars of pain and damage in the last forty years.</em></p>
<p dir="auto">Tony Hoare at QCon London in 2009&nbsp;<a href="https://en.wikipedia.org/wiki/Tony_Hoare" rel="nofollow">https://en.wikipedia.org/wiki/Tony_Hoare</a></p>
<p dir="auto"><strong>Source:</strong>&nbsp;<em>kotlinlang.org</em></p>
<h3 dir="auto"><a id="user-content-q2-what-is-a-motivation-to-make-classes-final-by-default-in-kotlin-do-you-agree-with-that-decision-" class="anchor" href="https://gist.github.com/paulfranco/4453383cc6df064d03087ce7aa5a0c8c#q2-what-is-a-motivation-to-make-classes-final-by-default-in-kotlin-do-you-agree-with-that-decision-"></a>Q2: What is a motivation to make classes final by default in Kotlin? Do you agree with that decision? ☆☆☆☆☆</h3>
<p dir="auto"><strong>Answer:</strong></p>
<ul dir="auto">
<li>
<p dir="auto">First Kotlin takes many ideas from the functional programming world and uses immutability as often as it can to avoid all the known problems with mutation. Also proper designing a class for inheritance requires an excruciating amount of work (and building at least 3 separate subclasses, to verify that you base class actually is useful). Most classes should be final. Extending them is probably a bad idea.</p>
</li>
<li>
<p dir="auto">The second thought which comes to my mind is that inheritance is often missused. There is the principle "Favor composition over inheritance" as a guideline for better designs. So declaring every class as final by default forces the developer to at least stop for a moment and think about alternative ways to solve the problem instead of using inheritance for the wrong reasons.</p>
</li>
</ul>
<p dir="auto"><strong>Source:</strong>&nbsp;<em>stackoverflow.com</em></p>
<h3 dir="auto"><a id="user-content-q3-how-does-the-reified-keyword-in-kotlin-work-" class="anchor" href="https://gist.github.com/paulfranco/4453383cc6df064d03087ce7aa5a0c8c#q3-how-does-the-reified-keyword-in-kotlin-work-"></a>Q3: How does the reified keyword in Kotlin work? ☆☆☆☆☆</h3>
<p dir="auto"><strong>Answer:</strong>&nbsp;In an ordinary generic function like&nbsp;<code>myGenericFun</code>, you can't access the type&nbsp;<code>T</code>&nbsp;because it is, like in Java, erased at runtime and thus only available at compile time. Therefore, if you want to use the generic type as a normal&nbsp;<code>Class</code>&nbsp;in the function body you need to explicitly pass the class as a parameter like the parameter&nbsp;<code>c</code>&nbsp;in the example.</p>
<div class="highlight highlight-source-kotlin">
<pre><span class="pl-k">fun</span> &lt;<span class="pl-en">T</span>&gt; <span class="pl-en">myGenericFun</span>(<span class="pl-smi">c</span><span class="pl-k">:</span> <span class="pl-en">Class</span>&lt;<span class="pl-en">T</span>&gt;)</pre>
</div>
<p dir="auto">By marking a type as&nbsp;<code>reified</code>, we&rsquo;ll have the ability to use that type within the function.</p>
<p dir="auto">As for a real example, in Java, when we call&nbsp;<code>startActivity</code>, we need to specify the destination class as a parameter. The Kotlin way is:</p>
<div class="highlight highlight-source-kotlin">
<pre><span class="pl-k">inline</span> <span class="pl-k">fun</span> &lt;<span class="pl-en">reified</span> <span class="pl-en">T</span> : <span class="pl-en">Activity</span>&gt; Activity.<span class="pl-en">startActivity</span>() {
    startActivity(<span class="pl-en">Intent</span>(<span class="pl-c1">this</span>, <span class="pl-en">T</span>::<span class="pl-c1">class</span>.java))
}</pre>
</div>
<p dir="auto">You can only use&nbsp;<code>reified</code>&nbsp;in combination with an&nbsp;<em>inline function</em>. Such a function makes the compiler&nbsp;<em>copy the function's bytecode to every place where the function is being used</em>&nbsp;(the function is being "inlined"). When you call an inline function with reified type, the&nbsp;<em>compiler knows</em>&nbsp;the actual type used as a type argument and modifies the generated bytecode to use the corresponding class directly. Therefore calls like&nbsp;<code>myVar is T</code>&nbsp;become&nbsp;<code>myVar is String</code>&nbsp;(if the type argument were&nbsp;<code>String</code>) in the bytecode and at runtime.</p>
<p dir="auto"><strong>Source:</strong>&nbsp;<em>stackoverflow.com</em></p>
<h3 dir="auto"><a id="user-content-q4-how-to-implement-builder-pattern-in-kotlin-" class="anchor" href="https://gist.github.com/paulfranco/4453383cc6df064d03087ce7aa5a0c8c#q4-how-to-implement-builder-pattern-in-kotlin-"></a>Q4: How to implement Builder pattern in Kotlin? ☆☆☆☆☆</h3>
<p dir="auto"><strong>Answer:</strong>&nbsp;First and foremost, in most cases you don't need to use builders in Kotlin because we have default and named arguments but if you need one use:</p>
<div class="highlight highlight-source-kotlin">
<pre><span class="pl-k">class</span> <span class="pl-en">Car</span>( <span class="pl-c"><span class="pl-c">//</span>add private constructor if necessary</span>
        <span class="pl-k">val</span> <span class="pl-smi">model</span><span class="pl-k">:</span> <span class="pl-c1">String?</span>,
        <span class="pl-k">val</span> <span class="pl-smi">year</span><span class="pl-k">:</span> <span class="pl-c1">Int</span>
) {

    <span class="pl-k">private</span> <span class="pl-en">constructor</span>(builder<span class="pl-k">:</span> <span class="pl-en">Builder</span>) <span class="pl-k">:</span> <span class="pl-c1">this</span>(builder.model, builder.year)

    <span class="pl-k">class</span> <span class="pl-en">Builder</span> {
        <span class="pl-k">var</span> model<span class="pl-k">:</span> <span class="pl-c1">String?</span> <span class="pl-k">=</span> <span class="pl-c1">null</span>
            <span class="pl-k">private</span> set

        <span class="pl-k">var</span> year<span class="pl-k">:</span> <span class="pl-c1">Int</span> <span class="pl-k">=</span> <span class="pl-c1">0</span>
            <span class="pl-k">private</span> set

        <span class="pl-k">fun</span> <span class="pl-en">model</span>(<span class="pl-smi">model</span><span class="pl-k">:</span> <span class="pl-c1">String</span>) <span class="pl-k">=</span> <span class="pl-c1">apply</span> { <span class="pl-c1">this</span>.model <span class="pl-k">=</span> model }

        <span class="pl-k">fun</span> <span class="pl-en">year</span>(<span class="pl-smi">year</span><span class="pl-k">:</span> <span class="pl-c1">Int</span>) <span class="pl-k">=</span> <span class="pl-c1">apply</span> { <span class="pl-c1">this</span>.year <span class="pl-k">=</span> year }

        <span class="pl-k">fun</span> <span class="pl-en">build</span>() <span class="pl-k">=</span> <span class="pl-en">Car</span>(<span class="pl-c1">this</span>)
    }
}</pre>
</div>
<p dir="auto">Usage:</p>
<div class="highlight highlight-source-kotlin">
<pre><span class="pl-k">val</span> car <span class="pl-k">=</span> <span class="pl-en">Car</span>.<span class="pl-en">Builder</span>().model(<span class="pl-s"><span class="pl-pds">"</span>X<span class="pl-pds">"</span></span>).build()</pre>
</div>
<p dir="auto"><strong>Source:</strong>&nbsp;<em>stackoverflow.com</em></p>
<h3 dir="auto"><a id="user-content-q5-when-to-use-and-do-not-use-an-inline-function-in-kotlin-" class="anchor" href="https://gist.github.com/paulfranco/4453383cc6df064d03087ce7aa5a0c8c#q5-when-to-use-and-do-not-use-an-inline-function-in-kotlin-"></a>Q5: When to use and do not use an inline function in Kotlin? ☆☆☆☆☆</h3>
<p dir="auto"><strong>Answer:</strong>&nbsp;Using higher-order functions imposes certain runtime penalties: each function is an object, and it captures a closure, i.e. those variables that are accessed in the body of the function. Memory allocations (both for function objects and classes) and virtual calls introduce runtime overhead.</p>
<p dir="auto">But it appears that in many cases this kind of overhead can be eliminated by&nbsp;<em>inlining the lambda expressions</em>.</p>
<p dir="auto">The&nbsp;<code>inline</code>&nbsp;modifier affects both the function itself and the lambdas passed to it: all of those will be inlined into the call site.</p>
<p dir="auto">The most important case when we use inline modifier is when we define util-like functions with parameter functions. This is why inline modifier is mostly an important optimization for library developers.</p>
<p dir="auto">Consider:</p>
<div class="highlight highlight-source-kotlin">
<pre><span class="pl-k">inline</span> <span class="pl-k">fun</span> <span class="pl-en">inlined</span>(<span class="pl-smi">block</span><span class="pl-k">:</span> () <span class="pl-k">-&gt;</span> <span class="pl-c1">Unit</span>) {
    <span class="pl-c1">println</span>(<span class="pl-s"><span class="pl-pds">"</span>before<span class="pl-pds">"</span></span>)
    block()
    <span class="pl-c1">println</span>(<span class="pl-s"><span class="pl-pds">"</span>after<span class="pl-pds">"</span></span>)
}

inlined {
    <span class="pl-c1">println</span>(<span class="pl-s"><span class="pl-pds">"</span>do something here<span class="pl-pds">"</span></span>)
}

<span class="pl-c"><span class="pl-c">//</span> No Function object instance will be created, instead, the code around the </span>
<span class="pl-c"><span class="pl-c">//</span> invocation of block inside the inlined function will be copied </span>
<span class="pl-c"><span class="pl-c">//</span> to the call site</span>
<span class="pl-en">System</span>.<span class="pl-k">out</span>.<span class="pl-c1">println</span>(<span class="pl-s"><span class="pl-pds">"</span>before<span class="pl-pds">"</span></span>);
<span class="pl-en">System</span>.<span class="pl-k">out</span>.<span class="pl-c1">println</span>(<span class="pl-s"><span class="pl-pds">"</span>do something here<span class="pl-pds">"</span></span>);
<span class="pl-en">System</span>.<span class="pl-k">out</span>.<span class="pl-c1">println</span>(<span class="pl-s"><span class="pl-pds">"</span>after<span class="pl-pds">"</span></span>);</pre>
</div>
<p dir="auto">When we don&rsquo;t have function type parameter, reified type parameter, and we don&rsquo;t need non-local return, then we most likely shouldn&rsquo;t use inline modifier.</p>
<p dir="auto">Also there is the code size problem. Inlining a large function could dramatically increase the size of the bytecode because it's copied to every calls site. Inlining may cause the generated code to grow; however, if we do it in a reasonable way (i.e. avoiding inlining large functions), it will pay off in performance.</p>
<p dir="auto"><strong>Source:</strong>&nbsp;<em>stackoverflow.com</em></p>
<h3 dir="auto"><a id="user-content-q6-how-kotlin-coroutines-are-better-than-rxkotlinrxjava-" class="anchor" href="https://gist.github.com/paulfranco/4453383cc6df064d03087ce7aa5a0c8c#q6-how-kotlin-coroutines-are-better-than-rxkotlinrxjava-"></a>Q6: How Kotlin coroutines are better than RxKotlin/RxJava? ☆☆☆☆☆</h3>
<p dir="auto"><strong>Answer:</strong>&nbsp;Kotlin coroutines are different from Rx. Both are designed to address a problem of asynchronous programming, however their approach to solution is very different:</p>
<ul dir="auto">
<li>
<p dir="auto">Rx comes with a particular functional style of programming that can be implemented in virtually any programming language without support from the language itself. It works well when the problem at hand easily decomposes into a sequence of standard operators and not so well otherwise.</p>
</li>
<li>
<p dir="auto">Kotlin coroutines provide a language feature that let library writers implement various asynchronous programming styles, including, but not limited to functional reactive style (Rx). With Kotlin coroutines you can also write your asynchronous code in imperative style, in promise/futures-based style, in actor-style, etc.</p>
</li>
</ul>
<p dir="auto">How Kotlin coroutines are better than RxKotlin? You just write sequential code, everything is as easy as writing synchronous code except it execute asynchronously. It's easier to grasp.</p>
<p dir="auto">Coroutines are better to deal with resources</p>
<ul dir="auto">
<li>In RxJava you can assign computations to schedulers but&nbsp;<code>subscribeOn()</code>&nbsp;and&nbsp;<code>ObserveOn()</code>are confusing. Every coroutine is given a thread context and return to parent context. For a channel, both side (producer, consumer) execute on his own context. Coroutines are more intuitive on thread or thread pool affectation.</li>
<li>Coroutines give more control on when those computation occur. You can for example pass hand (<code>yield</code>), prioritize (<code>select</code>), parallelize (multiple&nbsp;<code>producer</code>/<code>actor</code>&nbsp;on&nbsp;<code>channel</code>) or lock resource (<code>Mutex</code>) for a given computation. It may not matter on server (where RxJava came first) but on resources limited environment this level of control may be required.</li>
<li>Due to it's reactive nature, backpressure doesn't fit well in RxJava. In the other end&nbsp;<code>send()</code>&nbsp;to channel is a suspensive function that suspend when channel capacity is reached. It's out-of-the-box backpressure given by nature. You could also&nbsp;<code>offer()</code>&nbsp;to channel, in which case the call never suspend but return&nbsp;<code>false</code>&nbsp;in case the channel is full, effectively reproducing&nbsp;<code>onBackpressureDrop()</code>&nbsp;from RxJava. Or you could just write your own custom backpressure logic, which won't be difficult with coroutines, especially compared to do the same with RxJava.</li>
</ul>
<p dir="auto"><strong>Source:</strong>&nbsp;<em>stackoverflow.com</em></p>
<h3 dir="auto"><a id="user-content-q7-what-is-the-difference-between-launchjoin-and-asyncawait-in-kotlin-coroutines-" class="anchor" href="https://gist.github.com/paulfranco/4453383cc6df064d03087ce7aa5a0c8c#q7-what-is-the-difference-between-launchjoin-and-asyncawait-in-kotlin-coroutines-"></a>Q7: What is the difference between launch/join and async/await in Kotlin coroutines? ☆☆☆☆☆</h3>
<p dir="auto"><strong>Answer:</strong></p>
<ul dir="auto">
<li>
<p dir="auto"><strong>launch</strong>&nbsp;is used to** fire and forget coroutine**. It is like starting a new thread. If the code inside the&nbsp;<code>launch</code>&nbsp;terminates with exception, then it is treated like&nbsp;<em>uncaught</em>&nbsp;exception in a thread -- usually printed to stderr in backend JVM applications and crashes Android applications.&nbsp;<code>join</code>&nbsp;is used to wait for completion of the launched coroutine and it does not propagate its exception. However, a crashed&nbsp;<em>child</em>&nbsp;coroutine cancels its parent with the corresponding exception, too.</p>
</li>
<li>
<p dir="auto"><strong>async</strong>&nbsp;is used to&nbsp;<strong>start a coroutine that computes some result</strong>. The result is represented by an instance of&nbsp;<code>Deferred</code>&nbsp;and you&nbsp;<strong>must</strong>&nbsp;use&nbsp;<code>await</code>&nbsp;on it. An uncaught exception inside the async code is stored inside the resulting&nbsp;<code>Deferred</code>&nbsp;and is not delivered anywhere else, it will get silently dropped unless processed.&nbsp;<strong>You MUST NOT forget about the coroutine you&rsquo;ve started with async.</strong></p>
</li>
</ul>
<p dir="auto"><strong>Source:</strong>&nbsp;<em>stackoverflow.com</em></p>
<h3 dir="auto"><a id="user-content-q68-what-is-the-difference-between-java-field-and-kotlin-property-" class="anchor" href="https://gist.github.com/paulfranco/4453383cc6df064d03087ce7aa5a0c8c#q68-what-is-the-difference-between-java-field-and-kotlin-property-"></a>Q68: What is the difference between Java field and Kotlin property? ☆☆☆☆☆</h3>
<p dir="auto"><strong>Answer:</strong>&nbsp;This is an example of a Java field:</p>
<div class="highlight highlight-source-java">
<pre><span class="pl-k">public</span> <span class="pl-smi">String</span> name <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">"</span>Marcin<span class="pl-pds">"</span></span>;</pre>
</div>
<p dir="auto">Here is an example of a Kotlin property:</p>
<div class="highlight highlight-source-kotlin">
<pre><span class="pl-k">var</span> name<span class="pl-k">:</span> <span class="pl-c1">String</span> <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">"</span>Marcin<span class="pl-pds">"</span></span></pre>
</div>
<p dir="auto">They both look very similar, but these are two different concepts. Direct Java equivalent of above Kotlin property is following:</p>
<div class="highlight highlight-source-java">
<pre><span class="pl-k">private</span> <span class="pl-smi">String</span> name <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">"</span>Marcin<span class="pl-pds">"</span></span>;
<span class="pl-k">public</span> <span class="pl-smi">String</span> getName() {
    <span class="pl-k">return</span> name;
}
<span class="pl-k">public</span> <span class="pl-k">void</span> setName(<span class="pl-smi">String</span> name) {
    <span class="pl-c1">this</span><span class="pl-k">.</span>name <span class="pl-k">=</span> name;
}</pre>
</div>
<p dir="auto">The default implementation of Kotlin property includes field and accessors (getter for val, and getter and setter for var). Thanks to that, we can always replace accessors default implementation with a custom one.</p>
<p dir="auto"><strong>Source:</strong>&nbsp;<em>blog.kotlin-academy.com</em></p>
<h3 dir="auto"><a id="user-content-q69-what-is-the-difference-between-and-interface-and-an-abstract-class-" class="anchor" href="https://gist.github.com/paulfranco/4453383cc6df064d03087ce7aa5a0c8c#q69-what-is-the-difference-between-and-interface-and-an-abstract-class-"></a>Q69: What is the difference between and interface and an abstract class? ☆☆</h3>
<p dir="auto"><strong>Answer:</strong>&nbsp;Though both may seem very similar they are in fact very different and serve very different purposes. Abstract classes are meant to serve the purpose of Generalizing behavior while interfaces are meant to serve the purpose of Standardizing behavior.</p>
<p dir="auto"><strong>Source:</strong>&nbsp;<em>paulfran.co/</em></p>
</article>
</div>
</div>
</div>
</div>
</div>
</div>
<footer class="footer width-full container-lg p-responsive">
<div class="d-flex flex-justify-center pb-6">&nbsp;</div>
</footer>
