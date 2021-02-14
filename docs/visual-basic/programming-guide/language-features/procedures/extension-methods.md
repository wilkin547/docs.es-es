---
description: 'Más información acerca de: métodos de extensión (Visual Basic)'
title: Métodos de extensión
ms.date: 07/20/2015
f1_keywords:
- vb.ExtensionMethods
helpviewer_keywords:
- extending data types [Visual Basic]
- extension methods [Visual Basic]
ms.assetid: b8020aae-374d-46a9-bcb7-8cc2390b93b6
ms.openlocfilehash: 5a1482502b144524c0be90e1c83a38f49b4a4d26
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100434360"
---
# <a name="extension-methods-visual-basic"></a><span data-ttu-id="40f3f-103">Métodos de extensión (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="40f3f-103">Extension Methods (Visual Basic)</span></span>

<span data-ttu-id="40f3f-104">Los métodos de extensión permiten a los desarrolladores agregar funcionalidad personalizada a los tipos de datos que ya están definidos sin crear un nuevo tipo derivado.</span><span class="sxs-lookup"><span data-stu-id="40f3f-104">Extension methods enable developers to add custom functionality to data types that are already defined without creating a new derived type.</span></span> <span data-ttu-id="40f3f-105">Los métodos de extensión permiten escribir un método al que se puede llamar como si fuera un método de instancia del tipo existente.</span><span class="sxs-lookup"><span data-stu-id="40f3f-105">Extension methods make it possible to write a method that can be called as if it were an instance method of the existing type.</span></span>

## <a name="remarks"></a><span data-ttu-id="40f3f-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="40f3f-106">Remarks</span></span>

<span data-ttu-id="40f3f-107">Un método de extensión solo puede ser un `Sub` procedimiento o un `Function` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="40f3f-107">An extension method can be only a `Sub` procedure or a `Function` procedure.</span></span> <span data-ttu-id="40f3f-108">No se puede definir una propiedad de extensión, un campo o un evento.</span><span class="sxs-lookup"><span data-stu-id="40f3f-108">You cannot define an extension property, field, or event.</span></span> <span data-ttu-id="40f3f-109">Todos los métodos de extensión se deben marcar con el atributo `<Extension>` de extensión del <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> espacio de nombres y deben definirse en un [módulo](../../../language-reference/statements/module-statement.md).</span><span class="sxs-lookup"><span data-stu-id="40f3f-109">All extension methods must be marked with the extension attribute `<Extension>` from the <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> namespace and must be defined in a [Module](../../../language-reference/statements/module-statement.md).</span></span> <span data-ttu-id="40f3f-110">Si se define un método de extensión fuera de un módulo, el compilador Visual Basic genera el error [BC36551](../../../misc/bc36551.md), "los métodos de extensión solo se pueden definir en módulos".</span><span class="sxs-lookup"><span data-stu-id="40f3f-110">If an extension method is defined outside a module, the Visual Basic compiler generates error [BC36551](../../../misc/bc36551.md), "Extension methods can be defined only in modules".</span></span>

<span data-ttu-id="40f3f-111">El primer parámetro de una definición de método de extensión especifica qué tipo de datos extiende el método.</span><span class="sxs-lookup"><span data-stu-id="40f3f-111">The first parameter in an extension method definition specifies which data type the method extends.</span></span> <span data-ttu-id="40f3f-112">Cuando se ejecuta el método, el primer parámetro se enlaza a la instancia del tipo de datos que invoca el método.</span><span class="sxs-lookup"><span data-stu-id="40f3f-112">When the method is run, the first parameter is bound to the instance of the data type that invokes the method.</span></span>

