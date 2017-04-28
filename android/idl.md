From : [http://www.techrepublic.com/article/learn-the-basics-of-interface-definition-language/](http://www.techrepublic.com/article/learn-the-basics-of-interface-definition-language/)

# IDL - Interface Define/Description Language

Interface Definition Language \(IDL\) is a standard language for defining function and method interfaces for distributed or component-based applications. It's used heavily by such technologies as CORBA and COM. In most cases, the fact that you’re using IDL will be transparent to you; it’s usually integrated into the tools and development platform you work with.

However, it can be handy to have a working knowledge of IDL in case you need to work some up on your own or need to read it to understand how to use someone else’s component. \(For example, the W3C’s DOM specification documentation makes extensive use of IDL.\) If nothing else, IDL is important for historical perspective, since it could be viewed as paving the way for technologies such as SOAP and WSDL, which make Web services possible.

#### A very brief history of IDL

IDL started out as part of the Open Group’s Distributed Computing Environment \([DCE](http://www.opengroup.org/dce/info/papers/tog-dce-pd-1296.htm)\). The DCE created a standard way of carrying out remote procedure calls \(RPCs\), or calling a function across a network. This entails a process called marshalling, which involves gathering the data needed to make that function call to the remote computer.

At that time, most programmers who needed to reuse code simply compiled C header files into an application to statically link the app with the reused code. When the DCE developers began looking for ways to automatically provide the needed marshalling code for RPC, they naturally adapted these header files—which most people were creating anyway—into a format useful for this task. \(So, if you’re versed in any of the C-like language families, including Java, C++, and C\#, IDL's very C-like syntax will be familiar to you.\)

Later, when work began on dynamic component reuse standards, such as CORBA and COM, those developers looked to the work done earlier with RPC for a standard. So, IDL eventually came into widespread use as a way to define object interfaces in a language-neutral manner.

Today, there are several varieties of IDL in use: OMG/CORBA, Microsoft, and KDE-DCOP are a few of the various implementations. Vendors supporting each implementation provide compilers that convert IDL source into type libraries describing the component in question, so type checking can be done at compile time for the application using the component.

#### IDL in action

You can’t write actual programs in IDL because it lacks the logic and flow control structures you need to do anything useful with it. Instead, IDL concentrates on type definitions, both for primitive and class types, so you use it instead to define interfaces, not implementations. For example, a function used to calculate sales tax on an order might be defined like this:

```java
float  calculate_tax ( in float taxable_amount );
```

Here you have a function, calculate\_tax, that receives a single input \(by value\) parameter, taxable\_amount, of type float. The function also returns a value of type float. Notice that there is no implementation of the calculate\_tax function here; you provide that in your native language.

Function declarations are collected into interfaces, which represent all the defined methods for a class. These interfaces are defined using the standard curly braces, C-style class declaration. To extend the above example, you might include the calculate\_tax function, along with some other functions, in an order interface, like this:

```java
interface order {

    float calculate_tax ([in] float taxable_amount);

    float calculate_total([in] item_list items);

    bool place_order([in,out] item_list items);

}
```

Once you’ve defined an interface, it can be used as a parameter type for function declarations and may be extended by other interfaces using the C extension operator \(:\). In my example, I assume you’ve also created an item\_list interface, which you would use as the sole parameter of the calculate\_total and place\_order functions.

You create new non interface types using the typedef statement, which as you’d expect by now looks very similar to the format used in C. For example, I could create a new Currency type using the following typedef statement:

```java
typedef float Currency
```

#### Primitive types and attributes

The particular primitive types supported in a flavor of IDL depend somewhat upon the vendor’s implementation of the language. Usually, though, the basic types \(int, short, long, char, float, bool\) are supported. How these types translate into your chosen programming language is, once again, dependent upon the particular flavor of IDL you are using. However, common sense and a good reference to C variable types will usually carry you through.

One thing I’ve glossed over up until now is attributes. The \[in\] and \[out\] keywords preceding the function parameters in the order interface example are attributes, which indicate some special handling of the parameter they decorate. The \[in\] attribute indicates pass-by-value handling—you won’t be modifying variables decorated by the \[in\] attribute. The \[out\] attribute, on the other hand, not only indicates pass-by-reference but also specifies that the value of that parameter will not be passed to the called function. It’s a one-way return parameter.

Combining these attributes into one \[in,out\] attribute gives you a bidirectional parameter. There will be other attributes supported by the IDL variant you use.

#### For further reading

Below, I've listed some Web resources for the IDL flavors I mentioned in this article, so you can get more information if you need it.

* The Object Management Group or OMG has a brief
  [IDL information page](http://www.omg.org/gettingstarted/omg_idl.htm)
  for CORBA developers that includes links to training and other educational resources.
* Check out the documentation available on MSDN for information on
  [Microsoft Interface Definition Language](http://msdn.microsoft.com/library/default.asp?url=/library/en-us/midl/midl/midl_start_page.asp?frame=true)
  \(MIDL, Microsoft’s IDL variant for COM programmers\).



