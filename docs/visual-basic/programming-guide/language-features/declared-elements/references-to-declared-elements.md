---
description: 'Más información sobre: referencias a elementos declarados (Visual Basic)'
title: References to Declared Elements
ms.date: 07/20/2015
helpviewer_keywords:
- declared elements [Visual Basic]
- references [Visual Basic], declared elements
- qualified names [Visual Basic]
ms.assetid: d6301709-f4cc-4b7a-b8ba-80898f14ab46
ms.openlocfilehash: 75cc05381f01af00ac75995739647810fb7ff1d7
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100471440"
---
# <a name="references-to-declared-elements-visual-basic"></a><span data-ttu-id="e8d36-103">Referencias a elementos declarados (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e8d36-103">References to Declared Elements (Visual Basic)</span></span>

<span data-ttu-id="e8d36-104">Cuando el código hace referencia a un elemento declarado, el compilador Visual Basic coincide con el nombre de la referencia a la declaración adecuada de ese nombre.</span><span class="sxs-lookup"><span data-stu-id="e8d36-104">When your code refers to a declared element, the Visual Basic compiler matches the name in your reference to the appropriate declaration of that name.</span></span> <span data-ttu-id="e8d36-105">Si se declara más de un elemento con el mismo nombre, puede controlar a qué elementos se va a hacer referencia *calificando* su nombre.</span><span class="sxs-lookup"><span data-stu-id="e8d36-105">If more than one element is declared with the same name, you can control which of those elements is to be referenced by *qualifying* its name.</span></span>  
  
 <span data-ttu-id="e8d36-106">El compilador intenta buscar una referencia de nombre a una declaración de nombre con el *ámbito más restringido*.</span><span class="sxs-lookup"><span data-stu-id="e8d36-106">The compiler attempts to match a name reference to a name declaration with the *narrowest scope*.</span></span> <span data-ttu-id="e8d36-107">Esto significa que comienza con el código que hace la referencia y funciona de forma saliente a través de los niveles sucesivos de elementos contenedores.</span><span class="sxs-lookup"><span data-stu-id="e8d36-107">This means it starts with the code making the reference and works outward through successive levels of containing elements.</span></span>  
  
 <span data-ttu-id="e8d36-108">En el ejemplo siguiente se muestran referencias a dos variables con el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="e8d36-108">The following example shows references to two variables with the same name.</span></span> <span data-ttu-id="e8d36-109">En el ejemplo se declaran dos variables, cada una de ellas con `totalCount` un nivel diferente de ámbito en el módulo `container` .</span><span class="sxs-lookup"><span data-stu-id="e8d36-109">The example declares two variables, each named `totalCount`, at different levels of scope in module `container`.</span></span> <span data-ttu-id="e8d36-110">Cuando el procedimiento se `showCount` muestra `totalCount` sin calificación, el compilador Visual Basic resuelve la referencia a la declaración con el ámbito más restringido, es decir, la declaración local dentro de `showCount` .</span><span class="sxs-lookup"><span data-stu-id="e8d36-110">When the procedure `showCount` displays `totalCount` without qualification, the Visual Basic compiler resolves the reference to the declaration with the narrowest scope, namely the local declaration inside `showCount`.</span></span> <span data-ttu-id="e8d36-111">Cuando se califica `totalCount` con el módulo contenedor `container` , el compilador resuelve la referencia a la declaración con el ámbito más amplio.</span><span class="sxs-lookup"><span data-stu-id="e8d36-111">When it qualifies `totalCount` with the containing module `container`, the compiler resolves the reference to the declaration with the broader scope.</span></span>  
  
```vb  
' Assume these two modules are both in the same assembly.  
Module container  
    Public totalCount As Integer = 1  
    Public Sub showCount()  
        Dim totalCount As Integer = 6000  
        ' The following statement displays the local totalCount (6000).  
        MsgBox("Unqualified totalCount is " & CStr(totalCount))  
        ' The following statement displays the module's totalCount (1).  
        MsgBox("container.totalCount is " & CStr(container.totalCount))  
    End Sub  
End Module  
Module callingModule  
    Public Sub displayCount()  
        container.showCount()  
        ' The following statement displays the containing module's totalCount (1).  
        MsgBox("container.totalCount is " & CStr(container.totalCount))  
    End Sub  
End Module  
```  
  
