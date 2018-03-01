---
title: "Métodos de extensión (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.ExtensionMethods
helpviewer_keywords:
- extending data types [Visual Basic]
- extension methods [Visual Basic]
ms.assetid: b8020aae-374d-46a9-bcb7-8cc2390b93b6
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d3db3bc2b213b78ef2dceebcf56c9d5fbfa3016e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="extension-methods-visual-basic"></a><span data-ttu-id="30b67-102">Métodos de extensión (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="30b67-102">Extension Methods (Visual Basic)</span></span>
<span data-ttu-id="30b67-103">Métodos de extensión permiten a los programadores agregar funcionalidad personalizada a los tipos de datos que ya se han definido sin crear un nuevo tipo derivado.</span><span class="sxs-lookup"><span data-stu-id="30b67-103">Extension methods enable developers to add custom functionality to data types that are already defined without creating a new derived type.</span></span> <span data-ttu-id="30b67-104">Métodos de extensión permiten escribir un método que se pueda llamar como si fuera un método de instancia del tipo existente.</span><span class="sxs-lookup"><span data-stu-id="30b67-104">Extension methods make it possible to write a method that can be called as if it were an instance method of the existing type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="30b67-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="30b67-105">Remarks</span></span>  
 <span data-ttu-id="30b67-106">Un método de extensión puede ser solo un `Sub` procedimiento o una `Function` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="30b67-106">An extension method can be only a `Sub` procedure or a `Function` procedure.</span></span> <span data-ttu-id="30b67-107">No se puede definir una propiedad de extensión, el campo o el evento.</span><span class="sxs-lookup"><span data-stu-id="30b67-107">You cannot define an extension property, field, or event.</span></span> <span data-ttu-id="30b67-108">Todos los métodos de extensión se deben marcar con el atributo de extensión `<Extension()>` desde el <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="30b67-108">All extension methods must be marked with the extension attribute `<Extension()>` from the <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> namespace.</span></span>  
  
 <span data-ttu-id="30b67-109">El primer parámetro en una definición de método de extensión especifica el tipo de datos que extiende el método.</span><span class="sxs-lookup"><span data-stu-id="30b67-109">The first parameter in an extension method definition specifies which data type the method extends.</span></span> <span data-ttu-id="30b67-110">Cuando se ejecuta el método, el primer parámetro se enlaza a la instancia del tipo de datos que invoca el método.</span><span class="sxs-lookup"><span data-stu-id="30b67-110">When the method is run, the first parameter is bound to the instance of the data type that invokes the method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="30b67-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="30b67-111">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="30b67-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="30b67-112">Description</span></span>  
 <span data-ttu-id="30b67-113">En el ejemplo siguiente se define un `Print` extensión a la <xref:System.String> tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="30b67-113">The following example defines a `Print` extension to the <xref:System.String> data type.</span></span> <span data-ttu-id="30b67-114">El método usa `Console.WriteLine` para mostrar una cadena.</span><span class="sxs-lookup"><span data-stu-id="30b67-114">The method uses `Console.WriteLine` to display a string.</span></span> <span data-ttu-id="30b67-115">El parámetro de la `Print` método `aString`, Establece que el método extiende la <xref:System.String> clase.</span><span class="sxs-lookup"><span data-stu-id="30b67-115">The parameter of the `Print` method, `aString`, establishes that the method extends the <xref:System.String> class.</span></span>  
  
 [!code-vb[VbVbalrExtensionMethods#1](./codesnippet/VisualBasic/extension-methods_1.vb)]  
  
 <span data-ttu-id="30b67-116">Tenga en cuenta que la definición de método de extensión se marca con el atributo de extensión `<Extension()>`.</span><span class="sxs-lookup"><span data-stu-id="30b67-116">Notice that the extension method definition is marked with the extension attribute `<Extension()>`.</span></span> <span data-ttu-id="30b67-117">Marcar el módulo en el que se define el método es opcional, pero se debe marcar cada método de extensión.</span><span class="sxs-lookup"><span data-stu-id="30b67-117">Marking the module in which the method is defined is optional, but each extension method must be marked.</span></span> <span data-ttu-id="30b67-118"><xref:System.Runtime.CompilerServices>se debe importar con el fin de obtener acceso al atributo de extensión.</span><span class="sxs-lookup"><span data-stu-id="30b67-118"><xref:System.Runtime.CompilerServices> must be imported in order to access the extension attribute.</span></span>  
  
 <span data-ttu-id="30b67-119">Métodos de extensión se pueden declarar únicamente dentro de los módulos.</span><span class="sxs-lookup"><span data-stu-id="30b67-119">Extension methods can be declared only within modules.</span></span> <span data-ttu-id="30b67-120">Normalmente, el módulo en el que se define un método de extensión no es el mismo módulo que el uno en el que se llama.</span><span class="sxs-lookup"><span data-stu-id="30b67-120">Typically, the module in which an extension method is defined is not the same module as the one in which it is called.</span></span> <span data-ttu-id="30b67-121">En su lugar, se importa el módulo que contiene el método de extensión, si es necesario que, para volver a ponerlo en el ámbito.</span><span class="sxs-lookup"><span data-stu-id="30b67-121">Instead, the module that contains the extension method is imported, if it needs to be, to bring it into scope.</span></span> <span data-ttu-id="30b67-122">Después del módulo que contiene `Print` está en el ámbito, se puede llamar al método como si fuera un método de instancia normal que no toma ningún argumento, como `ToUpper`:</span><span class="sxs-lookup"><span data-stu-id="30b67-122">After the module that contains `Print` is in scope, the method can be called as if it were an ordinary instance method that takes no arguments, such as `ToUpper`:</span></span>  
  
 [!code-vb[VbVbalrExtensionMethods#2](./codesnippet/VisualBasic/extension-methods_2.vb)]  
  
 <span data-ttu-id="30b67-123">El ejemplo siguiente, `PrintAndPunctuate`, también es una extensión <xref:System.String>, pero esta vez definida con dos parámetros.</span><span class="sxs-lookup"><span data-stu-id="30b67-123">The next example, `PrintAndPunctuate`, is also an extension to <xref:System.String>, this time defined with two parameters.</span></span> <span data-ttu-id="30b67-124">El primer parámetro, `aString`, Establece que el método de extensión extiende <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="30b67-124">The first parameter, `aString`, establishes that the extension method extends <xref:System.String>.</span></span> <span data-ttu-id="30b67-125">El segundo parámetro, `punc`, está diseñada para ser una cadena de signos de puntuación que se pasa como argumento cuando se llama al método.</span><span class="sxs-lookup"><span data-stu-id="30b67-125">The second parameter, `punc`, is intended to be a string of punctuation marks that is passed in as an argument when the method is called.</span></span> <span data-ttu-id="30b67-126">El método muestra la cadena seguida de los signos de puntuación.</span><span class="sxs-lookup"><span data-stu-id="30b67-126">The method displays the string followed by the punctuation marks.</span></span>  
  
 [!code-vb[VbVbalrExtensionMethods#3](./codesnippet/VisualBasic/extension-methods_3.vb)]  
  
 <span data-ttu-id="30b67-127">Se llama al método mediante el envío de un argumento de cadena para `punc`:`example.PrintAndPunctuate(".")`</span><span class="sxs-lookup"><span data-stu-id="30b67-127">The method is called by sending in a string argument for `punc`: `example.PrintAndPunctuate(".")`</span></span>  
  
 <span data-ttu-id="30b67-128">El ejemplo siguiente muestra `Print` y `PrintAndPunctuate` define y llama.</span><span class="sxs-lookup"><span data-stu-id="30b67-128">The following example shows `Print` and `PrintAndPunctuate` defined and called.</span></span> <span data-ttu-id="30b67-129"><xref:System.Runtime.CompilerServices>se importa en el módulo de definición para habilitar el acceso al atributo de extensión.</span><span class="sxs-lookup"><span data-stu-id="30b67-129"><xref:System.Runtime.CompilerServices> is imported in the definition module in order to enable access to the extension attribute.</span></span>  
  
### <a name="code"></a><span data-ttu-id="30b67-130">Código</span><span class="sxs-lookup"><span data-stu-id="30b67-130">Code</span></span>  
  
```vb  
Imports System.Runtime.CompilerServices  
  
Module StringExtensions  
  
    <Extension()>   
    Public Sub Print(ByVal aString As String)  
        Console.WriteLine(aString)  
    End Sub  
  
    <Extension()>   
    Public Sub PrintAndPunctuate(ByVal aString As String,   
                                 ByVal punc As String)  
        Console.WriteLine(aString & punc)  
    End Sub  
  
End Module  
```  
  
 <span data-ttu-id="30b67-131">A continuación, los métodos de extensión se incluyen en el ámbito y se llama.</span><span class="sxs-lookup"><span data-stu-id="30b67-131">Next, the extension methods are brought into scope and called.</span></span>  
  
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
  
### <a name="comments"></a><span data-ttu-id="30b67-132">Comentarios</span><span class="sxs-lookup"><span data-stu-id="30b67-132">Comments</span></span>  
 <span data-ttu-id="30b67-133">Todo lo que son necesaria que sea capaz de ejecutar estos o métodos de extensión similares es que estén en el ámbito.</span><span class="sxs-lookup"><span data-stu-id="30b67-133">All that is required to be able to run these or similar extension methods is that they be in scope.</span></span> <span data-ttu-id="30b67-134">Si el módulo que contiene un método de extensión está en el ámbito, está visible en IntelliSense y puede llamarse como si fuera un método de instancia normal.</span><span class="sxs-lookup"><span data-stu-id="30b67-134">If the module that contains an extension method is in scope, it is visible in IntelliSense and can be called as if it were an ordinary instance method.</span></span>  
  
 <span data-ttu-id="30b67-135">Tenga en cuenta que cuando se invocan los métodos, se envía ningún argumento para el primer parámetro.</span><span class="sxs-lookup"><span data-stu-id="30b67-135">Notice that when the methods are invoked, no argument is sent in for the first parameter.</span></span> <span data-ttu-id="30b67-136">Parámetro `aString` en el método anterior definiciones se enlaza a `example`, la instancia de `String` que llama.</span><span class="sxs-lookup"><span data-stu-id="30b67-136">Parameter `aString` in the previous method definitions is bound to `example`, the instance of `String` that calls them.</span></span> <span data-ttu-id="30b67-137">El compilador usa `example` como el argumento enviado al primer parámetro.</span><span class="sxs-lookup"><span data-stu-id="30b67-137">The compiler will use `example` as the argument sent to the first parameter.</span></span>  
  
 <span data-ttu-id="30b67-138">Si se llama a un método de extensión para un objeto que se establece en `Nothing`, se ejecuta el método de extensión.</span><span class="sxs-lookup"><span data-stu-id="30b67-138">If an extension method is called for an object that is set to `Nothing`, the extension method executes.</span></span> <span data-ttu-id="30b67-139">Esto no se aplica a los métodos de instancia normal.</span><span class="sxs-lookup"><span data-stu-id="30b67-139">This does not apply to ordinary instance methods.</span></span> <span data-ttu-id="30b67-140">Puede comprobar explícitamente si hay `Nothing` en el método de extensión.</span><span class="sxs-lookup"><span data-stu-id="30b67-140">You can explicitly check for `Nothing` in the extension method.</span></span>  
  
## <a name="types-that-can-be-extended"></a><span data-ttu-id="30b67-141">Tipos que se pueden extender</span><span class="sxs-lookup"><span data-stu-id="30b67-141">Types That Can Be Extended</span></span>  
 <span data-ttu-id="30b67-142">Puede definir un método de extensión en la mayoría de los tipos que se puede representar en una lista de parámetros de Visual Basic, incluidas las siguientes:</span><span class="sxs-lookup"><span data-stu-id="30b67-142">You can define an extension method on most types that can be represented in a Visual Basic parameter list, including the following:</span></span>  
  
-   <span data-ttu-id="30b67-143">Clases (tipos de referencia)</span><span class="sxs-lookup"><span data-stu-id="30b67-143">Classes (reference types)</span></span>  
  
-   <span data-ttu-id="30b67-144">Estructuras (tipos de valor)</span><span class="sxs-lookup"><span data-stu-id="30b67-144">Structures (value types)</span></span>  
  
-   <span data-ttu-id="30b67-145">Interfaces</span><span class="sxs-lookup"><span data-stu-id="30b67-145">Interfaces</span></span>  
  
-   <span data-ttu-id="30b67-146">Delegados</span><span class="sxs-lookup"><span data-stu-id="30b67-146">Delegates</span></span>  
  
-   <span data-ttu-id="30b67-147">Argumentos ByRef y ByVal</span><span class="sxs-lookup"><span data-stu-id="30b67-147">ByRef and ByVal arguments</span></span>  
  
-   <span data-ttu-id="30b67-148">Parámetros de método genérico</span><span class="sxs-lookup"><span data-stu-id="30b67-148">Generic method parameters</span></span>  
  
-   <span data-ttu-id="30b67-149">Matrices</span><span class="sxs-lookup"><span data-stu-id="30b67-149">Arrays</span></span>  
  
 <span data-ttu-id="30b67-150">Dado que el primer parámetro especifica el tipo de datos que extiende el método de extensión, es necesario y no puede ser opcional.</span><span class="sxs-lookup"><span data-stu-id="30b67-150">Because the first parameter specifies the data type that the extension method extends, it is required and cannot be optional.</span></span> <span data-ttu-id="30b67-151">Por esta razón, `Optional` parámetros y `ParamArray` parámetros no pueden ser el primer parámetro de la lista de parámetros.</span><span class="sxs-lookup"><span data-stu-id="30b67-151">For that reason, `Optional` parameters and `ParamArray` parameters cannot be the first parameter in the parameter list.</span></span>  
  
 <span data-ttu-id="30b67-152">Métodos de extensión no se consideran en el enlace más tarde.</span><span class="sxs-lookup"><span data-stu-id="30b67-152">Extension methods are not considered in late binding.</span></span> <span data-ttu-id="30b67-153">En el ejemplo siguiente, la instrucción `anObject.PrintMe()` genera un <xref:System.MissingMemberException> excepción, la misma excepción que vería si el segundo `PrintMe` definición de método de extensión se eliminaron.</span><span class="sxs-lookup"><span data-stu-id="30b67-153">In the following example, the statement `anObject.PrintMe()` raises a <xref:System.MissingMemberException> exception, the same exception you would see if the second `PrintMe` extension method definition were deleted.</span></span>  
  
 [!code-vb[VbVbalrExtensionMethods#9](./codesnippet/VisualBasic/extension-methods_4.vb)]  
  
## <a name="best-practices"></a><span data-ttu-id="30b67-154">Procedimientos recomendados</span><span class="sxs-lookup"><span data-stu-id="30b67-154">Best Practices</span></span>  
 <span data-ttu-id="30b67-155">Métodos de extensión proporcionan una manera eficaz y conveniente para extender un tipo existente.</span><span class="sxs-lookup"><span data-stu-id="30b67-155">Extension methods provide a convenient and powerful way to extend an existing type.</span></span> <span data-ttu-id="30b67-156">Sin embargo, para poder utilizarlos correctamente, hay algunos puntos a tener en cuenta.</span><span class="sxs-lookup"><span data-stu-id="30b67-156">However, to use them successfully, there are some points to consider.</span></span> <span data-ttu-id="30b67-157">Estas consideraciones se aplican principalmente a los autores de bibliotecas de clases, pero podrían afectar a cualquier aplicación que utilice los métodos de extensión.</span><span class="sxs-lookup"><span data-stu-id="30b67-157">These considerations apply mainly to authors of class libraries, but they might affect any application that uses extension methods.</span></span>  
  
 <span data-ttu-id="30b67-158">Más generalmente, los métodos de extensión que se agregan a los tipos que no poseen son más vulnerables que agregó a tipos que controlan los métodos de extensión.</span><span class="sxs-lookup"><span data-stu-id="30b67-158">Most generally, extension methods that you add to types that you do not own are more vulnerable than extension methods added to types that you control.</span></span> <span data-ttu-id="30b67-159">Se pueden producir varios significados en clases no es propietario que pueden interferir con los métodos de extensión.</span><span class="sxs-lookup"><span data-stu-id="30b67-159">A number of things can occur in classes you do not own that can interfere with your extension methods.</span></span>  
  
-   <span data-ttu-id="30b67-160">Si existe cualquier miembro de instancia accesible que tenga una firma que es compatible con los argumentos en la instrucción que realiza la llamada, con no necesarias del argumento al parámetro de las conversiones de restricción, se utilizará el método de instancia con preferencia a cualquier método de extensión.</span><span class="sxs-lookup"><span data-stu-id="30b67-160">If any accessible instance member exists that has a signature that is compatible with the arguments in the calling statement, with no narrowing conversions required from argument to parameter, the instance method will be used in preference to any extension method.</span></span> <span data-ttu-id="30b67-161">Por lo tanto, si un método de instancia adecuado se agrega a una clase en algún momento, un miembro de extensión existente que se basan en puede quedar inaccesible.</span><span class="sxs-lookup"><span data-stu-id="30b67-161">Therefore, if an appropriate instance method is added to a class at some point, an existing extension member that you rely on may become inaccessible.</span></span>  
  
-   <span data-ttu-id="30b67-162">El autor de un método de extensión no puede impedir que otros programadores escribir métodos de extensión en conflicto que pueden tener prioridad sobre la extensión original.</span><span class="sxs-lookup"><span data-stu-id="30b67-162">The author of an extension method cannot prevent other programmers from writing conflicting extension methods that may have precedence over the original extension.</span></span>  
  
-   <span data-ttu-id="30b67-163">Puede mejorar la solidez colocando los métodos de extensión en su propio espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="30b67-163">You can improve robustness by putting extension methods in their own namespace.</span></span> <span data-ttu-id="30b67-164">Los consumidores de la biblioteca, a continuación, pueden incluir un espacio de nombres o excluirla o seleccionar entre los espacios de nombres, independientemente del resto de la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="30b67-164">Consumers of your library can then include a namespace or exclude it, or select among namespaces, separately from the rest of the library.</span></span>  
  
-   <span data-ttu-id="30b67-165">Puede ser más seguro extender interfaces de es extender clases, especialmente si no posee la interfaz o clase.</span><span class="sxs-lookup"><span data-stu-id="30b67-165">It may be safer to extend interfaces than it is to extend classes, especially if you do not own the interface or class.</span></span> <span data-ttu-id="30b67-166">Un cambio en una interfaz afecta a cada clase que lo implemente.</span><span class="sxs-lookup"><span data-stu-id="30b67-166">A change in an interface affects every class that implements it.</span></span> <span data-ttu-id="30b67-167">Por lo tanto, el autor puede ser menos probable que agregar o cambiar los métodos en una interfaz.</span><span class="sxs-lookup"><span data-stu-id="30b67-167">Therefore, the author may be less likely to add or change methods in an interface.</span></span> <span data-ttu-id="30b67-168">Sin embargo, si una clase implementa dos interfaces que tienen métodos de extensión con la misma firma, ninguno de los métodos extensión está visible.</span><span class="sxs-lookup"><span data-stu-id="30b67-168">However, if a class implements two interfaces that have extension methods with the same signature, neither extension method is visible.</span></span>  
  
-   <span data-ttu-id="30b67-169">Ampliar el tipo más específico que puede.</span><span class="sxs-lookup"><span data-stu-id="30b67-169">Extend the most specific type you can.</span></span> <span data-ttu-id="30b67-170">En una jerarquía de tipos, si selecciona un tipo desde el que se derivan muchos otros tipos, hay niveles de posibilidades para la inclusión de métodos de instancia u otros métodos de extensión que podrían interferir con el suyo.</span><span class="sxs-lookup"><span data-stu-id="30b67-170">In a hierarchy of types, if you select a type from which many other types are derived, there are layers of possibilities for the introduction of instance methods or other extension methods that might interfere with yours.</span></span>  
  
## <a name="extension-methods-instance-methods-and-properties"></a><span data-ttu-id="30b67-171">Propiedades, métodos de instancia y métodos de extensión</span><span class="sxs-lookup"><span data-stu-id="30b67-171">Extension Methods, Instance Methods, and Properties</span></span>  
 <span data-ttu-id="30b67-172">Cuando un método de instancia en el ámbito tiene una firma que es compatible con los argumentos de una instrucción de llamada, se elige el método de instancia con preferencia a cualquier método de extensión.</span><span class="sxs-lookup"><span data-stu-id="30b67-172">When an in-scope instance method has a signature that is compatible with the arguments of a calling statement, the instance method is chosen in preference to any extension method.</span></span> <span data-ttu-id="30b67-173">El método de instancia tiene prioridad incluso si el método de extensión es una coincidencia mejor.</span><span class="sxs-lookup"><span data-stu-id="30b67-173">The instance method has precedence even if the extension method is a better match.</span></span> <span data-ttu-id="30b67-174">En el ejemplo siguiente, `ExampleClass` contiene un método de instancia llamado `ExampleMethod` que tiene un parámetro de tipo `Integer`.</span><span class="sxs-lookup"><span data-stu-id="30b67-174">In the following example, `ExampleClass` contains an instance method named `ExampleMethod` that has one parameter of type `Integer`.</span></span> <span data-ttu-id="30b67-175">Método de extensión `ExampleMethod` extiende `ExampleClass`, y tiene un parámetro de tipo `Long`.</span><span class="sxs-lookup"><span data-stu-id="30b67-175">Extension method `ExampleMethod` extends `ExampleClass`, and has one parameter of type `Long`.</span></span>  
  
 [!code-vb[VbVbalrExtensionMethods#4](./codesnippet/VisualBasic/extension-methods_5.vb)]  
  
 <span data-ttu-id="30b67-176">La primera llamada a `ExampleMethod` en el código siguiente llama al método de extensión, porque `arg1` es `Long` y sólo es compatible con la `Long` parámetro del método de extensión.</span><span class="sxs-lookup"><span data-stu-id="30b67-176">The first call to `ExampleMethod` in the following code calls the extension method, because `arg1` is `Long` and is compatible only with the `Long` parameter in the extension method.</span></span> <span data-ttu-id="30b67-177">La segunda llamada a `ExampleMethod` tiene un `Integer` argumento, `arg2`, y llama al método de instancia.</span><span class="sxs-lookup"><span data-stu-id="30b67-177">The second call to `ExampleMethod` has an `Integer` argument, `arg2`, and it calls the instance method.</span></span>  
  
 [!code-vb[VbVbalrExtensionMethods#5](./codesnippet/VisualBasic/extension-methods_6.vb)]  
  
 <span data-ttu-id="30b67-178">Ahora invierta los tipos de datos de los parámetros en los dos métodos:</span><span class="sxs-lookup"><span data-stu-id="30b67-178">Now reverse the data types of the parameters in the two methods:</span></span>  
  
 [!code-vb[VbVbalrExtensionMethods#6](./codesnippet/VisualBasic/extension-methods_7.vb)]  
  
 <span data-ttu-id="30b67-179">En el código en esta ocasión `Main` dos veces que se llama al método.</span><span class="sxs-lookup"><span data-stu-id="30b67-179">This time the code in `Main` calls the instance method both times.</span></span> <span data-ttu-id="30b67-180">Esto es porque ambos `arg1` y `arg2` tiene una conversión de ampliación a `Long`, y el método de instancia tiene prioridad sobre el método de extensión en ambos casos.</span><span class="sxs-lookup"><span data-stu-id="30b67-180">This is because both `arg1` and `arg2` have a widening conversion to `Long`, and the instance method takes precedence over the extension method in both cases.</span></span>  
  
 [!code-vb[VbVbalrExtensionMethods#7](./codesnippet/VisualBasic/extension-methods_8.vb)]  
  
 <span data-ttu-id="30b67-181">Por lo tanto, un método de extensión no puede reemplazar un método de instancia existente.</span><span class="sxs-lookup"><span data-stu-id="30b67-181">Therefore, an extension method cannot replace an existing instance method.</span></span> <span data-ttu-id="30b67-182">Sin embargo, cuando un método de extensión tiene el mismo nombre que un método de instancia, pero las firmas no entran en conflicto, ambos métodos son accesibles.</span><span class="sxs-lookup"><span data-stu-id="30b67-182">However, when an extension method has the same name as an instance method but the signatures do not conflict, both methods can be accessed.</span></span> <span data-ttu-id="30b67-183">Por ejemplo, si clase `ExampleClass` contiene un método denominado `ExampleMethod` que toma ningún argumento, los métodos de extensión con el mismo nombre pero se permiten firmas diferentes, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="30b67-183">For example, if class `ExampleClass` contains a method named `ExampleMethod` that takes no arguments, extension methods with the same name but different signatures are permitted, as shown in the following code.</span></span>  
  
 [!code-vb[VbVbalrExtensionMethods#8](./codesnippet/VisualBasic/extension-methods_9.vb)]  
  
 <span data-ttu-id="30b67-184">El resultado de este código es como sigue:</span><span class="sxs-lookup"><span data-stu-id="30b67-184">The output from this code is as follows:</span></span>  
  
 `Extension method`  
  
 `Instance method`  
  
 <span data-ttu-id="30b67-185">La situación es más fácil con propiedades: si un método de extensión tiene el mismo nombre que una propiedad de la clase que extiende, el método de extensión no está visible y no son accesibles.</span><span class="sxs-lookup"><span data-stu-id="30b67-185">The situation is simpler with properties: if an extension method has the same name as a property of the class it extends, the extension method is not visible and cannot be accessed.</span></span>  
  
## <a name="extension-method-precedence"></a><span data-ttu-id="30b67-186">Prioridad del método de extensión</span><span class="sxs-lookup"><span data-stu-id="30b67-186">Extension Method Precedence</span></span>  
 <span data-ttu-id="30b67-187">Cuando dos métodos de extensión que tienen firmas idénticas están en el ámbito y son accesibles, se invocará el uno con prioridad más alta.</span><span class="sxs-lookup"><span data-stu-id="30b67-187">When two extension methods that have identical signatures are in scope and accessible, the one with higher precedence will be invoked.</span></span> <span data-ttu-id="30b67-188">Prioridad de un método de extensión se basa en el mecanismo utilizado para devolver el método en el ámbito.</span><span class="sxs-lookup"><span data-stu-id="30b67-188">An extension method's precedence is based on the mechanism used to bring the method into scope.</span></span> <span data-ttu-id="30b67-189">En la lista siguiente muestra la jerarquía de prioridad, de mayor a menor.</span><span class="sxs-lookup"><span data-stu-id="30b67-189">The following list shows the precedence hierarchy, from highest to lowest.</span></span>  
  
1.  <span data-ttu-id="30b67-190">Métodos de extensión definidos dentro del módulo actual.</span><span class="sxs-lookup"><span data-stu-id="30b67-190">Extension methods defined inside the current module.</span></span>  
  
2.  <span data-ttu-id="30b67-191">Métodos de extensión definen dentro de datos tipos en el espacio de nombres actual o cualquiera de sus elementos primarios, con espacios de nombres secundarios tener mayor prioridad que los espacios de nombres primario.</span><span class="sxs-lookup"><span data-stu-id="30b67-191">Extension methods defined inside data types in the current namespace or any one of its parents, with child namespaces having higher precedence than parent namespaces.</span></span>  
  
3.  <span data-ttu-id="30b67-192">Métodos de extensión definidos dentro de cualquier tipo de importaciones del archivo actual.</span><span class="sxs-lookup"><span data-stu-id="30b67-192">Extension methods defined inside any type imports in the current file.</span></span>  
  
4.  <span data-ttu-id="30b67-193">Métodos de extensión definidos dentro de cualquier importación de espacio de nombres en el archivo actual.</span><span class="sxs-lookup"><span data-stu-id="30b67-193">Extension methods defined inside any namespace imports in the current file.</span></span>  
  
5.  <span data-ttu-id="30b67-194">Métodos de extensión definidos dentro de cualquier tipo de nivel de proyecto de importaciones.</span><span class="sxs-lookup"><span data-stu-id="30b67-194">Extension methods defined inside any project-level type imports.</span></span>  
  
6.  <span data-ttu-id="30b67-195">Métodos de extensión definidos dentro de cualquier importación de espacio de nombres de nivel de proyecto.</span><span class="sxs-lookup"><span data-stu-id="30b67-195">Extension methods defined inside any project-level namespace imports.</span></span>  
  
 <span data-ttu-id="30b67-196">Si la prioridad no resolver la ambigüedad, puede usar el nombre completo para especificar el método que está llamando.</span><span class="sxs-lookup"><span data-stu-id="30b67-196">If precedence does not resolve the ambiguity, you can use the fully qualified name to specify the method that you are calling.</span></span> <span data-ttu-id="30b67-197">Si el `Print` método en el ejemplo anterior se define en un módulo denominado `StringExtensions`, el nombre completo es `StringExtensions.Print(example)` en lugar de `example.Print()`.</span><span class="sxs-lookup"><span data-stu-id="30b67-197">If the `Print` method in the earlier example is defined in a module named `StringExtensions`, the fully qualified name is `StringExtensions.Print(example)` instead of `example.Print()`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30b67-198">Vea también</span><span class="sxs-lookup"><span data-stu-id="30b67-198">See Also</span></span>  
 <xref:System.Runtime.CompilerServices>  
 <xref:System.Runtime.CompilerServices.ExtensionAttribute>  
 [<span data-ttu-id="30b67-199">Métodos de extensión</span><span class="sxs-lookup"><span data-stu-id="30b67-199">Extension Methods</span></span>](../../../../csharp/programming-guide/classes-and-structs/extension-methods.md)  
 [<span data-ttu-id="30b67-200">Module (instrucción)</span><span class="sxs-lookup"><span data-stu-id="30b67-200">Module Statement</span></span>](../../../../visual-basic/language-reference/statements/module-statement.md)  
 [<span data-ttu-id="30b67-201">Argumentos y parámetros de procedimiento</span><span class="sxs-lookup"><span data-stu-id="30b67-201">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="30b67-202">Parámetros opcionales</span><span class="sxs-lookup"><span data-stu-id="30b67-202">Optional Parameters</span></span>](./optional-parameters.md)  
 [<span data-ttu-id="30b67-203">Matrices de parámetros</span><span class="sxs-lookup"><span data-stu-id="30b67-203">Parameter Arrays</span></span>](./parameter-arrays.md)  
 [<span data-ttu-id="30b67-204">Información general de atributos</span><span class="sxs-lookup"><span data-stu-id="30b67-204">Attributes overview</span></span>](../../../../visual-basic/programming-guide/concepts/attributes/index.md)  
 [<span data-ttu-id="30b67-205">Ámbito en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="30b67-205">Scope in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
