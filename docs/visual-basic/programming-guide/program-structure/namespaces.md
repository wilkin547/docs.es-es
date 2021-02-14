---
description: 'Más información acerca de: espacios de nombres en Visual Basic'
title: Espacios de nombres
ms.date: 07/20/2015
f1_keywords:
- vb.global
helpviewer_keywords:
- assemblies [Visual Basic], namespaces
- name collisions
- Global keyword [Visual Basic]
- namespace pollution
- names [Visual Basic], avoiding conflicts
- naming conflicts [Visual Basic], namespaces
- namespaces [Visual Basic], assemblies
- Visual Basic code, namespaces
- fully qualified names [Visual Basic]
- naming conventions [Visual Basic], naming conflicts
- namespaces
ms.assetid: cffac744-ab8c-4f1f-ba50-732c22ab4b88
ms.openlocfilehash: 2f7c0bfd29bf6fe104252aa125b4ddff1259b50a
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100460753"
---
# <a name="namespaces-in-visual-basic"></a><span data-ttu-id="b6b1b-103">Espacios de nombres en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b6b1b-103">Namespaces in Visual Basic</span></span>

<span data-ttu-id="b6b1b-104">Los espacios de nombres organizan los objetos definidos en un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="b6b1b-104">Namespaces organize the objects defined in an assembly.</span></span> <span data-ttu-id="b6b1b-105">Los ensamblados pueden contener varios espacios de nombres, que a su vez pueden contener otros espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="b6b1b-105">Assemblies can contain multiple namespaces, which can in turn contain other namespaces.</span></span> <span data-ttu-id="b6b1b-106">Los espacios de nombres evitan las ambigüedades y simplifican las referencias cuando se usan grupos de objetos grandes, como las bibliotecas de clases.</span><span class="sxs-lookup"><span data-stu-id="b6b1b-106">Namespaces prevent ambiguity and simplify references when using large groups of objects such as class libraries.</span></span>  
  
 <span data-ttu-id="b6b1b-107">Por ejemplo, el .NET Framework define la <xref:System.Windows.Forms.ListBox> clase en el <xref:System.Windows.Forms?displayProperty=nameWithType> espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="b6b1b-107">For example, the .NET Framework defines the <xref:System.Windows.Forms.ListBox> class in the <xref:System.Windows.Forms?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="b6b1b-108">En el siguiente fragmento de código se muestra cómo declarar una variable con el nombre completo de esta clase:</span><span class="sxs-lookup"><span data-stu-id="b6b1b-108">The following code fragment shows how to declare a variable using the fully qualified name for this class:</span></span>  
  
 [!code-vb[VbVbalrApplication#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#6)]  
  
## <a name="avoiding-name-collisions"></a><span data-ttu-id="b6b1b-109">Evitar conflictos de nombres</span><span class="sxs-lookup"><span data-stu-id="b6b1b-109">Avoiding Name Collisions</span></span>  

 <span data-ttu-id="b6b1b-110">.NET Framework espacios de nombres resuelven un problema que a veces se denomina *contaminación de espacio de nombres*, en el que el desarrollador de una biblioteca de clases se ve obstaculizado por el uso de nombres similares en otra biblioteca.</span><span class="sxs-lookup"><span data-stu-id="b6b1b-110">.NET Framework namespaces address a problem sometimes called *namespace pollution*, in which the developer of a class library is hampered by the use of similar names in another library.</span></span> <span data-ttu-id="b6b1b-111">Estos conflictos con componentes existentes a veces se denominan *conflictos de nombres*.</span><span class="sxs-lookup"><span data-stu-id="b6b1b-111">These conflicts with existing components are sometimes called *name collisions*.</span></span>  
  
 <span data-ttu-id="b6b1b-112">Por ejemplo, si crea una clase denominada `ListBox`, puede usarla en su proyecto sin ninguna calificación,</span><span class="sxs-lookup"><span data-stu-id="b6b1b-112">For example, if you create a new class named `ListBox`, you can use it inside your project without qualification.</span></span> <span data-ttu-id="b6b1b-113">Sin embargo, si desea utilizar la clase .NET Framework <xref:System.Windows.Forms.ListBox> en el mismo proyecto, debe usar una referencia completa para que la referencia sea única.</span><span class="sxs-lookup"><span data-stu-id="b6b1b-113">However, if you want to use the .NET Framework <xref:System.Windows.Forms.ListBox> class in the same project, you must use a fully qualified reference to make the reference unique.</span></span> <span data-ttu-id="b6b1b-114">Si la referencia no es única, Visual Basic genera un error que indica que el nombre es ambiguo.</span><span class="sxs-lookup"><span data-stu-id="b6b1b-114">If the reference is not unique, Visual Basic produces an error stating that the name is ambiguous.</span></span> <span data-ttu-id="b6b1b-115">En el ejemplo de código siguiente se muestra cómo declarar estos objetos:</span><span class="sxs-lookup"><span data-stu-id="b6b1b-115">The following code example demonstrates how to declare these objects:</span></span>  
  
 [!code-vb[VbVbalrApplication#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#7)]  
  
 <span data-ttu-id="b6b1b-116">En la ilustración siguiente se muestran dos jerarquías de espacios de nombres que contienen un objeto denominado `ListBox` :</span><span class="sxs-lookup"><span data-stu-id="b6b1b-116">The following illustration shows two namespace hierarchies, both containing an object named `ListBox`:</span></span>  
  
 ![Captura de pantalla que muestra dos jerarquías de espacios de nombres.](./media/namespaces/visual-basic-namespace-hierarchy.gif)  
  
 <span data-ttu-id="b6b1b-118">De forma predeterminada, cada archivo ejecutable que se crea con Visual Basic contiene un espacio de nombres con el mismo nombre que el proyecto.</span><span class="sxs-lookup"><span data-stu-id="b6b1b-118">By default, every executable file you create with Visual Basic contains a namespace with the same name as your project.</span></span> <span data-ttu-id="b6b1b-119">Por ejemplo, si define un objeto en un proyecto denominado `ListBoxProject`, el archivo ejecutable ListBoxProject.exe contiene un espacio de nombres llamado `ListBoxProject`.</span><span class="sxs-lookup"><span data-stu-id="b6b1b-119">For example, if you define an object within a project named `ListBoxProject`, the executable file ListBoxProject.exe contains a namespace called `ListBoxProject`.</span></span>  
  
 <span data-ttu-id="b6b1b-120">Se puede usar el mismo espacio de nombres en varios ensamblados.</span><span class="sxs-lookup"><span data-stu-id="b6b1b-120">Multiple assemblies can use the same namespace.</span></span> <span data-ttu-id="b6b1b-121">Visual Basic los trata como un único conjunto de nombres.</span><span class="sxs-lookup"><span data-stu-id="b6b1b-121">Visual Basic treats them as a single set of names.</span></span> <span data-ttu-id="b6b1b-122">Por ejemplo, puede definir clases para un espacio de nombres ( `SomeNameSpace` ) en un ensamblado ( `Assemb1`) y definir clases adicionales para el mismo espacio de nombres desde un ensamblado denominado `Assemb2`.</span><span class="sxs-lookup"><span data-stu-id="b6b1b-122">For example, you can define classes for a namespace called `SomeNameSpace` in an assembly named `Assemb1`, and define additional classes for the same namespace from an assembly named `Assemb2`.</span></span>  
  
## <a name="fully-qualified-names"></a><span data-ttu-id="b6b1b-123">nombres completos</span><span class="sxs-lookup"><span data-stu-id="b6b1b-123">Fully Qualified Names</span></span>  

 <span data-ttu-id="b6b1b-124">Los nombres completos son referencias de objetos que llevan como prefijo el nombre del espacio de nombres en el que se define el objeto.</span><span class="sxs-lookup"><span data-stu-id="b6b1b-124">Fully qualified names are object references that are prefixed with the name of the namespace in which the object is defined.</span></span> <span data-ttu-id="b6b1b-125">Puede usar los objetos definidos en otros proyectos si crea una referencia a la clase (eligiendo **Agregar referencia** desde el menú **Proyecto** ) y usa el nombre completo del objeto en el código.</span><span class="sxs-lookup"><span data-stu-id="b6b1b-125">You can use objects defined in other projects if you create a reference to the class (by choosing **Add Reference** from the **Project** menu) and then use the fully qualified name for the object in your code.</span></span> <span data-ttu-id="b6b1b-126">En el siguiente fragmento de código se muestra cómo usar el nombre completo de un objeto desde el espacio de nombres de otro proyecto:</span><span class="sxs-lookup"><span data-stu-id="b6b1b-126">The following code fragment shows how to use the fully qualified name for an object from another project's namespace:</span></span>  
  
 [!code-vb[VbVbalrApplication#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#8)]  
  
 <span data-ttu-id="b6b1b-127">Los nombres completos evitan conflictos de nomenclatura, ya que permiten que el compilador determine el objeto que se está usando,</span><span class="sxs-lookup"><span data-stu-id="b6b1b-127">Fully qualified names prevent naming conflicts because they make it possible for the compiler to determine which object is being used.</span></span> <span data-ttu-id="b6b1b-128">aunque los nombres pueden llegar a ser largos y complicados.</span><span class="sxs-lookup"><span data-stu-id="b6b1b-128">However, the names themselves can get long and cumbersome.</span></span> <span data-ttu-id="b6b1b-129">Para solucionar este problema, puede usar la instrucción `Imports` para definir un *alias*: un nombre abreviado que puede usar en lugar de un nombre completo.</span><span class="sxs-lookup"><span data-stu-id="b6b1b-129">To get around this, you can use the `Imports` statement to define an *alias*—an abbreviated name you can use in place of a fully qualified name.</span></span> <span data-ttu-id="b6b1b-130">Por ejemplo, en el siguiente ejemplo de código se crean alias para dos nombres completos y se usan para definir dos objetos.</span><span class="sxs-lookup"><span data-stu-id="b6b1b-130">For example, the following code example creates aliases for two fully qualified names, and uses these aliases to define two objects.</span></span>  
  
 [!code-vb[VbVbalrApplication#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#9)]  
  
 [!code-vb[VbVbalrApplication#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#10)]  
  
 <span data-ttu-id="b6b1b-131">Si usa la instrucción `Imports` sin un alias, puede usar todos los nombres de ese espacio de nombres sin ninguna calificación, siempre que sean únicos en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="b6b1b-131">If you use the `Imports` statement without an alias, you can use all the names in that namespace without qualification, provided they are unique to the project.</span></span> <span data-ttu-id="b6b1b-132">Si el proyecto contiene instrucciones `Imports` de los espacios de nombres que contienen elementos con el mismo nombre, debe calificar totalmente ese nombre en el momento de usarlo.</span><span class="sxs-lookup"><span data-stu-id="b6b1b-132">If your project contains `Imports` statements for namespaces that contain items with the same name, you must fully qualify that name when you use it.</span></span> <span data-ttu-id="b6b1b-133">Supongamos, por ejemplo, que el proyecto contenía las dos instrucciones `Imports` siguientes:</span><span class="sxs-lookup"><span data-stu-id="b6b1b-133">Suppose, for example, your project contained the following two `Imports` statements:</span></span>  
  
 [!code-vb[VbVbalrApplication#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#11)]  
  
 <span data-ttu-id="b6b1b-134">Si intenta usar `Class1` sin calificarla por completo, Visual Basic genera un error que indica que el nombre `Class1` es ambiguo.</span><span class="sxs-lookup"><span data-stu-id="b6b1b-134">If you attempt to use `Class1` without fully qualifying it, Visual Basic produces an error stating that the name `Class1` is ambiguous.</span></span>  
  
## <a name="namespace-level-statements"></a><span data-ttu-id="b6b1b-135">Instrucciones de nivel de espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="b6b1b-135">Namespace Level Statements</span></span>  

 <span data-ttu-id="b6b1b-136">Dentro de un espacio de nombres, puede definir elementos tales como módulos, interfaces, clases, delegados, enumeraciones, estructuras y otros espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="b6b1b-136">Within a namespace, you can define items such as modules, interfaces, classes, delegates, enumerations, structures, and other namespaces.</span></span> <span data-ttu-id="b6b1b-137">Los elementos tales como propiedades, procedimientos, variables y eventos no se pueden definir en el nivel de espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="b6b1b-137">You cannot define items such as properties, procedures, variables and events at the namespace level.</span></span> <span data-ttu-id="b6b1b-138">Estos elementos deben declararse dentro de contenedores tales como módulos, estructuras o clases.</span><span class="sxs-lookup"><span data-stu-id="b6b1b-138">These items must be declared within containers such as modules, structures, or classes.</span></span>  
  
## <a name="global-keyword-in-fully-qualified-names"></a><span data-ttu-id="b6b1b-139">Palabra clave Global en los nombres completos</span><span class="sxs-lookup"><span data-stu-id="b6b1b-139">Global Keyword in Fully Qualified Names</span></span>  

 <span data-ttu-id="b6b1b-140">Si ha definido una jerarquía anidada de espacios de nombres, el código insertado en esa jerarquía podría tener bloqueado el acceso al espacio de nombres <xref:System?displayProperty=nameWithType> de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b6b1b-140">If you have defined a nested hierarchy of namespaces, code inside that hierarchy might be blocked from accessing the <xref:System?displayProperty=nameWithType> namespace of the .NET Framework.</span></span> <span data-ttu-id="b6b1b-141">En el siguiente ejemplo se muestra una jerarquía en la que el espacio de nombres `SpecialSpace.System` bloquea el acceso a <xref:System?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b6b1b-141">The following example illustrates a hierarchy in which the `SpecialSpace.System` namespace blocks access to <xref:System?displayProperty=nameWithType>.</span></span>  
  
```vb  
Namespace SpecialSpace  
    Namespace System  
        Class abc  
            Function getValue() As System.Int32  
                Dim n As System.Int32  
                Return n  
            End Function  
        End Class  
    End Namespace  
End Namespace  
```  
  
 <span data-ttu-id="b6b1b-142">Como resultado, el compilador de Visual Basic no puede resolver correctamente la referencia a <xref:System.Int32?displayProperty=nameWithType>, porque `SpecialSpace.System` no define `Int32`.</span><span class="sxs-lookup"><span data-stu-id="b6b1b-142">As a result, the Visual Basic compiler cannot successfully resolve the reference to <xref:System.Int32?displayProperty=nameWithType>, because `SpecialSpace.System` does not define `Int32`.</span></span> <span data-ttu-id="b6b1b-143">Puede usar la palabra clave `Global` para iniciar la cadena de calificación en el nivel más externo de la biblioteca de clases de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b6b1b-143">You can use the `Global` keyword to start the qualification chain at the outermost level of the .NET Framework class library.</span></span> <span data-ttu-id="b6b1b-144">De este modo, puede especificar el espacio de nombres <xref:System?displayProperty=nameWithType> o cualquier otro espacio de nombres en la biblioteca de clases.</span><span class="sxs-lookup"><span data-stu-id="b6b1b-144">This allows you to specify the <xref:System?displayProperty=nameWithType> namespace or any other namespace in the class library.</span></span> <span data-ttu-id="b6b1b-145">Esto se ilustra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b6b1b-145">The following example illustrates this.</span></span>  
  
```vb  
Namespace SpecialSpace  
    Namespace System  
        Class abc  
            Function getValue() As Global.System.Int32  
                Dim n As Global.System.Int32  
                Return n  
            End Function  
        End Class  
    End Namespace  
End Namespace  
```  
  
 <span data-ttu-id="b6b1b-146">Puede usar `Global` para obtener acceso a otros espacios de nombres de nivel de raíz, como <xref:Microsoft.VisualBasic?displayProperty=nameWithType>, y a cualquier espacio de nombres asociado a su proyecto.</span><span class="sxs-lookup"><span data-stu-id="b6b1b-146">You can use `Global` to access other root-level namespaces, such as <xref:Microsoft.VisualBasic?displayProperty=nameWithType>, and any namespace associated with your project.</span></span>  
  
## <a name="global-keyword-in-namespace-statements"></a><span data-ttu-id="b6b1b-147">Palabra clave Global en las instrucciones de espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="b6b1b-147">Global Keyword in Namespace Statements</span></span>  

 <span data-ttu-id="b6b1b-148">También puede usar la palabra clave `Global` en una [Namespace Statement](../../language-reference/statements/namespace-statement.md).</span><span class="sxs-lookup"><span data-stu-id="b6b1b-148">You can also use the `Global` keyword in a [Namespace Statement](../../language-reference/statements/namespace-statement.md).</span></span> <span data-ttu-id="b6b1b-149">con lo que podrá definir un espacio de nombres fuera del espacio de nombres raíz del proyecto.</span><span class="sxs-lookup"><span data-stu-id="b6b1b-149">This lets you define a namespace out of the root namespace of your project.</span></span>  
  
 <span data-ttu-id="b6b1b-150">Todos los espacios de nombres del proyecto se basan en el espacio de nombres raíz de este.</span><span class="sxs-lookup"><span data-stu-id="b6b1b-150">All namespaces in your project are based on the root namespace for the project.</span></span>  <span data-ttu-id="b6b1b-151">Visual Studio asigna el nombre del proyecto como el espacio de nombres raíz predeterminado para todo el código del proyecto.</span><span class="sxs-lookup"><span data-stu-id="b6b1b-151">Visual Studio assigns your project name as the default root namespace for all code in your project.</span></span> <span data-ttu-id="b6b1b-152">Por ejemplo, si el proyecto se llama `ConsoleApplication1`, los respectivos elementos de programación pertenecerán al espacio de nombres `ConsoleApplication1`.</span><span class="sxs-lookup"><span data-stu-id="b6b1b-152">For example, if your project is named `ConsoleApplication1`, its programming elements belong to namespace `ConsoleApplication1`.</span></span> <span data-ttu-id="b6b1b-153">Si declara `Namespace Magnetosphere`, las referencias a `Magnetosphere` en el proyecto tendrán acceso a `ConsoleApplication1.Magnetosphere`.</span><span class="sxs-lookup"><span data-stu-id="b6b1b-153">If you declare `Namespace Magnetosphere`, references to `Magnetosphere` in the project will access `ConsoleApplication1.Magnetosphere`.</span></span>  
  
 <span data-ttu-id="b6b1b-154">En los siguientes ejemplos se usa la palabra clave `Global` para declarar un espacio de nombres fuera del espacio de nombres raíz del proyecto.</span><span class="sxs-lookup"><span data-stu-id="b6b1b-154">The following examples use the `Global` keyword to declare a namespace out of the root namespace for the project.</span></span>  
  
 [!code-vb[VbVbalrApplication#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/module1.vb#22)]  
  
 <span data-ttu-id="b6b1b-155">En una declaración de espacio de nombres, no se puede anidar `Global` en otro espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="b6b1b-155">In a namespace declaration, `Global` cannot be nested in another namespace.</span></span>  
  
 <span data-ttu-id="b6b1b-156">Puede usar la [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic) para ver y modificar el **espacio de nombres raíz** del proyecto.</span><span class="sxs-lookup"><span data-stu-id="b6b1b-156">You can use the [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic) to view and modify the **Root Namespace** of the project.</span></span>  <span data-ttu-id="b6b1b-157">En cuanto a los proyectos nuevos, el **espacio de nombres raíz** tiene como nombre predeterminado el nombre del proyecto.</span><span class="sxs-lookup"><span data-stu-id="b6b1b-157">For new projects, the **Root Namespace** defaults to the project name.</span></span> <span data-ttu-id="b6b1b-158">Para que `Global` sea el espacio de nombres de nivel superior, puede borrar la entrada **Espacio de nombres raíz** para que el cuadro esté vacío.</span><span class="sxs-lookup"><span data-stu-id="b6b1b-158">To cause `Global` to be the top-level namespace, you can clear the **Root Namespace** entry so that the box is empty.</span></span> <span data-ttu-id="b6b1b-159">Si se borra **Espacio de nombres raíz** , ya no es necesario usar la palabra clave `Global` en las declaraciones de espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="b6b1b-159">Clearing **Root Namespace** removes the need for the `Global` keyword in namespace declarations.</span></span>  
  
 <span data-ttu-id="b6b1b-160">Si una instrucción `Namespace` declara un nombre que también es un espacio de nombres en .NET Framework, el espacio de nombres de .NET Framework dejará de estar disponible si la palabra clave `Global` no se usa en un nombre completo.</span><span class="sxs-lookup"><span data-stu-id="b6b1b-160">If a `Namespace` statement declares a name that is also a namespace in the .NET Framework, the .NET Framework namespace becomes unavailable if the `Global` keyword is not used in a fully qualified name.</span></span> <span data-ttu-id="b6b1b-161">Para habilitar el acceso al espacio de nombres de .NET Framework sin usar la palabra clave `Global` , puede incluir la palabra clave `Global` en la instrucción `Namespace` .</span><span class="sxs-lookup"><span data-stu-id="b6b1b-161">To enable access to that .NET Framework namespace without using the `Global` keyword, you can include the `Global` keyword in the `Namespace` statement.</span></span>  
  
 <span data-ttu-id="b6b1b-162">En el siguiente ejemplo aparece la palabra clave `Global` en la declaración de espacio de nombres `System.Text` .</span><span class="sxs-lookup"><span data-stu-id="b6b1b-162">The following example has the `Global` keyword in the `System.Text` namespace declaration.</span></span>  
  
 <span data-ttu-id="b6b1b-163">Si la palabra clave `Global` no estuviera presente en la declaración de espacio de nombres, no se podría obtener acceso a <xref:System.Text.StringBuilder> sin especificar `Global.System.Text.StringBuilder`.</span><span class="sxs-lookup"><span data-stu-id="b6b1b-163">If the `Global` keyword was not present in the namespace declaration, <xref:System.Text.StringBuilder> could not be accessed without specifying `Global.System.Text.StringBuilder`.</span></span> <span data-ttu-id="b6b1b-164">Para el proyecto `ConsoleApplication1`, las referencias a `System.Text` tendrían acceso a `ConsoleApplication1.System.Text` si no se usara la palabra clave `Global` .</span><span class="sxs-lookup"><span data-stu-id="b6b1b-164">For a project named `ConsoleApplication1`, references to `System.Text` would access `ConsoleApplication1.System.Text` if the `Global` keyword was not used.</span></span>  
  
 [!code-vb[VbVbalrApplication#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/module1.vb#21)]  
  
## <a name="see-also"></a><span data-ttu-id="b6b1b-165">Vea también</span><span class="sxs-lookup"><span data-stu-id="b6b1b-165">See also</span></span>

- <xref:System.Windows.Forms.ListBox>
- <xref:System.Windows.Forms?displayProperty=nameWithType>
- [<span data-ttu-id="b6b1b-166">Ensamblados de .NET</span><span class="sxs-lookup"><span data-stu-id="b6b1b-166">Assemblies in .NET</span></span>](../../../standard/assembly/index.md)
- [<span data-ttu-id="b6b1b-167">Referencias y la instrucción Imports</span><span class="sxs-lookup"><span data-stu-id="b6b1b-167">References and the Imports Statement</span></span>](references-and-the-imports-statement.md)
- [<span data-ttu-id="b6b1b-168">Instrucción Imports (Tipo y espacio de nombres de .NET)</span><span class="sxs-lookup"><span data-stu-id="b6b1b-168">Imports Statement (.NET Namespace and Type)</span></span>](../../language-reference/statements/imports-statement-net-namespace-and-type.md)
- [<span data-ttu-id="b6b1b-169">Escribir código en soluciones de Office</span><span class="sxs-lookup"><span data-stu-id="b6b1b-169">Writing Code in Office Solutions</span></span>](/visualstudio/vsto/writing-code-in-office-solutions)
