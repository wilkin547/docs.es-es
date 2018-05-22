---
title: nameof (Referencia de C#)
ms.date: 06/16/2017
f1_keywords:
- nameof_CSharpKeyword
- nameof
ms.assetid: 33601bf3-cc2c-4496-846d-f9679bccf2a7
ms.openlocfilehash: 8a850633bee26120a12f9d72e9d18b5af131d267
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="nameof-c-reference"></a><span data-ttu-id="0d713-102">nameof (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="0d713-102">nameof (C# Reference)</span></span>

<span data-ttu-id="0d713-103">Se utiliza para obtener el nombre de cadena (incompleto) simple de una variable, tipo o miembro.</span><span class="sxs-lookup"><span data-stu-id="0d713-103">Used to obtain the simple (unqualified) string name of a variable, type, or member.</span></span>  

<span data-ttu-id="0d713-104">Al informar de errores en el código, enlazar vínculos de controlador de vistas de modelo (MVC), desencadenar eventos de propiedad cambiada, etc., a menudo le interesa capturar el nombre de cadena de un método.</span><span class="sxs-lookup"><span data-stu-id="0d713-104">When reporting errors in code, hooking up model-view-controller (MVC) links, firing property changed events, etc., you often want to capture the string name of a method.</span></span>  <span data-ttu-id="0d713-105">Usar `nameof` ayuda a lograr que su código siga siendo válido al cambiar el nombre de definiciones.</span><span class="sxs-lookup"><span data-stu-id="0d713-105">Using `nameof` helps keep your code valid when renaming definitions.</span></span>  <span data-ttu-id="0d713-106">Antes había que usar literales de cadena para hacer referencia a definiciones, lo que resulta precario al cambiar el nombre de elementos de código, ya que las herramientas no saben comprobar estos literales de cadena.</span><span class="sxs-lookup"><span data-stu-id="0d713-106">Before, you had to use string literals to refer to definitions, which is brittle when renaming code elements because tools do not know to check these string literals.</span></span>  
  
 <span data-ttu-id="0d713-107">Una expresión `nameof` tiene este formato:</span><span class="sxs-lookup"><span data-stu-id="0d713-107">A `nameof` expression has this form:</span></span>  
  
```csharp  
if (x == null) throw new ArgumentNullException(nameof(x));  
WriteLine(nameof(person.Address.ZipCode)); // prints "ZipCode"  
```  
  
## <a name="key-use-cases"></a><span data-ttu-id="0d713-108">Casos de uso clave</span><span class="sxs-lookup"><span data-stu-id="0d713-108">Key Use Cases</span></span>  
 <span data-ttu-id="0d713-109">Estos ejemplos muestran los casos de uso clave para `nameof`.</span><span class="sxs-lookup"><span data-stu-id="0d713-109">These examples show the key use cases for `nameof`.</span></span>  
  
 <span data-ttu-id="0d713-110">Validar parámetros:</span><span class="sxs-lookup"><span data-stu-id="0d713-110">Validate parameters:</span></span>  
 ```csharp  
void f(string s) {  
    if (s == null) throw new ArgumentNullException(nameof(s));  
}  
```  
  
 <span data-ttu-id="0d713-111">Vínculos de acción de MVC:</span><span class="sxs-lookup"><span data-stu-id="0d713-111">MVC Action links:</span></span>  
 ```html  
<%= Html.ActionLink("Sign up",  
             @typeof(UserController),  
             @nameof(UserController.SignUp))  
%>  
```  
  
 <span data-ttu-id="0d713-112">INotifyPropertyChanged:</span><span class="sxs-lookup"><span data-stu-id="0d713-112">INotifyPropertyChanged:</span></span>  
 ```csharp  
int p {  
    get { return this.p; }  
    set { this.p = value; PropertyChanged(this, new PropertyChangedEventArgs(nameof(this.p)); } // nameof(p) works too  
}  
```  
  
 <span data-ttu-id="0d713-113">Propiedad de dependencia de XAML:</span><span class="sxs-lookup"><span data-stu-id="0d713-113">XAML dependency property:</span></span>  
 ```csharp  
public static DependencyProperty AgeProperty = DependencyProperty.Register(nameof(Age), typeof(int), typeof(C));  
```  
  
 <span data-ttu-id="0d713-114">Registro:</span><span class="sxs-lookup"><span data-stu-id="0d713-114">Logging:</span></span>  
 ```csharp  
void f(int i) {  
    Log(nameof(f), "method entry");  
}  
```  
  
 <span data-ttu-id="0d713-115">Atributos:</span><span class="sxs-lookup"><span data-stu-id="0d713-115">Attributes:</span></span>  
 ```csharp  
[DebuggerDisplay("={" + nameof(GetString) + "()}")]  
class C {  
    string GetString() { }  
}  
```  
  
## <a name="examples"></a><span data-ttu-id="0d713-116">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="0d713-116">Examples</span></span>  
 <span data-ttu-id="0d713-117">Algunos ejemplos de C#:</span><span class="sxs-lookup"><span data-stu-id="0d713-117">Some C# examples:</span></span>  
  
```csharp  
using Stuff = Some.Cool.Functionality  
class C {  
    static int Method1 (string x, int y) {}  
    static int Method1 (string x, string y) {}  
    int Method2 (int z) {}  
    string f<T>() => nameof(T);  
}  
  
var c = new C()  
  
nameof(C) -> "C"  
nameof(C.Method1) -> "Method1"   
nameof(C.Method2) -> "Method2"  
nameof(c.Method1) -> "Method1"   
nameof(c.Method2) -> "Method2"  
nameof(z) -> "z" // inside of Method2 ok, inside Method1 is a compiler error  
nameof(Stuff) = "Stuff"  
nameof(T) -> "T" // works inside of method but not in attributes on the method  
nameof(f) -> "f"  
nameof(f<T>) -> syntax error  
nameof(f<>) -> syntax error  
nameof(Method2()) -> error "This expression does not have a name"  
```  
  
## <a name="remarks"></a><span data-ttu-id="0d713-118">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0d713-118">Remarks</span></span>  
 <span data-ttu-id="0d713-119">El argumento `nameof` debe ser un nombre sencillo, nombre completo, acceso a miembros, acceso base a un miembro especificado o este acceso a un miembro especificado.</span><span class="sxs-lookup"><span data-stu-id="0d713-119">The argument to `nameof` must be a simple name, qualified name, member access, base access with a specified member, or this access with a specified member.</span></span>  <span data-ttu-id="0d713-120">La expresión de argumento identifica una definición de código, pero nunca se evalúa.</span><span class="sxs-lookup"><span data-stu-id="0d713-120">The argument expression identifies a code definition, but it is never evaluated.</span></span>  
  
 <span data-ttu-id="0d713-121">Dado que el argumento debe ser sintácticamente una expresión, hay muchas cosas no permitidas que no sería útil mostrar.</span><span class="sxs-lookup"><span data-stu-id="0d713-121">Because the argument needs to be an expression syntactically, there are many things disallowed that are not useful to list.</span></span>  <span data-ttu-id="0d713-122">Sí vale la pena mencionar los siguientes elementos que producen errores: tipos predefinidos (por ejemplo, `int` o `void`), tipos que aceptan valores null (`Point?`), tipos de matriz (`Customer[,]`), tipos de puntero (`Buffer*`), alias completo (`A::B`), tipos genéricos sin enlazar (`Dictionary<,>`), símbolos de preprocesamiento (`DEBUG`) y etiquetas (`loop:`).</span><span class="sxs-lookup"><span data-stu-id="0d713-122">The following are worth mentioning that produce errors: predefined types (for example, `int` or `void`), nullable types (`Point?`), array types (`Customer[,]`), pointer types (`Buffer*`), qualified alias (`A::B`), and unbound generic types (`Dictionary<,>`), preprocessing symbols (`DEBUG`), and labels (`loop:`).</span></span>  
  
 <span data-ttu-id="0d713-123">Si necesita obtener el nombre completo, puede utilizar la expresión `typeof` junto con `nameof`.</span><span class="sxs-lookup"><span data-stu-id="0d713-123">If you need to get the fully-qualified name, you can use the `typeof` expression along with `nameof`.</span></span>  <span data-ttu-id="0d713-124">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0d713-124">For example:</span></span>
```csharp  
class C {
    void f(int i) {  
        Log($"{typeof(C)}.{nameof(f)}", "method entry");  
    }
}
``` 

 <span data-ttu-id="0d713-125">`typeof` no es una expresión constante como `nameof`, por lo que `typeof` no puede usarse junto con `nameof` en los mismos lugares que `nameof`.</span><span class="sxs-lookup"><span data-stu-id="0d713-125">Unfortunately `typeof` is not a constant expression like `nameof`, so `typeof` cannot be used in conjunction with `nameof` in all the same places as `nameof`.</span></span>  <span data-ttu-id="0d713-126">Por ejemplo, el siguiente ejemplo provocaría un error de compilación CS0182:</span><span class="sxs-lookup"><span data-stu-id="0d713-126">For example, the following would cause a CS0182 compile error:</span></span>
 ```csharp  
[DebuggerDisplay("={" + typeof(C) + nameof(GetString) + "()}")]  
class C {  
    string GetString() { }  
}  
```    
 <span data-ttu-id="0d713-127">En los ejemplos verá que puede utilizar un nombre de tipo y acceder a un nombre de método de instancia.</span><span class="sxs-lookup"><span data-stu-id="0d713-127">In the examples you see that you can use a type name and access an instance method name.</span></span>  <span data-ttu-id="0d713-128">No es necesario tener una instancia del tipo, tal como se requiere en las expresiones evaluadas.</span><span class="sxs-lookup"><span data-stu-id="0d713-128">You do not need to have an instance of the type, as required in evaluated expressions.</span></span>  <span data-ttu-id="0d713-129">Usar el nombre de tipo puede ser muy práctico en algunas situaciones, y puesto que solo hace referencia al nombre y no utiliza datos de instancia, no necesita idear una expresión o una variable de instancia.</span><span class="sxs-lookup"><span data-stu-id="0d713-129">Using the type name can be very convenient in some situations, and since you are just referring to the name and not using instance data, you do not need to contrive an instance variable or expression.</span></span>  
  
 <span data-ttu-id="0d713-130">Puede hacer referencia a los miembros de una clase en expresiones de atributos en la clase.</span><span class="sxs-lookup"><span data-stu-id="0d713-130">You can reference the members of a class in attribute expressions on the class.</span></span>  
  
 <span data-ttu-id="0d713-131">No hay ninguna manera de obtener información de firma, como "`Method1 (str, str)`".</span><span class="sxs-lookup"><span data-stu-id="0d713-131">There is no way to get a signatures information such as "`Method1 (str, str)`".</span></span>  <span data-ttu-id="0d713-132">Una manera de hacerlo es usar una expresión, `Expression e = () => A.B.Method1("s1", "s2")`, y extraer el MemberInfo del árbol de expresión resultante.</span><span class="sxs-lookup"><span data-stu-id="0d713-132">One way to do that is to use an Expression, `Expression e = () => A.B.Method1("s1", "s2")`, and pull the MemberInfo from the resulting expression tree.</span></span>  
  
## <a name="language-specifications"></a><span data-ttu-id="0d713-133">Especificaciones del lenguaje</span><span class="sxs-lookup"><span data-stu-id="0d713-133">Language Specifications</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0d713-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="0d713-134">See Also</span></span>  
 [<span data-ttu-id="0d713-135">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="0d713-135">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="0d713-136">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="0d713-136">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="0d713-137">typeof</span><span class="sxs-lookup"><span data-stu-id="0d713-137">typeof</span></span>](../../../csharp/language-reference/keywords/typeof.md)  
 