<span data-ttu-id="40f3f-113">El `Extension` atributo solo se puede aplicar a un Visual Basic [`Module`](../../../language-reference/statements/module-statement.md) , [`Sub`](../../../language-reference/statements/sub-statement.md) o [`Function`](../../../language-reference/statements/function-statement.md) .</span><span class="sxs-lookup"><span data-stu-id="40f3f-113">The `Extension` attribute can only be applied to a Visual Basic [`Module`](../../../language-reference/statements/module-statement.md), [`Sub`](../../../language-reference/statements/sub-statement.md), or [`Function`](../../../language-reference/statements/function-statement.md).</span></span> <span data-ttu-id="40f3f-114">Si se aplica a un objeto o a un objeto `Class` `Structure` , el compilador Visual Basic genera el error [BC36550](../../../language-reference/error-messages/extension-attribute-can-be-applied-only-to-module-sub-or-function-declarations.md), el atributo ' Extension ' solo se puede aplicar a las declaraciones ' module ', ' sub ' o ' function '.</span><span class="sxs-lookup"><span data-stu-id="40f3f-114">If you apply it to a `Class` or a `Structure`, the Visual Basic compiler generates error [BC36550](../../../language-reference/error-messages/extension-attribute-can-be-applied-only-to-module-sub-or-function-declarations.md), "'Extension' attribute can be applied only to 'Module', 'Sub', or 'Function' declarations".</span></span>

## <a name="example"></a><span data-ttu-id="40f3f-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="40f3f-115">Example</span></span>

<span data-ttu-id="40f3f-116">En el ejemplo siguiente se define una `Print` extensión para el <xref:System.String> tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="40f3f-116">The following example defines a `Print` extension to the <xref:System.String> data type.</span></span> <span data-ttu-id="40f3f-117">El método utiliza `Console.WriteLine` para mostrar una cadena.</span><span class="sxs-lookup"><span data-stu-id="40f3f-117">The method uses `Console.WriteLine` to display a string.</span></span> <span data-ttu-id="40f3f-118">El parámetro del `Print` método, `aString` , establece que el método extiende la <xref:System.String> clase.</span><span class="sxs-lookup"><span data-stu-id="40f3f-118">The parameter of the `Print` method, `aString`, establishes that the method extends the <xref:System.String> class.</span></span>