## <a name="qualifying-an-element-name"></a><span data-ttu-id="e8d36-112">Calificar un nombre de elemento</span><span class="sxs-lookup"><span data-stu-id="e8d36-112">Qualifying an Element Name</span></span>  

 <span data-ttu-id="e8d36-113">Si desea invalidar este proceso de búsqueda y especificar un nombre declarado en un ámbito más amplio, debe *calificar* el nombre con el elemento contenedor del ámbito más amplio.</span><span class="sxs-lookup"><span data-stu-id="e8d36-113">If you want to override this search process and specify a name declared in a broader scope, you must *qualify* the name with the containing element of the broader scope.</span></span> <span data-ttu-id="e8d36-114">En algunos casos, es posible que también tenga que calificar el elemento contenedor.</span><span class="sxs-lookup"><span data-stu-id="e8d36-114">In some cases, you might also have to qualify the containing element.</span></span>  
  
 <span data-ttu-id="e8d36-115">Calificar un nombre significa que lo antepone en la instrucción de origen con información que identifica dónde se define el elemento de destino.</span><span class="sxs-lookup"><span data-stu-id="e8d36-115">Qualifying a name means preceding it in your source statement with information that identifies where the target element is defined.</span></span> <span data-ttu-id="e8d36-116">Esta información se denomina *cadena de calificación*.</span><span class="sxs-lookup"><span data-stu-id="e8d36-116">This information is called a *qualification string*.</span></span> <span data-ttu-id="e8d36-117">Puede incluir uno o varios espacios de nombres y un módulo, clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="e8d36-117">It can include one or more namespaces and a module, class, or structure.</span></span>  
  
 <span data-ttu-id="e8d36-118">La cadena de calificación debe especificar de forma inequívoca el módulo, la clase o la estructura que contiene el elemento de destino.</span><span class="sxs-lookup"><span data-stu-id="e8d36-118">The qualification string should unambiguously specify the module, class, or structure containing the target element.</span></span> <span data-ttu-id="e8d36-119">A su vez, el contenedor se puede ubicar en otro elemento contenedor, normalmente un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="e8d36-119">The container might in turn be located in another containing element, usually a namespace.</span></span> <span data-ttu-id="e8d36-120">Es posible que deba incluir varios elementos contenedores en la cadena de calificación.</span><span class="sxs-lookup"><span data-stu-id="e8d36-120">You might need to include several containing elements in the qualification string.</span></span>  
  
#### <a name="to-access-a-declared-element-by-qualifying-its-name"></a><span data-ttu-id="e8d36-121">Para tener acceso a un elemento declarado calificando su nombre</span><span class="sxs-lookup"><span data-stu-id="e8d36-121">To access a declared element by qualifying its name</span></span>  
  
1. <span data-ttu-id="e8d36-122">Determine la ubicación en la que se ha definido el elemento.</span><span class="sxs-lookup"><span data-stu-id="e8d36-122">Determine the location in which the element has been defined.</span></span> <span data-ttu-id="e8d36-123">Esto puede incluir un espacio de nombres, o incluso una jerarquía de espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="e8d36-123">This might include a namespace, or even a hierarchy of namespaces.</span></span> <span data-ttu-id="e8d36-124">Dentro del espacio de nombres de nivel inferior, el elemento debe estar incluido en un módulo, una clase o una estructura.</span><span class="sxs-lookup"><span data-stu-id="e8d36-124">Within the lowest-level namespace, the element must be contained in a module, class, or structure.</span></span>  
  
    ```vb  
    ' Assume the following hierarchy exists outside your code.  
    Namespace outerSpace  
        Namespace innerSpace  
            Module holdsTotals  
                Public Structure totals  
                    Public thisTotal As Integer  
                    Public Shared grandTotal As Long  
                End Structure  
            End Module  
        End Namespace  
    End Namespace  
    ```  
  
