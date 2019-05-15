---
title: Referencias a elementos declarados (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declared elements [Visual Basic]
- references [Visual Basic], declared elements
- qualified names [Visual Basic]
ms.assetid: d6301709-f4cc-4b7a-b8ba-80898f14ab46
ms.openlocfilehash: 616599e15c0d3d4c2177622d6820269bcff3ea39
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2019
ms.locfileid: "65592802"
---
# <a name="references-to-declared-elements-visual-basic"></a><span data-ttu-id="c5955-102">Referencias a elementos declarados (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c5955-102">References to Declared Elements (Visual Basic)</span></span>
<span data-ttu-id="c5955-103">Cuando el código hace referencia a un elemento declarado, el compilador de Visual Basic coincide con el nombre de la referencia a la declaración adecuada de ese nombre.</span><span class="sxs-lookup"><span data-stu-id="c5955-103">When your code refers to a declared element, the Visual Basic compiler matches the name in your reference to the appropriate declaration of that name.</span></span> <span data-ttu-id="c5955-104">Si se declara más de un elemento con el mismo nombre, puede controlar cuál de estos elementos es hacer referencia a *calificación* su nombre.</span><span class="sxs-lookup"><span data-stu-id="c5955-104">If more than one element is declared with the same name, you can control which of those elements is to be referenced by *qualifying* its name.</span></span>  
  
 <span data-ttu-id="c5955-105">El compilador intenta hacer coincidir una referencia de nombre a una declaración de nombre con el *ámbito más restringido*.</span><span class="sxs-lookup"><span data-stu-id="c5955-105">The compiler attempts to match a name reference to a name declaration with the *narrowest scope*.</span></span> <span data-ttu-id="c5955-106">Esto significa se inicia con el código que hace la referencia y se lleva a través de los niveles sucesivos de los elementos contenedores.</span><span class="sxs-lookup"><span data-stu-id="c5955-106">This means it starts with the code making the reference and works outward through successive levels of containing elements.</span></span>  
  
 <span data-ttu-id="c5955-107">El ejemplo siguiente muestra las referencias a dos variables con el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="c5955-107">The following example shows references to two variables with the same name.</span></span> <span data-ttu-id="c5955-108">En el ejemplo se declara dos variables, cada uno denominado `totalCount`, en diferentes niveles de ámbito en el módulo `container`.</span><span class="sxs-lookup"><span data-stu-id="c5955-108">The example declares two variables, each named `totalCount`, at different levels of scope in module `container`.</span></span> <span data-ttu-id="c5955-109">Cuando el procedimiento `showCount` muestra `totalCount` sin calificación, el compilador de Visual Basic resuelve la referencia a la declaración con el ámbito más restringido, concretamente la declaración local dentro de `showCount`.</span><span class="sxs-lookup"><span data-stu-id="c5955-109">When the procedure `showCount` displays `totalCount` without qualification, the Visual Basic compiler resolves the reference to the declaration with the narrowest scope, namely the local declaration inside `showCount`.</span></span> <span data-ttu-id="c5955-110">Cuando califica `totalCount` con el módulo contenedor `container`, el compilador resuelve la referencia a la declaración con el ámbito más amplio.</span><span class="sxs-lookup"><span data-stu-id="c5955-110">When it qualifies `totalCount` with the containing module `container`, the compiler resolves the reference to the declaration with the broader scope.</span></span>  
  
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
  
## <a name="qualifying-an-element-name"></a><span data-ttu-id="c5955-111">Calificar un nombre de elemento</span><span class="sxs-lookup"><span data-stu-id="c5955-111">Qualifying an Element Name</span></span>  
 <span data-ttu-id="c5955-112">Si desea invalidar este proceso de búsqueda y especificar un nombre declarado en un ámbito más amplio, debe *calificar* el nombre con el elemento contenedor del ámbito más amplio.</span><span class="sxs-lookup"><span data-stu-id="c5955-112">If you want to override this search process and specify a name declared in a broader scope, you must *qualify* the name with the containing element of the broader scope.</span></span> <span data-ttu-id="c5955-113">En algunos casos, es posible que deba calificar el elemento contenedor.</span><span class="sxs-lookup"><span data-stu-id="c5955-113">In some cases, you might also have to qualify the containing element.</span></span>  
  
 <span data-ttu-id="c5955-114">Calificar un nombre significa que le precede en la instrucción de origen con la información que identifica donde se define el elemento de destino.</span><span class="sxs-lookup"><span data-stu-id="c5955-114">Qualifying a name means preceding it in your source statement with information that identifies where the target element is defined.</span></span> <span data-ttu-id="c5955-115">Esta información se conoce como un *cadena de calificación*.</span><span class="sxs-lookup"><span data-stu-id="c5955-115">This information is called a *qualification string*.</span></span> <span data-ttu-id="c5955-116">Puede incluir uno o más espacios de nombres y un módulo, clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="c5955-116">It can include one or more namespaces and a module, class, or structure.</span></span>  
  
 <span data-ttu-id="c5955-117">La cadena de calificación debe especificar de forma inequívoca el módulo, clase o estructura que contiene el elemento de destino.</span><span class="sxs-lookup"><span data-stu-id="c5955-117">The qualification string should unambiguously specify the module, class, or structure containing the target element.</span></span> <span data-ttu-id="c5955-118">El contenedor a su vez puede estar ubicado en otro elemento contenedor, normalmente un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="c5955-118">The container might in turn be located in another containing element, usually a namespace.</span></span> <span data-ttu-id="c5955-119">Es posible que deba incluir varios elementos contenedores en la cadena de calificación.</span><span class="sxs-lookup"><span data-stu-id="c5955-119">You might need to include several containing elements in the qualification string.</span></span>  
  
#### <a name="to-access-a-declared-element-by-qualifying-its-name"></a><span data-ttu-id="c5955-120">Para obtener acceso a un elemento declarado por su nombre</span><span class="sxs-lookup"><span data-stu-id="c5955-120">To access a declared element by qualifying its name</span></span>  
  
1. <span data-ttu-id="c5955-121">Determinar la ubicación en la que se ha definido el elemento.</span><span class="sxs-lookup"><span data-stu-id="c5955-121">Determine the location in which the element has been defined.</span></span> <span data-ttu-id="c5955-122">Esto podría incluir un espacio de nombres o incluso una jerarquía de espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="c5955-122">This might include a namespace, or even a hierarchy of namespaces.</span></span> <span data-ttu-id="c5955-123">En el espacio de nombres de nivel más bajo, el elemento debe incluirse en un módulo, clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="c5955-123">Within the lowest-level namespace, the element must be contained in a module, class, or structure.</span></span>  
  
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
  
2. <span data-ttu-id="c5955-124">Determinar una ruta de acceso de calificación según la ubicación del elemento de destino.</span><span class="sxs-lookup"><span data-stu-id="c5955-124">Determine a qualification path based on the target element's location.</span></span> <span data-ttu-id="c5955-125">Comience con el espacio de nombres de nivel superior, continúe con el espacio de nombres de nivel inferior y terminar con el módulo, clase o estructura que contiene el elemento de destino.</span><span class="sxs-lookup"><span data-stu-id="c5955-125">Start with the highest-level namespace, proceed to the lowest-level namespace, and end with the module, class, or structure containing the target element.</span></span> <span data-ttu-id="c5955-126">Cada elemento de la ruta de acceso debe incluir el elemento que le sigue.</span><span class="sxs-lookup"><span data-stu-id="c5955-126">Each element in the path must contain the element that follows it.</span></span>  
  
     <span data-ttu-id="c5955-127">`outerSpace` → `innerSpace` → `holdsTotals` → `totals`</span><span class="sxs-lookup"><span data-stu-id="c5955-127">`outerSpace` → `innerSpace` → `holdsTotals` → `totals`</span></span>  
  
3. <span data-ttu-id="c5955-128">Prepare la cadena de calificación para el elemento de destino.</span><span class="sxs-lookup"><span data-stu-id="c5955-128">Prepare the qualification string for the target element.</span></span> <span data-ttu-id="c5955-129">Escriba un punto (`.`) después de todos los elementos de la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="c5955-129">Place a period (`.`) after every element in the path.</span></span> <span data-ttu-id="c5955-130">La aplicación debe tener acceso a todos los elementos de la cadena de calificación.</span><span class="sxs-lookup"><span data-stu-id="c5955-130">Your application must have access to every element in your qualification string.</span></span>  
  
    ```vb  
    outerSpace.innerSpace.holdsTotals.totals.  
    ```  
  
4. <span data-ttu-id="c5955-131">Escribir la expresión o instrucción de asignación que hace referencia al elemento de destino de la manera normal.</span><span class="sxs-lookup"><span data-stu-id="c5955-131">Write the expression or assignment statement referring to the target element in the normal way.</span></span>  
  
    ```vb  
    grandTotal = 9000  
    ```  
  
5. <span data-ttu-id="c5955-132">Delante del nombre de elemento de destino con la cadena de calificación.</span><span class="sxs-lookup"><span data-stu-id="c5955-132">Precede the target element name with the qualification string.</span></span> <span data-ttu-id="c5955-133">El nombre debe seguir inmediatamente el período (`.`) que sigue el módulo, clase o estructura que contiene el elemento.</span><span class="sxs-lookup"><span data-stu-id="c5955-133">The name should immediately follow the period (`.`) that follows the module, class, or structure that contains the element.</span></span>  
  
    ```vb  
    ' Assume the following module is part of your code.  
    Module accessGrandTotal  
        Public Sub setGrandTotal()  
            outerSpace.innerSpace.holdsTotals.totals.grandTotal = 9000  
        End Sub  
    End Module  
    ```  
  
6. <span data-ttu-id="c5955-134">El compilador usa la cadena de calificación para encontrar una declaración, inequívoca a la que puede coincidir con la referencia de elemento de destino.</span><span class="sxs-lookup"><span data-stu-id="c5955-134">The compiler uses the qualification string to find a clear, unambiguous declaration to which it can match the target element reference.</span></span>  
  
 <span data-ttu-id="c5955-135">También es posible que deba calificar una referencia de nombre si la aplicación tiene acceso a más de un elemento de programación que tiene el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="c5955-135">You might also have to qualify a name reference if your application has access to more than one programming element that has the same name.</span></span> <span data-ttu-id="c5955-136">Por ejemplo, el <xref:System.Windows.Forms> y <xref:System.Web.UI.WebControls> espacios de nombres ambos contienen una `Label` clase (<xref:System.Windows.Forms.Label?displayProperty=nameWithType> y <xref:System.Web.UI.WebControls.Label?displayProperty=nameWithType>).</span><span class="sxs-lookup"><span data-stu-id="c5955-136">For example, the <xref:System.Windows.Forms> and <xref:System.Web.UI.WebControls> namespaces both contain a `Label` class (<xref:System.Windows.Forms.Label?displayProperty=nameWithType> and <xref:System.Web.UI.WebControls.Label?displayProperty=nameWithType>).</span></span> <span data-ttu-id="c5955-137">Si la aplicación utiliza los dos, o bien, si define su propio `Label` (clase), se deben distinguir los diferentes `Label` objetos.</span><span class="sxs-lookup"><span data-stu-id="c5955-137">If your application uses both, or if it defines its own `Label` class, you must distinguish the different `Label` objects.</span></span> <span data-ttu-id="c5955-138">Incluir el alias de espacio de nombres o importar en la declaración de variable.</span><span class="sxs-lookup"><span data-stu-id="c5955-138">Include the namespace or import alias in the variable declaration.</span></span> <span data-ttu-id="c5955-139">El ejemplo siguiente usa el alias de importación.</span><span class="sxs-lookup"><span data-stu-id="c5955-139">The following example uses the import alias.</span></span>  
  
```vb  
' The following statement must precede all your declarations.  
Imports win = System.Windows.Forms, web = System.Web.UI.WebControls  
' The following statement references the Windows.Forms.Label class.  
Dim winLabel As New win.Label()  
```  
  
## <a name="members-of-other-containing-elements"></a><span data-ttu-id="c5955-140">Miembros de otros elementos que contiene</span><span class="sxs-lookup"><span data-stu-id="c5955-140">Members of Other Containing Elements</span></span>  
 <span data-ttu-id="c5955-141">Cuando se usa un miembro no compartido de otra clase o estructura, primero debe calificar el nombre del miembro con una variable o expresión que apunta a una instancia de la clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="c5955-141">When you use a nonshared member of another class or structure, you must first qualify the member name with a variable or expression that points to an instance of the class or structure.</span></span> <span data-ttu-id="c5955-142">En el ejemplo siguiente, `demoClass` es una instancia de una clase denominada `class1`.</span><span class="sxs-lookup"><span data-stu-id="c5955-142">In the following example, `demoClass` is an instance of a class named `class1`.</span></span>  
  
```vb  
Dim demoClass As class1 = New class1()  
demoClass.someSub[(argumentlist)]  
```  
  
 <span data-ttu-id="c5955-143">No se puede usar el nombre de la clase para calificar a un miembro que no es [Shared](../../../../visual-basic/language-reference/modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="c5955-143">You cannot use the class name itself to qualify a member that is not [Shared](../../../../visual-basic/language-reference/modifiers/shared.md).</span></span> <span data-ttu-id="c5955-144">Primero debe crear una instancia en una variable de objeto (en este caso `demoClass`) y, a continuación, haga referencia a él por el nombre de variable.</span><span class="sxs-lookup"><span data-stu-id="c5955-144">You must first create an instance in an object variable (in this case `demoClass`) and then reference it by the variable name.</span></span>  
  
 <span data-ttu-id="c5955-145">Si una clase o estructura tiene un `Shared` miembros, puede calificar ese miembro con el nombre de clase o estructura o con una variable o expresión que apunta a una instancia.</span><span class="sxs-lookup"><span data-stu-id="c5955-145">If a class or structure has a `Shared` member, you can qualify that member either with the class or structure name or with a variable or expression that points to an instance.</span></span>  
  
 <span data-ttu-id="c5955-146">Un módulo no tiene todas las instancias independientes, y todos sus miembros son `Shared` de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="c5955-146">A module does not have any separate instances, and all its members are `Shared` by default.</span></span> <span data-ttu-id="c5955-147">Por lo tanto, para calificar al miembro de un módulo con el nombre del módulo.</span><span class="sxs-lookup"><span data-stu-id="c5955-147">Therefore, you qualify a module member with the module name.</span></span>  
  
 <span data-ttu-id="c5955-148">El ejemplo siguiente muestra referencias completas a los procedimientos de miembros de módulo.</span><span class="sxs-lookup"><span data-stu-id="c5955-148">The following example shows qualified references to module member procedures.</span></span> <span data-ttu-id="c5955-149">El ejemplo declara dos `Sub` procedimientos, ambos denominados `perform`, en módulos diferentes de un proyecto.</span><span class="sxs-lookup"><span data-stu-id="c5955-149">The example declares two `Sub` procedures, both named `perform`, in different modules in a project.</span></span> <span data-ttu-id="c5955-150">Cada una de ellas puede especificarse sin calificación en su propio módulo, pero debe ser completa si se hace referencia desde cualquier otro lugar.</span><span class="sxs-lookup"><span data-stu-id="c5955-150">Each one can be specified without qualification within its own module but must be qualified if referenced from anywhere else.</span></span> <span data-ttu-id="c5955-151">Dado que hacen referencia a la última en `module3` no cumple los requisitos `perform`, el compilador no puede resolver esa referencia.</span><span class="sxs-lookup"><span data-stu-id="c5955-151">Because the final reference in `module3` does not qualify `perform`, the compiler cannot resolve that reference.</span></span>  
  
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
  
## <a name="references-to-projects"></a><span data-ttu-id="c5955-152">Referencias a proyectos</span><span class="sxs-lookup"><span data-stu-id="c5955-152">References to Projects</span></span>  
 <span data-ttu-id="c5955-153">Para usar [pública](../../../../visual-basic/language-reference/modifiers/public.md) elementos definidos en otro proyecto, primero debe establecer un *referencia* del ese proyecto ensamblado o biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="c5955-153">To use [Public](../../../../visual-basic/language-reference/modifiers/public.md) elements defined in another project, you must first set a *reference* to that project's assembly or type library.</span></span> <span data-ttu-id="c5955-154">Para establecer una referencia, haga clic en **Agregar referencia** en el **proyecto** menú o use el [/Reference (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/reference.md) opción del compilador de línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="c5955-154">To set a reference, click **Add Reference** on the **Project** menu, or use the [/reference (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/reference.md) command-line compiler option.</span></span>  
  
 <span data-ttu-id="c5955-155">Por ejemplo, puede usar el modelo de objetos XML de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c5955-155">For example, you can use the XML object model of the .NET Framework.</span></span> <span data-ttu-id="c5955-156">Si establece una referencia a la <xref:System.Xml> espacio de nombres, puede declarar y usar cualquiera de sus clases, como <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="c5955-156">If you set a reference to the <xref:System.Xml> namespace, you can declare and use any of its classes, such as <xref:System.Xml.XmlDocument>.</span></span> <span data-ttu-id="c5955-157">En el ejemplo siguiente se usa <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="c5955-157">The following example uses <xref:System.Xml.XmlDocument>.</span></span>  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As System.Xml.XmlDocument  
```  
  
## <a name="importing-containing-elements"></a><span data-ttu-id="c5955-158">Importar elementos contenedores</span><span class="sxs-lookup"><span data-stu-id="c5955-158">Importing Containing Elements</span></span>  
 <span data-ttu-id="c5955-159">Puede usar el [instrucción Imports (tipo y Namespace. NET)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) a *importar* los espacios de nombres que contienen los módulos o clases que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="c5955-159">You can use the [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) to *import* the namespaces that contain the modules or classes that you want to use.</span></span> <span data-ttu-id="c5955-160">Esto le permite hacer referencia a los elementos definidos en un espacio de nombres importado sin calificar por completo sus nombres.</span><span class="sxs-lookup"><span data-stu-id="c5955-160">This enables you to refer to the elements defined in an imported namespace without fully qualifying their names.</span></span> <span data-ttu-id="c5955-161">El ejemplo siguiente se vuelve a escribir el ejemplo anterior para importar el <xref:System.Xml> espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="c5955-161">The following example rewrites the previous example to import the <xref:System.Xml> namespace.</span></span>  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement must precede all your declarations.  
Imports System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As XmlDocument  
```  
  
 <span data-ttu-id="c5955-162">Además, el `Imports` instrucción puede definir un *alias de importación* para cada espacio de nombres importado.</span><span class="sxs-lookup"><span data-stu-id="c5955-162">In addition, the `Imports` statement can define an *import alias* for each imported namespace.</span></span> <span data-ttu-id="c5955-163">Esto puede hacer que el código fuente más corto y fácil de leer.</span><span class="sxs-lookup"><span data-stu-id="c5955-163">This can make the source code shorter and easier to read.</span></span> <span data-ttu-id="c5955-164">El ejemplo siguiente se vuelve a escribir el ejemplo anterior se usan `xD` como un alias para el <xref:System.Xml> espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="c5955-164">The following example rewrites the previous example to use `xD` as an alias for the <xref:System.Xml> namespace.</span></span>  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement must precede all your declarations.  
Imports xD = System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As xD.XmlDocument  
```  
  
 <span data-ttu-id="c5955-165">El `Imports` no hace que los elementos de otros proyectos disponibles para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="c5955-165">The `Imports` statement does not make elements from other projects available to your application.</span></span> <span data-ttu-id="c5955-166">Es decir, no tiene lugar de la configuración de una referencia.</span><span class="sxs-lookup"><span data-stu-id="c5955-166">That is, it does not take the place of setting a reference.</span></span> <span data-ttu-id="c5955-167">Importar un espacio de nombres solo quita el requisito para calificar los nombres definidos en dicho espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="c5955-167">Importing a namespace just removes the requirement to qualify the names defined in that namespace.</span></span>  
  
 <span data-ttu-id="c5955-168">También puede usar el `Imports` instrucción para importar módulos, clases, estructuras y enumeraciones.</span><span class="sxs-lookup"><span data-stu-id="c5955-168">You can also use the `Imports` statement to import modules, classes, structures, and enumerations.</span></span> <span data-ttu-id="c5955-169">A continuación, puede utilizar a los miembros de estos elementos importados sin calificación.</span><span class="sxs-lookup"><span data-stu-id="c5955-169">You can then use the members of such imported elements without qualification.</span></span> <span data-ttu-id="c5955-170">Sin embargo, siempre debe calificar a los miembros no compartidos de clases y estructuras con una variable o expresión que se evalúa como una instancia de la clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="c5955-170">However, you must always qualify nonshared members of classes and structures with a variable or expression that evaluates to an instance of the class or structure.</span></span>  
  
## <a name="naming-guidelines"></a><span data-ttu-id="c5955-171">Instrucciones de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="c5955-171">Naming Guidelines</span></span>  
 <span data-ttu-id="c5955-172">Cuando se definen dos o más elementos de programación que tienen el mismo nombre, un *nombre ambigüedad* puede producir cuando el compilador intenta resolver una referencia a ese nombre.</span><span class="sxs-lookup"><span data-stu-id="c5955-172">When you define two or more programming elements that have the same name, a *name ambiguity* can result when the compiler attempts to resolve a reference to that name.</span></span> <span data-ttu-id="c5955-173">Si hay más de una definición en el ámbito, o si ninguna definición está en el ámbito, la referencia es irresoluble.</span><span class="sxs-lookup"><span data-stu-id="c5955-173">If more than one definition is in scope, or if no definition is in scope, the reference is irresolvable.</span></span> <span data-ttu-id="c5955-174">Para obtener un ejemplo, vea "Ejemplo de referencia completo" en esta página de ayuda.</span><span class="sxs-lookup"><span data-stu-id="c5955-174">For an example, see "Qualified Reference Example" on this Help page.</span></span>  
  
 <span data-ttu-id="c5955-175">Puede evitar la ambigüedad de nombre proporcionando nombres únicos a todos los elementos.</span><span class="sxs-lookup"><span data-stu-id="c5955-175">You can avoid name ambiguity by giving all your elements unique names.</span></span> <span data-ttu-id="c5955-176">A continuación, puede hacer referencia a cualquier elemento sin tener que calificar su nombre con un espacio de nombres, módulo o clase.</span><span class="sxs-lookup"><span data-stu-id="c5955-176">Then you can make reference to any element without having to qualify its name with a namespace, module, or class.</span></span> <span data-ttu-id="c5955-177">También reduce las posibilidades de accidentalmente que hace referencia a un elemento equivocado.</span><span class="sxs-lookup"><span data-stu-id="c5955-177">You also reduce the chances of accidentally referring to the wrong element.</span></span>  
  
## <a name="shadowing"></a><span data-ttu-id="c5955-178">Sombreado</span><span class="sxs-lookup"><span data-stu-id="c5955-178">Shadowing</span></span>  
 <span data-ttu-id="c5955-179">Cuando dos elementos de programación comparten el mismo nombre, puede ocultar uno de ellos, o *sombra*, otro.</span><span class="sxs-lookup"><span data-stu-id="c5955-179">When two programming elements share the same name, one of them can hide, or *shadow*, the other one.</span></span> <span data-ttu-id="c5955-180">Un elemento reemplazado no está disponible para la referencia; en su lugar, cuando el código usa el nombre del elemento reemplazado, el compilador de Visual Basic resuelve en el elemento reemplazado.</span><span class="sxs-lookup"><span data-stu-id="c5955-180">A shadowed element is not available for reference; instead, when your code uses the shadowed element name, the Visual Basic compiler resolves it to the shadowing element.</span></span> <span data-ttu-id="c5955-181">Para obtener una explicación más detallada con ejemplos, vea [sombrear en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span><span class="sxs-lookup"><span data-stu-id="c5955-181">For a more detailed explanation with examples, see [Shadowing in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5955-182">Vea también</span><span class="sxs-lookup"><span data-stu-id="c5955-182">See also</span></span>

- [<span data-ttu-id="c5955-183">Nombres de elementos declarados</span><span class="sxs-lookup"><span data-stu-id="c5955-183">Declared Element Names</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [<span data-ttu-id="c5955-184">Características de los elementos declarados</span><span class="sxs-lookup"><span data-stu-id="c5955-184">Declared Element Characteristics</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)
- [<span data-ttu-id="c5955-185">Administrar propiedades de soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="c5955-185">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
- [<span data-ttu-id="c5955-186">Variables</span><span class="sxs-lookup"><span data-stu-id="c5955-186">Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/index.md)
- [<span data-ttu-id="c5955-187">Imports (instrucción), espacio de nombres y tipo .NET</span><span class="sxs-lookup"><span data-stu-id="c5955-187">Imports Statement (.NET Namespace and Type)</span></span>](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [<span data-ttu-id="c5955-188">New (operador)</span><span class="sxs-lookup"><span data-stu-id="c5955-188">New Operator</span></span>](../../../../visual-basic/language-reference/operators/new-operator.md)
- [<span data-ttu-id="c5955-189">Public</span><span class="sxs-lookup"><span data-stu-id="c5955-189">Public</span></span>](../../../../visual-basic/language-reference/modifiers/public.md)
