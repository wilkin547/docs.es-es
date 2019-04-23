---
title: 'nameof: Referencia de C#'
ms.custom: seodec18
ms.date: 06/16/2017
f1_keywords:
- nameof_CSharpKeyword
- nameof
ms.assetid: 33601bf3-cc2c-4496-846d-f9679bccf2a7
ms.openlocfilehash: 04de4dc6f320213c1a9c95b1abb92488fac0a81f
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2019
ms.locfileid: "59614095"
---
# <a name="nameof-c-reference"></a><span data-ttu-id="b7401-102">nameof (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="b7401-102">nameof (C# Reference)</span></span>

<span data-ttu-id="b7401-103">Se utiliza para obtener el nombre de cadena (incompleto) simple de una variable, tipo o miembro.</span><span class="sxs-lookup"><span data-stu-id="b7401-103">Used to obtain the simple (unqualified) string name of a variable, type, or member.</span></span>

<span data-ttu-id="b7401-104">Al informar de errores en el código, enlazar vínculos de controlador de vistas de modelo (MVC), desencadenar eventos de propiedad cambiada, etc., a menudo le interesa capturar el nombre de cadena de un método.</span><span class="sxs-lookup"><span data-stu-id="b7401-104">When reporting errors in code, hooking up model-view-controller (MVC) links, firing property changed events, etc., you often want to capture the string name of a method.</span></span>  <span data-ttu-id="b7401-105">Usar `nameof` ayuda a lograr que su código siga siendo válido al cambiar el nombre de definiciones.</span><span class="sxs-lookup"><span data-stu-id="b7401-105">Using `nameof` helps keep your code valid when renaming definitions.</span></span>  <span data-ttu-id="b7401-106">Antes había que usar literales de cadena para hacer referencia a definiciones, lo que resulta precario al cambiar el nombre de elementos de código, ya que las herramientas no saben comprobar estos literales de cadena.</span><span class="sxs-lookup"><span data-stu-id="b7401-106">Before, you had to use string literals to refer to definitions, which is brittle when renaming code elements because tools do not know to check these string literals.</span></span>

<span data-ttu-id="b7401-107">Una expresión `nameof` tiene este formato:</span><span class="sxs-lookup"><span data-stu-id="b7401-107">A `nameof` expression has this form:</span></span>

```csharp
if (x == null) throw new ArgumentNullException(nameof(x));
WriteLine(nameof(person.Address.ZipCode)); // prints "ZipCode"
```

## <a name="key-use-cases"></a><span data-ttu-id="b7401-108">Casos de uso clave</span><span class="sxs-lookup"><span data-stu-id="b7401-108">Key Use Cases</span></span>

<span data-ttu-id="b7401-109">Estos ejemplos muestran los casos de uso clave para `nameof`.</span><span class="sxs-lookup"><span data-stu-id="b7401-109">These examples show the key use cases for `nameof`.</span></span>

<span data-ttu-id="b7401-110">Validar parámetros:</span><span class="sxs-lookup"><span data-stu-id="b7401-110">Validate parameters:</span></span>

 ```csharp
void f(string s) {
    if (s == null) throw new ArgumentNullException(nameof(s));
}
```

<span data-ttu-id="b7401-111">Vínculos de acción de MVC:</span><span class="sxs-lookup"><span data-stu-id="b7401-111">MVC Action links:</span></span>

```html
<%= Html.ActionLink("Sign up",
             @typeof(UserController),
             @nameof(UserController.SignUp))
%>
```

<span data-ttu-id="b7401-112">INotifyPropertyChanged:</span><span class="sxs-lookup"><span data-stu-id="b7401-112">INotifyPropertyChanged:</span></span>

```csharp
int p {
    get { return this.p; }
    set { this.p = value; PropertyChanged(this, new PropertyChangedEventArgs(nameof(this.p)); } // nameof(p) works too
}
```

<span data-ttu-id="b7401-113">Propiedad de dependencia de XAML:</span><span class="sxs-lookup"><span data-stu-id="b7401-113">XAML dependency property:</span></span>

```csharp
public static DependencyProperty AgeProperty = DependencyProperty.Register(nameof(Age), typeof(int), typeof(C));
```