2. <span data-ttu-id="e8d36-125">Determinar una ruta de acceso de calificación en función de la ubicación del elemento de destino.</span><span class="sxs-lookup"><span data-stu-id="e8d36-125">Determine a qualification path based on the target element's location.</span></span> <span data-ttu-id="e8d36-126">Comience con el espacio de nombres de nivel superior, continúe con el espacio de nombres de nivel más bajo y termine con el módulo, la clase o la estructura que contiene el elemento de destino.</span><span class="sxs-lookup"><span data-stu-id="e8d36-126">Start with the highest-level namespace, proceed to the lowest-level namespace, and end with the module, class, or structure containing the target element.</span></span> <span data-ttu-id="e8d36-127">Cada elemento de la ruta de acceso debe contener el elemento que le sigue.</span><span class="sxs-lookup"><span data-stu-id="e8d36-127">Each element in the path must contain the element that follows it.</span></span>  
  
     <span data-ttu-id="e8d36-128">`outerSpace` → `innerSpace` → `holdsTotals` → `totals`</span><span class="sxs-lookup"><span data-stu-id="e8d36-128">`outerSpace` → `innerSpace` → `holdsTotals` → `totals`</span></span>  
  
3. <span data-ttu-id="e8d36-129">Preparar la cadena de calificación para el elemento de destino.</span><span class="sxs-lookup"><span data-stu-id="e8d36-129">Prepare the qualification string for the target element.</span></span> <span data-ttu-id="e8d36-130">Coloque un punto ( `.` ) después de cada elemento de la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="e8d36-130">Place a period (`.`) after every element in the path.</span></span> <span data-ttu-id="e8d36-131">La aplicación debe tener acceso a todos los elementos de la cadena de calificación.</span><span class="sxs-lookup"><span data-stu-id="e8d36-131">Your application must have access to every element in your qualification string.</span></span>  
  
    ```vb  
    outerSpace.innerSpace.holdsTotals.totals.  
    ```  
  
4. <span data-ttu-id="e8d36-132">Escriba la expresión o instrucción de asignación que hace referencia al elemento de destino de la manera normal.</span><span class="sxs-lookup"><span data-stu-id="e8d36-132">Write the expression or assignment statement referring to the target element in the normal way.</span></span>  
  
    ```vb  
    grandTotal = 9000  
    ```  
  
5. <span data-ttu-id="e8d36-133">Anteponga el nombre del elemento de destino a la cadena de calificación.</span><span class="sxs-lookup"><span data-stu-id="e8d36-133">Precede the target element name with the qualification string.</span></span> <span data-ttu-id="e8d36-134">El nombre debe seguir inmediatamente al punto ( `.` ) que sigue al módulo, la clase o la estructura que contiene el elemento.</span><span class="sxs-lookup"><span data-stu-id="e8d36-134">The name should immediately follow the period (`.`) that follows the module, class, or structure that contains the element.</span></span>  
  
    ```vb  
    ' Assume the following module is part of your code.  
    Module accessGrandTotal  
        Public Sub setGrandTotal()  
            outerSpace.innerSpace.holdsTotals.totals.grandTotal = 9000  
        End Sub  
    End Module  
    ```  
  
6. <span data-ttu-id="e8d36-135">El compilador usa la cadena de calificación para encontrar una declaración clara y no ambigua a la que puede coincidir con la referencia del elemento de destino.</span><span class="sxs-lookup"><span data-stu-id="e8d36-135">The compiler uses the qualification string to find a clear, unambiguous declaration to which it can match the target element reference.</span></span>  
  
 <span data-ttu-id="e8d36-136">También podría tener que calificar una referencia de nombre si la aplicación tiene acceso a más de un elemento de programación con el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="e8d36-136">You might also have to qualify a name reference if your application has access to more than one programming element that has the same name.</span></span> <span data-ttu-id="e8d36-137">Por ejemplo, los <xref:System.Windows.Forms> <xref:System.Web.UI.WebControls> espacios de nombres y contienen una `Label` clase ( <xref:System.Windows.Forms.Label?displayProperty=nameWithType> y <xref:System.Web.UI.WebControls.Label?displayProperty=nameWithType> ).</span><span class="sxs-lookup"><span data-stu-id="e8d36-137">For example, the <xref:System.Windows.Forms> and <xref:System.Web.UI.WebControls> namespaces both contain a `Label` class (<xref:System.Windows.Forms.Label?displayProperty=nameWithType> and <xref:System.Web.UI.WebControls.Label?displayProperty=nameWithType>).</span></span> <span data-ttu-id="e8d36-138">Si su aplicación usa ambos o si define su propia `Label` clase, debe distinguir los diferentes `Label` objetos.</span><span class="sxs-lookup"><span data-stu-id="e8d36-138">If your application uses both, or if it defines its own `Label` class, you must distinguish the different `Label` objects.</span></span> <span data-ttu-id="e8d36-139">Incluya el espacio de nombres o el alias de importación en la declaración de variable.</span><span class="sxs-lookup"><span data-stu-id="e8d36-139">Include the namespace or import alias in the variable declaration.</span></span> <span data-ttu-id="e8d36-140">En el ejemplo siguiente se usa el alias de importación.</span><span class="sxs-lookup"><span data-stu-id="e8d36-140">The following example uses the import alias.</span></span>  
  