[!code-vb[VbVbalrExtensionMethods#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/StringExtensions.vb#1)]

<span data-ttu-id="40f3f-119">Observe que la definición del método de extensión está marcada con el atributo de extensión `<Extension()>` .</span><span class="sxs-lookup"><span data-stu-id="40f3f-119">Notice that the extension method definition is marked with the extension attribute `<Extension()>`.</span></span> <span data-ttu-id="40f3f-120">Marcar el módulo en el que se define el método es opcional, pero se debe marcar cada método de extensión.</span><span class="sxs-lookup"><span data-stu-id="40f3f-120">Marking the module in which the method is defined is optional, but each extension method must be marked.</span></span> <span data-ttu-id="40f3f-121"><xref:System.Runtime.CompilerServices> se debe importar para tener acceso al atributo de extensión.</span><span class="sxs-lookup"><span data-stu-id="40f3f-121"><xref:System.Runtime.CompilerServices> must be imported in order to access the extension attribute.</span></span>

<span data-ttu-id="40f3f-122">Los métodos de extensión se pueden declarar solo dentro de los módulos.</span><span class="sxs-lookup"><span data-stu-id="40f3f-122">Extension methods can be declared only within modules.</span></span> <span data-ttu-id="40f3f-123">Normalmente, el módulo en el que se define un método de extensión no es el mismo módulo que el en el que se llama.</span><span class="sxs-lookup"><span data-stu-id="40f3f-123">Typically, the module in which an extension method is defined is not the same module as the one in which it is called.</span></span> <span data-ttu-id="40f3f-124">En su lugar, se importa el módulo que contiene el método de extensión, si es necesario, para ponerlo en el ámbito.</span><span class="sxs-lookup"><span data-stu-id="40f3f-124">Instead, the module that contains the extension method is imported, if it needs to be, to bring it into scope.</span></span> <span data-ttu-id="40f3f-125">Después de que el módulo que contiene `Print` está en el ámbito, se puede llamar al método como si fuera un método de instancia normal que no toma ningún argumento, como `ToUpper` :</span><span class="sxs-lookup"><span data-stu-id="40f3f-125">After the module that contains `Print` is in scope, the method can be called as if it were an ordinary instance method that takes no arguments, such as `ToUpper`:</span></span>

[!code-vb[VbVbalrExtensionMethods#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Class1.vb#2)]

<span data-ttu-id="40f3f-126">En el ejemplo siguiente, `PrintAndPunctuate` , es también una extensión de <xref:System.String> , esta vez definida con dos parámetros.</span><span class="sxs-lookup"><span data-stu-id="40f3f-126">The next example, `PrintAndPunctuate`, is also an extension to <xref:System.String>, this time defined with two parameters.</span></span> <span data-ttu-id="40f3f-127">El primer parámetro, `aString` , establece que el método de extensión extiende <xref:System.String> .</span><span class="sxs-lookup"><span data-stu-id="40f3f-127">The first parameter, `aString`, establishes that the extension method extends <xref:System.String>.</span></span> <span data-ttu-id="40f3f-128">El segundo parámetro, `punc` , está pensado para ser una cadena de signos de puntuación que se pasa como argumento cuando se llama al método.</span><span class="sxs-lookup"><span data-stu-id="40f3f-128">The second parameter, `punc`, is intended to be a string of punctuation marks that is passed in as an argument when the method is called.</span></span> <span data-ttu-id="40f3f-129">El método muestra la cadena seguida de los signos de puntuación.</span><span class="sxs-lookup"><span data-stu-id="40f3f-129">The method displays the string followed by the punctuation marks.</span></span>

[!code-vb[VbVbalrExtensionMethods#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Class2.vb#3)]

<span data-ttu-id="40f3f-130">Se llama al método mediante el envío de un argumento de cadena para `punc` : `example.PrintAndPunctuate(".")`</span><span class="sxs-lookup"><span data-stu-id="40f3f-130">The method is called by sending in a string argument for `punc`: `example.PrintAndPunctuate(".")`</span></span>

<span data-ttu-id="40f3f-131">En el ejemplo siguiente se muestra `Print` y se `PrintAndPunctuate` define y se llama a.</span><span class="sxs-lookup"><span data-stu-id="40f3f-131">The following example shows `Print` and `PrintAndPunctuate` defined and called.</span></span> <span data-ttu-id="40f3f-132"><xref:System.Runtime.CompilerServices> se importa en el módulo de definición para permitir el acceso al atributo de extensión.</span><span class="sxs-lookup"><span data-stu-id="40f3f-132"><xref:System.Runtime.CompilerServices> is imported in the definition module in order to enable access to the extension attribute.</span></span>

```vb
Imports System.Runtime.CompilerServices

Module StringExtensions

    <Extension()>
    Public Sub Print(aString As String)
        Console.WriteLine(aString)
    End Sub

    <Extension()>
    Public Sub PrintAndPunctuate(aString As String, punc As String)
        Console.WriteLine(aString & punc)
    End Sub
End Module
```

<span data-ttu-id="40f3f-133">Después, los métodos de extensión se incluyen en el ámbito y se denominan:</span><span class="sxs-lookup"><span data-stu-id="40f3f-133">Next, the extension methods are brought into scope and called:</span></span>

```vb
Imports ConsoleApplication2.StringExtensions

Module Module1

    Sub Main()
        Dim example As String = "Example string"
        example.Print()

        example = "Hello"
        example.PrintAndPunctuate(".")
        example.PrintAndPunctuate("!!!!")
    End Sub
End Module
```

<span data-ttu-id="40f3f-134">Todo lo que se necesita para poder ejecutar estos métodos de extensión o similares es que están dentro del ámbito.</span><span class="sxs-lookup"><span data-stu-id="40f3f-134">All that is required to be able to run these or similar extension methods is that they be in scope.</span></span> <span data-ttu-id="40f3f-135">Si el módulo que contiene un método de extensión está en el ámbito, es visible en IntelliSense y se puede llamar como si fuera un método de instancia normal.</span><span class="sxs-lookup"><span data-stu-id="40f3f-135">If the module that contains an extension method is in scope, it is visible in IntelliSense and can be called as if it were an ordinary instance method.</span></span>

<span data-ttu-id="40f3f-136">Tenga en cuenta que cuando se invocan los métodos, no se envía ningún argumento para el primer parámetro.</span><span class="sxs-lookup"><span data-stu-id="40f3f-136">Notice that when the methods are invoked, no argument is sent in for the first parameter.</span></span> <span data-ttu-id="40f3f-137">El parámetro `aString` de las definiciones de método anteriores se enlaza a `example` , la instancia de `String` que los llama.</span><span class="sxs-lookup"><span data-stu-id="40f3f-137">Parameter `aString` in the previous method definitions is bound to `example`, the instance of `String` that calls them.</span></span> <span data-ttu-id="40f3f-138">El compilador usará `example` como el argumento enviado al primer parámetro.</span><span class="sxs-lookup"><span data-stu-id="40f3f-138">The compiler will use `example` as the argument sent to the first parameter.</span></span>

<span data-ttu-id="40f3f-139">Si se llama a un método de extensión para un objeto que se establece en `Nothing` , se ejecuta el método de extensión.</span><span class="sxs-lookup"><span data-stu-id="40f3f-139">If an extension method is called for an object that is set to `Nothing`, the extension method executes.</span></span> <span data-ttu-id="40f3f-140">Esto no se aplica a los métodos de instancia normales.</span><span class="sxs-lookup"><span data-stu-id="40f3f-140">This does not apply to ordinary instance methods.</span></span> <span data-ttu-id="40f3f-141">Puede comprobar explícitamente `Nothing` en el método de extensión.</span><span class="sxs-lookup"><span data-stu-id="40f3f-141">You can explicitly check for `Nothing` in the extension method.</span></span>

## <a name="types-that-can-be-extended"></a><span data-ttu-id="40f3f-142">Tipos que se pueden extender</span><span class="sxs-lookup"><span data-stu-id="40f3f-142">Types that can be extended</span></span>

<span data-ttu-id="40f3f-143">Puede definir un método de extensión en la mayoría de los tipos que se pueden representar en una lista de parámetros de Visual Basic, incluidas las siguientes:</span><span class="sxs-lookup"><span data-stu-id="40f3f-143">You can define an extension method on most types that can be represented in a Visual Basic parameter list, including the following:</span></span>

- <span data-ttu-id="40f3f-144">Clases (tipos de referencia)</span><span class="sxs-lookup"><span data-stu-id="40f3f-144">Classes (reference types)</span></span>
- <span data-ttu-id="40f3f-145">Estructuras (tipos de valor)</span><span class="sxs-lookup"><span data-stu-id="40f3f-145">Structures (value types)</span></span>
- <span data-ttu-id="40f3f-146">Interfaces</span><span class="sxs-lookup"><span data-stu-id="40f3f-146">Interfaces</span></span>
- <span data-ttu-id="40f3f-147">Delegados</span><span class="sxs-lookup"><span data-stu-id="40f3f-147">Delegates</span></span>
- <span data-ttu-id="40f3f-148">Argumentos ByRef y ByVal</span><span class="sxs-lookup"><span data-stu-id="40f3f-148">ByRef and ByVal arguments</span></span>
- <span data-ttu-id="40f3f-149">Parámetros de método genérico</span><span class="sxs-lookup"><span data-stu-id="40f3f-149">Generic method parameters</span></span>
- <span data-ttu-id="40f3f-150">Matrices</span><span class="sxs-lookup"><span data-stu-id="40f3f-150">Arrays</span></span>

<span data-ttu-id="40f3f-151">Dado que el primer parámetro especifica el tipo de datos que extiende el método de extensión, es obligatorio y no puede ser opcional.</span><span class="sxs-lookup"><span data-stu-id="40f3f-151">Because the first parameter specifies the data type that the extension method extends, it is required and cannot be optional.</span></span> <span data-ttu-id="40f3f-152">Por ese motivo, `Optional` los parámetros y parámetros `ParamArray` no pueden ser el primer parámetro de la lista de parámetros.</span><span class="sxs-lookup"><span data-stu-id="40f3f-152">For that reason, `Optional` parameters and `ParamArray` parameters cannot be the first parameter in the parameter list.</span></span>

<span data-ttu-id="40f3f-153">Los métodos de extensión no se consideran en el enlace en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="40f3f-153">Extension methods are not considered in late binding.</span></span> <span data-ttu-id="40f3f-154">En el ejemplo siguiente, la instrucción `anObject.PrintMe()` genera una <xref:System.MissingMemberException> excepción, la misma excepción que vería si `PrintMe` se eliminara la segunda definición de método de extensión.</span><span class="sxs-lookup"><span data-stu-id="40f3f-154">In the following example, the statement `anObject.PrintMe()` raises a <xref:System.MissingMemberException> exception, the same exception you would see if the second `PrintMe` extension method definition were deleted.</span></span>

[!code-vb[VbVbalrExtensionMethods#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Class6.vb#9)]

## <a name="best-practices"></a><span data-ttu-id="40f3f-155">Procedimientos recomendados</span><span class="sxs-lookup"><span data-stu-id="40f3f-155">Best practices</span></span>

<span data-ttu-id="40f3f-156">Los métodos de extensión proporcionan una forma cómoda y eficaz de extender un tipo existente.</span><span class="sxs-lookup"><span data-stu-id="40f3f-156">Extension methods provide a convenient and powerful way to extend an existing type.</span></span> <span data-ttu-id="40f3f-157">Sin embargo, para usarlos correctamente, hay que tener en cuenta algunos aspectos.</span><span class="sxs-lookup"><span data-stu-id="40f3f-157">However, to use them successfully, there are some points to consider.</span></span> <span data-ttu-id="40f3f-158">Estas consideraciones se aplican principalmente a los autores de bibliotecas de clases, pero pueden afectar a cualquier aplicación que use métodos de extensión.</span><span class="sxs-lookup"><span data-stu-id="40f3f-158">These considerations apply mainly to authors of class libraries, but they might affect any application that uses extension methods.</span></span>

<span data-ttu-id="40f3f-159">En general, los métodos de extensión que se agregan a tipos que no son de su propiedad son más vulnerables que los métodos de extensión agregados a los tipos que usted controla.</span><span class="sxs-lookup"><span data-stu-id="40f3f-159">Most generally, extension methods that you add to types that you do not own are more vulnerable than extension methods added to types that you control.</span></span> <span data-ttu-id="40f3f-160">Se pueden producir varias cosas en las clases que no son de su propiedad y que pueden interferir con los métodos de extensión.</span><span class="sxs-lookup"><span data-stu-id="40f3f-160">A number of things can occur in classes you do not own that can interfere with your extension methods.</span></span>

- <span data-ttu-id="40f3f-161">Si existe un miembro de instancia accesible que tiene una firma que es compatible con los argumentos de la instrucción de llamada, sin conversiones de restricción necesarias del argumento al parámetro, se utilizará el método de instancia en preferencia a cualquier método de extensión.</span><span class="sxs-lookup"><span data-stu-id="40f3f-161">If any accessible instance member exists that has a signature that is compatible with the arguments in the calling statement, with no narrowing conversions required from argument to parameter, the instance method will be used in preference to any extension method.</span></span> <span data-ttu-id="40f3f-162">Por lo tanto, si se agrega un método de instancia adecuado a una clase en algún momento, es posible que no se pueda obtener acceso a un miembro de extensión existente del que dependa.</span><span class="sxs-lookup"><span data-stu-id="40f3f-162">Therefore, if an appropriate instance method is added to a class at some point, an existing extension member that you rely on may become inaccessible.</span></span>

- <span data-ttu-id="40f3f-163">El autor de un método de extensión no puede impedir que otros programadores escriban métodos de extensión en conflicto que puedan tener prioridad sobre la extensión original.</span><span class="sxs-lookup"><span data-stu-id="40f3f-163">The author of an extension method cannot prevent other programmers from writing conflicting extension methods that may have precedence over the original extension.</span></span>

- <span data-ttu-id="40f3f-164">Puede mejorar la robustez colocando métodos de extensión en su propio espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="40f3f-164">You can improve robustness by putting extension methods in their own namespace.</span></span> <span data-ttu-id="40f3f-165">Los consumidores de la biblioteca pueden incluir un espacio de nombres o excluirlo, o seleccionar entre espacios de nombres, independientemente del resto de la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="40f3f-165">Consumers of your library can then include a namespace or exclude it, or select among namespaces, separately from the rest of the library.</span></span>

- <span data-ttu-id="40f3f-166">Puede ser más seguro extender las interfaces que para ampliar las clases, especialmente si no posee la interfaz o la clase.</span><span class="sxs-lookup"><span data-stu-id="40f3f-166">It may be safer to extend interfaces than it is to extend classes, especially if you do not own the interface or class.</span></span> <span data-ttu-id="40f3f-167">Un cambio en una interfaz afecta a cada clase que lo implementa.</span><span class="sxs-lookup"><span data-stu-id="40f3f-167">A change in an interface affects every class that implements it.</span></span> <span data-ttu-id="40f3f-168">Por lo tanto, es menos probable que el autor agregue o cambie métodos en una interfaz.</span><span class="sxs-lookup"><span data-stu-id="40f3f-168">Therefore, the author may be less likely to add or change methods in an interface.</span></span> <span data-ttu-id="40f3f-169">Sin embargo, si una clase implementa dos interfaces que tienen métodos de extensión con la misma firma, no hay ningún método de extensión visible.</span><span class="sxs-lookup"><span data-stu-id="40f3f-169">However, if a class implements two interfaces that have extension methods with the same signature, neither extension method is visible.</span></span>

- <span data-ttu-id="40f3f-170">Extienda el tipo más específico que pueda.</span><span class="sxs-lookup"><span data-stu-id="40f3f-170">Extend the most specific type you can.</span></span> <span data-ttu-id="40f3f-171">En una jerarquía de tipos, si selecciona un tipo del que se derivan muchos otros tipos, existen capas de posibilidades para la introducción de métodos de instancia u otros métodos de extensión que podrían interferir con el suyo.</span><span class="sxs-lookup"><span data-stu-id="40f3f-171">In a hierarchy of types, if you select a type from which many other types are derived, there are layers of possibilities for the introduction of instance methods or other extension methods that might interfere with yours.</span></span>

## <a name="extension-methods-instance-methods-and-properties"></a><span data-ttu-id="40f3f-172">Métodos de extensión, métodos de instancia y propiedades</span><span class="sxs-lookup"><span data-stu-id="40f3f-172">Extension methods, instance methods, and properties</span></span>

<span data-ttu-id="40f3f-173">Cuando un método de instancia en el ámbito tiene una firma que es compatible con los argumentos de una instrucción de llamada, se elige el método de instancia en preferencia a cualquier método de extensión.</span><span class="sxs-lookup"><span data-stu-id="40f3f-173">When an in-scope instance method has a signature that is compatible with the arguments of a calling statement, the instance method is chosen in preference to any extension method.</span></span> <span data-ttu-id="40f3f-174">El método de instancia tiene prioridad incluso si el método de extensión es una coincidencia mejor.</span><span class="sxs-lookup"><span data-stu-id="40f3f-174">The instance method has precedence even if the extension method is a better match.</span></span> <span data-ttu-id="40f3f-175">En el ejemplo siguiente, `ExampleClass` contiene un método de instancia denominado `ExampleMethod` que tiene un parámetro de tipo `Integer` .</span><span class="sxs-lookup"><span data-stu-id="40f3f-175">In the following example, `ExampleClass` contains an instance method named `ExampleMethod` that has one parameter of type `Integer`.</span></span> <span data-ttu-id="40f3f-176">El método `ExampleMethod` de extensión extiende `ExampleClass` y tiene un parámetro de tipo `Long` .</span><span class="sxs-lookup"><span data-stu-id="40f3f-176">Extension method `ExampleMethod` extends `ExampleClass`, and has one parameter of type `Long`.</span></span>

[!code-vb[VbVbalrExtensionMethods#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Class4.vb#4)]

<span data-ttu-id="40f3f-177">La primera llamada a `ExampleMethod` en el código siguiente llama al método de extensión, porque `arg1` es `Long` y solo es compatible con el `Long` parámetro en el método de extensión.</span><span class="sxs-lookup"><span data-stu-id="40f3f-177">The first call to `ExampleMethod` in the following code calls the extension method, because `arg1` is `Long` and is compatible only with the `Long` parameter in the extension method.</span></span> <span data-ttu-id="40f3f-178">La segunda llamada a `ExampleMethod` tiene un `Integer` argumento, `arg2` , y llama al método de instancia.</span><span class="sxs-lookup"><span data-stu-id="40f3f-178">The second call to `ExampleMethod` has an `Integer` argument, `arg2`, and it calls the instance method.</span></span>

[!code-vb[VbVbalrExtensionMethods#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Class4.vb#5)]

<span data-ttu-id="40f3f-179">Ahora, invierta los tipos de datos de los parámetros en los dos métodos:</span><span class="sxs-lookup"><span data-stu-id="40f3f-179">Now reverse the data types of the parameters in the two methods:</span></span>

[!code-vb[VbVbalrExtensionMethods#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Class5.vb#6)]

<span data-ttu-id="40f3f-180">Esta vez, el código de `Main` llama al método de instancia ambas veces.</span><span class="sxs-lookup"><span data-stu-id="40f3f-180">This time the code in `Main` calls the instance method both times.</span></span> <span data-ttu-id="40f3f-181">Esto se debe `arg1` a que y `arg2` tienen una conversión de ampliación a `Long` y el método de instancia tiene prioridad sobre el método de extensión en ambos casos.</span><span class="sxs-lookup"><span data-stu-id="40f3f-181">This is because both `arg1` and `arg2` have a widening conversion to `Long`, and the instance method takes precedence over the extension method in both cases.</span></span>

[!code-vb[VbVbalrExtensionMethods#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Class5.vb#7)]

<span data-ttu-id="40f3f-182">Por lo tanto, un método de extensión no puede reemplazar un método de instancia existente.</span><span class="sxs-lookup"><span data-stu-id="40f3f-182">Therefore, an extension method cannot replace an existing instance method.</span></span> <span data-ttu-id="40f3f-183">Sin embargo, cuando un método de extensión tiene el mismo nombre que un método de instancia pero las firmas no entran en conflicto, se puede tener acceso a ambos métodos.</span><span class="sxs-lookup"><span data-stu-id="40f3f-183">However, when an extension method has the same name as an instance method but the signatures do not conflict, both methods can be accessed.</span></span> <span data-ttu-id="40f3f-184">Por ejemplo, si `ExampleClass` la clase contiene un método denominado `ExampleMethod` que no toma ningún argumento, se permiten métodos de extensión con el mismo nombre pero con firmas diferentes, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="40f3f-184">For example, if class `ExampleClass` contains a method named `ExampleMethod` that takes no arguments, extension methods with the same name but different signatures are permitted, as shown in the following code.</span></span>

[!code-vb[VbVbalrExtensionMethods#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Module3.vb#8)]

<span data-ttu-id="40f3f-185">El resultado de este código es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="40f3f-185">The output from this code is as follows:</span></span>

```console
Extension method
Instance method
```

<span data-ttu-id="40f3f-186">La situación es más sencilla con las propiedades: Si un método de extensión tiene el mismo nombre que una propiedad de la clase que extiende, el método de extensión no es visible y no se puede tener acceso a él.</span><span class="sxs-lookup"><span data-stu-id="40f3f-186">The situation is simpler with properties: if an extension method has the same name as a property of the class it extends, the extension method is not visible and cannot be accessed.</span></span>

## <a name="extension-method-precedence"></a><span data-ttu-id="40f3f-187">Precedencia del método de extensión</span><span class="sxs-lookup"><span data-stu-id="40f3f-187">Extension method precedence</span></span>

<span data-ttu-id="40f3f-188">Cuando dos métodos de extensión que tienen firmas idénticas están en el ámbito y son accesibles, se invocará el que tenga mayor precedencia.</span><span class="sxs-lookup"><span data-stu-id="40f3f-188">When two extension methods that have identical signatures are in scope and accessible, the one with higher precedence will be invoked.</span></span> <span data-ttu-id="40f3f-189">La prioridad de un método de extensión se basa en el mecanismo utilizado para poner el método en el ámbito.</span><span class="sxs-lookup"><span data-stu-id="40f3f-189">An extension method's precedence is based on the mechanism used to bring the method into scope.</span></span> <span data-ttu-id="40f3f-190">La lista siguiente muestra la jerarquía de precedencia, de mayor a menor.</span><span class="sxs-lookup"><span data-stu-id="40f3f-190">The following list shows the precedence hierarchy, from highest to lowest.</span></span>

1. <span data-ttu-id="40f3f-191">Métodos de extensión definidos dentro del módulo actual.</span><span class="sxs-lookup"><span data-stu-id="40f3f-191">Extension methods defined inside the current module.</span></span>

2. <span data-ttu-id="40f3f-192">Métodos de extensión definidos dentro de tipos de datos en el espacio de nombres actual o cualquiera de sus elementos primarios, con espacios de nombres secundarios con mayor precedencia que espacios de nombres primarios.</span><span class="sxs-lookup"><span data-stu-id="40f3f-192">Extension methods defined inside data types in the current namespace or any one of its parents, with child namespaces having higher precedence than parent namespaces.</span></span>

3. <span data-ttu-id="40f3f-193">Métodos de extensión definidos dentro de cualquier importación de tipo en el archivo actual.</span><span class="sxs-lookup"><span data-stu-id="40f3f-193">Extension methods defined inside any type imports in the current file.</span></span>

4. <span data-ttu-id="40f3f-194">Métodos de extensión definidos dentro de cualquier importación de espacio de nombres en el archivo actual.</span><span class="sxs-lookup"><span data-stu-id="40f3f-194">Extension methods defined inside any namespace imports in the current file.</span></span>

5. <span data-ttu-id="40f3f-195">Métodos de extensión definidos dentro de cualquier importación de tipo de nivel de proyecto.</span><span class="sxs-lookup"><span data-stu-id="40f3f-195">Extension methods defined inside any project-level type imports.</span></span>

6. <span data-ttu-id="40f3f-196">Métodos de extensión definidos dentro de cualquier importación de espacio de nombres de nivel de proyecto.</span><span class="sxs-lookup"><span data-stu-id="40f3f-196">Extension methods defined inside any project-level namespace imports.</span></span>

<span data-ttu-id="40f3f-197">Si la precedencia no resuelve la ambigüedad, puede usar el nombre completo para especificar el método al que está llamando.</span><span class="sxs-lookup"><span data-stu-id="40f3f-197">If precedence does not resolve the ambiguity, you can use the fully qualified name to specify the method that you are calling.</span></span> <span data-ttu-id="40f3f-198">Si el `Print` método del ejemplo anterior se define en un módulo denominado `StringExtensions` , el nombre completo es `StringExtensions.Print(example)` en lugar de `example.Print()` .</span><span class="sxs-lookup"><span data-stu-id="40f3f-198">If the `Print` method in the earlier example is defined in a module named `StringExtensions`, the fully qualified name is `StringExtensions.Print(example)` instead of `example.Print()`.</span></span>

## <a name="see-also"></a><span data-ttu-id="40f3f-199">Consulte también</span><span class="sxs-lookup"><span data-stu-id="40f3f-199">See also</span></span>

- <xref:System.Runtime.CompilerServices>
- <xref:System.Runtime.CompilerServices.ExtensionAttribute>
- [<span data-ttu-id="40f3f-200">Métodos de extensión</span><span class="sxs-lookup"><span data-stu-id="40f3f-200">Extension Methods</span></span>](../../../../csharp/programming-guide/classes-and-structs/extension-methods.md)
- [<span data-ttu-id="40f3f-201">Module (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="40f3f-201">Module Statement</span></span>](../../../language-reference/statements/module-statement.md)
- [<span data-ttu-id="40f3f-202">Argumentos y parámetros de procedimiento</span><span class="sxs-lookup"><span data-stu-id="40f3f-202">Procedure Parameters and Arguments</span></span>](procedure-parameters-and-arguments.md)
- [<span data-ttu-id="40f3f-203">Parámetros opcionales</span><span class="sxs-lookup"><span data-stu-id="40f3f-203">Optional Parameters</span></span>](optional-parameters.md)
- [<span data-ttu-id="40f3f-204">Matrices de parámetros</span><span class="sxs-lookup"><span data-stu-id="40f3f-204">Parameter Arrays</span></span>](parameter-arrays.md)
- [<span data-ttu-id="40f3f-205">Información general de atributos</span><span class="sxs-lookup"><span data-stu-id="40f3f-205">Attributes overview</span></span>](../../concepts/attributes/index.md)
- [<span data-ttu-id="40f3f-206">Ámbito en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="40f3f-206">Scope in Visual Basic</span></span>](../declared-elements/scope.md)