<span data-ttu-id="b7401-114">Registro:</span><span class="sxs-lookup"><span data-stu-id="b7401-114">Logging:</span></span>

```csharp
void f(int i) {
    Log(nameof(f), "method entry");
}
```

<span data-ttu-id="b7401-115">Atributos:</span><span class="sxs-lookup"><span data-stu-id="b7401-115">Attributes:</span></span>

```csharp
[DebuggerDisplay("={" + nameof(GetString) + "()}")]
class C {
    string GetString() { }
}
```

## <a name="examples"></a><span data-ttu-id="b7401-116">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="b7401-116">Examples</span></span>

<span data-ttu-id="b7401-117">Algunos ejemplos de C#:</span><span class="sxs-lookup"><span data-stu-id="b7401-117">Some C# examples:</span></span>

```csharp
using Stuff = Some.Cool.Functionality
class C {
    static int Method1 (string x, int y) {}
    static int Method1 (string x, string y) {}
    int Method2 (int z) {}
    string f<T>() => nameof(T);
}

var c = new C()

class Test {
    static void Main (string[] args) {
        Console.WriteLine(nameof(C)); // -> "C"
        Console.WriteLine(nameof(C.Method1)); // -> "Method1"
        Console.WriteLine(nameof(C.Method2)); // -> "Method2"
        Console.WriteLine(nameof(c.Method1)); // -> "Method1"
        Console.WriteLine(nameof(c.Method2)); // -> "Method2"
        // Console.WriteLine(nameof(z)); -> "z" [inside of Method2 ok, inside Method1 is a compiler error]
        Console.WriteLine(nameof(Stuff)); // -> "Stuff"
        // Console.WriteLine(nameof(T)); -> "T" [works inside of method but not in attributes on the method]
        Console.WriteLine(nameof(f)); // -> "f"
        // Console.WriteLine(nameof(f<T>)); -> [syntax error]
        // Console.WriteLine(nameof(f<>)); -> [syntax error]
        // Console.WriteLine(nameof(Method2())); -> [error "This expression does not have a name"]
    }
}
```

## <a name="remarks"></a><span data-ttu-id="b7401-118">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b7401-118">Remarks</span></span>

<span data-ttu-id="b7401-119">El argumento `nameof` debe ser un nombre sencillo, nombre completo, acceso a miembros, acceso base a un miembro especificado o este acceso a un miembro especificado.</span><span class="sxs-lookup"><span data-stu-id="b7401-119">The argument to `nameof` must be a simple name, qualified name, member access, base access with a specified member, or this access with a specified member.</span></span>  <span data-ttu-id="b7401-120">La expresión de argumento identifica una definición de código, pero nunca se evalúa.</span><span class="sxs-lookup"><span data-stu-id="b7401-120">The argument expression identifies a code definition, but it is never evaluated.</span></span>

<span data-ttu-id="b7401-121">Dado que el argumento debe ser sintácticamente una expresión, hay muchas cosas no permitidas que no sería útil mostrar.</span><span class="sxs-lookup"><span data-stu-id="b7401-121">Because the argument needs to be an expression syntactically, there are many things disallowed that are not useful to list.</span></span>  <span data-ttu-id="b7401-122">Sí vale la pena mencionar los siguientes elementos que producen errores: tipos predefinidos (por ejemplo, `int` o `void`), tipos que aceptan valores null (`Point?`), tipos de matriz (`Customer[,]`), tipos de puntero (`Buffer*`), alias completo (`A::B`), tipos genéricos sin enlazar (`Dictionary<,>`), símbolos de preprocesamiento (`DEBUG`) y etiquetas (`loop:`).</span><span class="sxs-lookup"><span data-stu-id="b7401-122">The following are worth mentioning that produce errors: predefined types (for example, `int` or `void`), nullable types (`Point?`), array types (`Customer[,]`), pointer types (`Buffer*`), qualified alias (`A::B`), and unbound generic types (`Dictionary<,>`), preprocessing symbols (`DEBUG`), and labels (`loop:`).</span></span>

<span data-ttu-id="b7401-123">Si necesita obtener el nombre completo, puede utilizar la expresión `typeof` junto con `nameof`.</span><span class="sxs-lookup"><span data-stu-id="b7401-123">If you need to get the fully-qualified name, you can use the `typeof` expression along with `nameof`.</span></span>  <span data-ttu-id="b7401-124">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b7401-124">For example:</span></span>