```vb  
' The following statement must precede all your declarations.  
Imports win = System.Windows.Forms, web = System.Web.UI.WebControls  
' The following statement references the Windows.Forms.Label class.  
Dim winLabel As New win.Label()  
```  
  
## <a name="members-of-other-containing-elements"></a><span data-ttu-id="e8d36-141">Miembros de otros elementos contenedores</span><span class="sxs-lookup"><span data-stu-id="e8d36-141">Members of Other Containing Elements</span></span>  

 <span data-ttu-id="e8d36-142">Cuando se usa un miembro no compartido de otra clase o estructura, primero se debe calificar el nombre del miembro con una variable o expresión que apunte a una instancia de la clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="e8d36-142">When you use a nonshared member of another class or structure, you must first qualify the member name with a variable or expression that points to an instance of the class or structure.</span></span> <span data-ttu-id="e8d36-143">En el ejemplo siguiente, `demoClass` es una instancia de una clase denominada `class1` .</span><span class="sxs-lookup"><span data-stu-id="e8d36-143">In the following example, `demoClass` is an instance of a class named `class1`.</span></span>  
  
```vb  
Dim demoClass As class1 = New class1()  
demoClass.someSub[(argumentlist)]  
```  
  
 <span data-ttu-id="e8d36-144">No se puede usar el propio nombre de clase para calificar a un miembro que no se [comparte](../../../language-reference/modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="e8d36-144">You cannot use the class name itself to qualify a member that is not [Shared](../../../language-reference/modifiers/shared.md).</span></span> <span data-ttu-id="e8d36-145">Primero debe crear una instancia en una variable de objeto (en este caso `demoClass` ) y luego hacer referencia a ella mediante el nombre de la variable.</span><span class="sxs-lookup"><span data-stu-id="e8d36-145">You must first create an instance in an object variable (in this case `demoClass`) and then reference it by the variable name.</span></span>  
  
 <span data-ttu-id="e8d36-146">Si una clase o estructura tiene un `Shared` miembro, puede calificar ese miembro con el nombre de la clase o la estructura, o con una variable o expresión que apunte a una instancia.</span><span class="sxs-lookup"><span data-stu-id="e8d36-146">If a class or structure has a `Shared` member, you can qualify that member either with the class or structure name or with a variable or expression that points to an instance.</span></span>  
  
 <span data-ttu-id="e8d36-147">Un módulo no tiene ninguna instancia independiente y todos sus miembros son `Shared` de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="e8d36-147">A module does not have any separate instances, and all its members are `Shared` by default.</span></span> <span data-ttu-id="e8d36-148">Por lo tanto, puede calificar un miembro de módulo con el nombre de módulo.</span><span class="sxs-lookup"><span data-stu-id="e8d36-148">Therefore, you qualify a module member with the module name.</span></span>  
  
 <span data-ttu-id="e8d36-149">En el ejemplo siguiente se muestran referencias completas a los procedimientos de miembros de módulo.</span><span class="sxs-lookup"><span data-stu-id="e8d36-149">The following example shows qualified references to module member procedures.</span></span> <span data-ttu-id="e8d36-150">En el ejemplo se declaran dos `Sub` procedimientos, ambos denominados `perform` , en módulos diferentes de un proyecto.</span><span class="sxs-lookup"><span data-stu-id="e8d36-150">The example declares two `Sub` procedures, both named `perform`, in different modules in a project.</span></span> <span data-ttu-id="e8d36-151">Cada una se puede especificar sin calificación dentro de su propio módulo, pero se debe calificar si se hace referencia a ella desde cualquier otra parte.</span><span class="sxs-lookup"><span data-stu-id="e8d36-151">Each one can be specified without qualification within its own module but must be qualified if referenced from anywhere else.</span></span> <span data-ttu-id="e8d36-152">Dado que la referencia final de no `module3` cumple los requisitos `perform` , el compilador no puede resolver esa referencia.</span><span class="sxs-lookup"><span data-stu-id="e8d36-152">Because the final reference in `module3` does not qualify `perform`, the compiler cannot resolve that reference.</span></span>  
  
```vb  
' Assume these three modules are all in the same assembly.  
Module module1  
    Public Sub perform()  
        MsgBox("module1.perform() now returning")  
    End Sub  
End Module  
Module module2  
    Public Sub perform()  
        MsgBox("module2.perform() now returning")  
    End Sub  
    Public Sub doSomething()  
        ' The following statement calls perform in module2, the active module.  
        perform()  
        ' The following statement calls perform in module1.  
        module1.perform()  
    End Sub  
End Module  
Module module3  
    Public Sub callPerform()  
        ' The following statement calls perform in module1.  
        module1.perform()  
        ' The following statement makes an unresolvable name reference  
        ' and therefore generates a COMPILER ERROR.  
        perform() ' INVALID statement  
    End Sub  
End Module  
```  
  
## <a name="references-to-projects"></a><span data-ttu-id="e8d36-153">Referencias a proyectos</span><span class="sxs-lookup"><span data-stu-id="e8d36-153">References to Projects</span></span>  

 <span data-ttu-id="e8d36-154">Para usar elementos [públicos](../../../language-reference/modifiers/public.md) definidos en otro proyecto, primero debe establecer una *referencia* al ensamblado o la biblioteca de tipos del proyecto.</span><span class="sxs-lookup"><span data-stu-id="e8d36-154">To use [Public](../../../language-reference/modifiers/public.md) elements defined in another project, you must first set a *reference* to that project's assembly or type library.</span></span> <span data-ttu-id="e8d36-155">Para establecer una referencia, haga clic en **Agregar referencia** en el menú **proyecto** o use la opción del compilador [de línea de comandos-Reference (Visual Basic)](../../../reference/command-line-compiler/reference.md) .</span><span class="sxs-lookup"><span data-stu-id="e8d36-155">To set a reference, click **Add Reference** on the **Project** menu, or use the [-reference (Visual Basic)](../../../reference/command-line-compiler/reference.md) command-line compiler option.</span></span>  
  
 <span data-ttu-id="e8d36-156">Por ejemplo, puede utilizar el modelo de objetos XML del .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e8d36-156">For example, you can use the XML object model of the .NET Framework.</span></span> <span data-ttu-id="e8d36-157">Si establece una referencia al espacio de <xref:System.Xml> nombres, puede declarar y usar cualquiera de sus clases, como <xref:System.Xml.XmlDocument> .</span><span class="sxs-lookup"><span data-stu-id="e8d36-157">If you set a reference to the <xref:System.Xml> namespace, you can declare and use any of its classes, such as <xref:System.Xml.XmlDocument>.</span></span> <span data-ttu-id="e8d36-158">En el ejemplo siguiente se utiliza <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="e8d36-158">The following example uses <xref:System.Xml.XmlDocument>.</span></span>  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As System.Xml.XmlDocument  
```  
  
## <a name="importing-containing-elements"></a><span data-ttu-id="e8d36-159">Importar elementos contenedores</span><span class="sxs-lookup"><span data-stu-id="e8d36-159">Importing Containing Elements</span></span>  

 <span data-ttu-id="e8d36-160">Puede usar la [instrucción Imports (espacio de nombres y tipo de .net)](../../../language-reference/statements/imports-statement-net-namespace-and-type.md) para *importar* los espacios de nombres que contienen los módulos o las clases que desea usar.</span><span class="sxs-lookup"><span data-stu-id="e8d36-160">You can use the [Imports Statement (.NET Namespace and Type)](../../../language-reference/statements/imports-statement-net-namespace-and-type.md) to *import* the namespaces that contain the modules or classes that you want to use.</span></span> <span data-ttu-id="e8d36-161">Esto le permite hacer referencia a los elementos definidos en un espacio de nombres importado sin calificar totalmente sus nombres.</span><span class="sxs-lookup"><span data-stu-id="e8d36-161">This enables you to refer to the elements defined in an imported namespace without fully qualifying their names.</span></span> <span data-ttu-id="e8d36-162">En el ejemplo siguiente se vuelve a escribir el ejemplo anterior para importar el <xref:System.Xml> espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="e8d36-162">The following example rewrites the previous example to import the <xref:System.Xml> namespace.</span></span>  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement must precede all your declarations.  
Imports System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As XmlDocument  
```  
  
 <span data-ttu-id="e8d36-163">Además, la `Imports` instrucción puede definir un *alias de importación* para cada espacio de nombres importado.</span><span class="sxs-lookup"><span data-stu-id="e8d36-163">In addition, the `Imports` statement can define an *import alias* for each imported namespace.</span></span> <span data-ttu-id="e8d36-164">Esto puede hacer que el código fuente sea más corto y más fácil de leer.</span><span class="sxs-lookup"><span data-stu-id="e8d36-164">This can make the source code shorter and easier to read.</span></span> <span data-ttu-id="e8d36-165">En el ejemplo siguiente se vuelve a escribir el ejemplo anterior para usarlo `xD` como alias del <xref:System.Xml> espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="e8d36-165">The following example rewrites the previous example to use `xD` as an alias for the <xref:System.Xml> namespace.</span></span>  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement must precede all your declarations.  
Imports xD = System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As xD.XmlDocument  
```  
  
 <span data-ttu-id="e8d36-166">La `Imports` instrucción no hace que los elementos de otros proyectos estén disponibles para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e8d36-166">The `Imports` statement does not make elements from other projects available to your application.</span></span> <span data-ttu-id="e8d36-167">Es decir, no se ocupa del establecimiento de una referencia.</span><span class="sxs-lookup"><span data-stu-id="e8d36-167">That is, it does not take the place of setting a reference.</span></span> <span data-ttu-id="e8d36-168">La importación de un espacio de nombres solo quita el requisito de calificar los nombres definidos en ese espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="e8d36-168">Importing a namespace just removes the requirement to qualify the names defined in that namespace.</span></span>  
  
 <span data-ttu-id="e8d36-169">También puede usar la `Imports` instrucción para importar módulos, clases, estructuras y enumeraciones.</span><span class="sxs-lookup"><span data-stu-id="e8d36-169">You can also use the `Imports` statement to import modules, classes, structures, and enumerations.</span></span> <span data-ttu-id="e8d36-170">Después, puede usar los miembros de estos elementos importados sin calificación.</span><span class="sxs-lookup"><span data-stu-id="e8d36-170">You can then use the members of such imported elements without qualification.</span></span> <span data-ttu-id="e8d36-171">Sin embargo, siempre debe calificar miembros no compartidos de clases y estructuras con una variable o una expresión que se evalúe como una instancia de la clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="e8d36-171">However, you must always qualify nonshared members of classes and structures with a variable or expression that evaluates to an instance of the class or structure.</span></span>  
  
## <a name="naming-guidelines"></a><span data-ttu-id="e8d36-172">Instrucciones de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="e8d36-172">Naming Guidelines</span></span>  

 <span data-ttu-id="e8d36-173">Cuando se definen dos o más elementos de programación con el mismo nombre, puede producirse una *ambigüedad de nombres* cuando el compilador intenta resolver una referencia a ese nombre.</span><span class="sxs-lookup"><span data-stu-id="e8d36-173">When you define two or more programming elements that have the same name, a *name ambiguity* can result when the compiler attempts to resolve a reference to that name.</span></span> <span data-ttu-id="e8d36-174">Si hay más de una definición en el ámbito, o si no hay ninguna definición en el ámbito, la referencia es irresoluble.</span><span class="sxs-lookup"><span data-stu-id="e8d36-174">If more than one definition is in scope, or if no definition is in scope, the reference is irresolvable.</span></span> <span data-ttu-id="e8d36-175">Para obtener un ejemplo, vea "ejemplo de referencia completa" en esta página de ayuda.</span><span class="sxs-lookup"><span data-stu-id="e8d36-175">For an example, see "Qualified Reference Example" on this Help page.</span></span>  
  
 <span data-ttu-id="e8d36-176">Puede evitar la ambigüedad de nombres proporcionando a todos los elementos nombres únicos.</span><span class="sxs-lookup"><span data-stu-id="e8d36-176">You can avoid name ambiguity by giving all your elements unique names.</span></span> <span data-ttu-id="e8d36-177">Después, puede hacer referencia a cualquier elemento sin tener que calificar su nombre con un espacio de nombres, un módulo o una clase.</span><span class="sxs-lookup"><span data-stu-id="e8d36-177">Then you can make reference to any element without having to qualify its name with a namespace, module, or class.</span></span> <span data-ttu-id="e8d36-178">También reduce las posibilidades de hacer referencia accidental al elemento equivocado.</span><span class="sxs-lookup"><span data-stu-id="e8d36-178">You also reduce the chances of accidentally referring to the wrong element.</span></span>  
  
## <a name="shadowing"></a><span data-ttu-id="e8d36-179">Sombreado</span><span class="sxs-lookup"><span data-stu-id="e8d36-179">Shadowing</span></span>  

 <span data-ttu-id="e8d36-180">Cuando dos elementos de programación comparten el mismo nombre, uno de ellos puede ocultar, o *sombrear*, el otro.</span><span class="sxs-lookup"><span data-stu-id="e8d36-180">When two programming elements share the same name, one of them can hide, or *shadow*, the other one.</span></span> <span data-ttu-id="e8d36-181">Un elemento sombreado no está disponible como referencia; en su lugar, cuando el código usa el nombre del elemento con sombra, el compilador Visual Basic lo resuelve en el elemento de sombreado.</span><span class="sxs-lookup"><span data-stu-id="e8d36-181">A shadowed element is not available for reference; instead, when your code uses the shadowed element name, the Visual Basic compiler resolves it to the shadowing element.</span></span> <span data-ttu-id="e8d36-182">Para obtener una explicación más detallada de los ejemplos, vea [sombrear en Visual Basic](shadowing.md).</span><span class="sxs-lookup"><span data-stu-id="e8d36-182">For a more detailed explanation with examples, see [Shadowing in Visual Basic](shadowing.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8d36-183">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e8d36-183">See also</span></span>

- [<span data-ttu-id="e8d36-184">Declared Element Names</span><span class="sxs-lookup"><span data-stu-id="e8d36-184">Declared Element Names</span></span>](declared-element-names.md)
- [<span data-ttu-id="e8d36-185">Características de los elementos declarados</span><span class="sxs-lookup"><span data-stu-id="e8d36-185">Declared Element Characteristics</span></span>](declared-element-characteristics.md)
- [<span data-ttu-id="e8d36-186">Administrar propiedades de soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="e8d36-186">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
- [<span data-ttu-id="e8d36-187">Variables</span><span class="sxs-lookup"><span data-stu-id="e8d36-187">Variables</span></span>](../variables/index.md)
- [<span data-ttu-id="e8d36-188">Instrucción Imports (Tipo y espacio de nombres de .NET)</span><span class="sxs-lookup"><span data-stu-id="e8d36-188">Imports Statement (.NET Namespace and Type)</span></span>](../../../language-reference/statements/imports-statement-net-namespace-and-type.md)
- [<span data-ttu-id="e8d36-189">New Operator (Nuevo operador)</span><span class="sxs-lookup"><span data-stu-id="e8d36-189">New Operator</span></span>](../../../language-reference/operators/new-operator.md)
- [<span data-ttu-id="e8d36-190">Público</span><span class="sxs-lookup"><span data-stu-id="e8d36-190">Public</span></span>](../../../language-reference/modifiers/public.md)