```csharp
class C {
    void f(int i) {
        Log($"{typeof(C)}.{nameof(f)}", "method entry");
    }
}
```

<span data-ttu-id="b7401-125">`typeof` no es una expresión constante como `nameof`, por lo que `typeof` no puede usarse junto con `nameof` en los mismos lugares que `nameof`.</span><span class="sxs-lookup"><span data-stu-id="b7401-125">Unfortunately `typeof` is not a constant expression like `nameof`, so `typeof` cannot be used in conjunction with `nameof` in all the same places as `nameof`.</span></span>  <span data-ttu-id="b7401-126">Por ejemplo, el siguiente ejemplo provocaría un error de compilación CS0182:</span><span class="sxs-lookup"><span data-stu-id="b7401-126">For example, the following would cause a CS0182 compile error:</span></span>

```csharp
[DebuggerDisplay("={" + typeof(C) + nameof(GetString) + "()}")]
class C {
    string GetString() { }
}
```

<span data-ttu-id="b7401-127">En los ejemplos verá que puede utilizar un nombre de tipo y acceder a un nombre de método de instancia.</span><span class="sxs-lookup"><span data-stu-id="b7401-127">In the examples you see that you can use a type name and access an instance method name.</span></span>  <span data-ttu-id="b7401-128">No es necesario tener una instancia del tipo, tal como se requiere en las expresiones evaluadas.</span><span class="sxs-lookup"><span data-stu-id="b7401-128">You do not need to have an instance of the type, as required in evaluated expressions.</span></span>  <span data-ttu-id="b7401-129">Usar el nombre de tipo puede ser muy práctico en algunas situaciones, y puesto que solo hace referencia al nombre y no utiliza datos de instancia, no necesita idear una expresión o una variable de instancia.</span><span class="sxs-lookup"><span data-stu-id="b7401-129">Using the type name can be very convenient in some situations, and since you are just referring to the name and not using instance data, you do not need to contrive an instance variable or expression.</span></span>

<span data-ttu-id="b7401-130">Puede hacer referencia a los miembros de una clase en expresiones de atributos en la clase.</span><span class="sxs-lookup"><span data-stu-id="b7401-130">You can reference the members of a class in attribute expressions on the class.</span></span>

<span data-ttu-id="b7401-131">No hay ninguna manera de obtener información de firma, como "`Method1 (str, str)`".</span><span class="sxs-lookup"><span data-stu-id="b7401-131">There is no way to get a signatures information such as "`Method1 (str, str)`".</span></span>  <span data-ttu-id="b7401-132">Una manera de hacerlo es usar una expresión, `Expression e = () => A.B.Method1("s1", "s2")`, y extraer el MemberInfo del árbol de expresión resultante.</span><span class="sxs-lookup"><span data-stu-id="b7401-132">One way to do that is to use an Expression, `Expression e = () => A.B.Method1("s1", "s2")`, and pull the MemberInfo from the resulting expression tree.</span></span>

## <a name="language-specifications"></a><span data-ttu-id="b7401-133">Especificaciones del lenguaje</span><span class="sxs-lookup"><span data-stu-id="b7401-133">Language Specifications</span></span>

<span data-ttu-id="b7401-134">Para obtener más información, vea la sección [Expresiones nameof](~/_csharplang/spec/expressions.md#nameof-expressions) de la [Especificación del lenguaje C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="b7401-134">For more information, see [Nameof expressions](~/_csharplang/spec/expressions.md#nameof-expressions) in the [C# Language Specification](../language-specification/index.md).</span></span> <span data-ttu-id="b7401-135">La especificación del lenguaje es la fuente definitiva de la sintaxis y el uso de C#.</span><span class="sxs-lookup"><span data-stu-id="b7401-135">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="b7401-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="b7401-136">See also</span></span>

- [<span data-ttu-id="b7401-137">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="b7401-137">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="b7401-138">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="b7401-138">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="b7401-139">typeof</span><span class="sxs-lookup"><span data-stu-id="b7401-139">typeof</span></span>](../../../csharp/language-reference/keywords/typeof.md)
