---
title: Namespace (Instrucción)
ms.date: 07/20/2015
f1_keywords:
- vb.Namespace
helpviewer_keywords:
- namespaces [Visual Basic], root
- Namespace statement [Visual Basic]
- namespaces [Visual Basic], nested
- declaring namespaces [Visual Basic], syntax
- namespaces [Visual Basic], declaring
- root namespaces
- declarations [Visual Basic], namespaces
ms.assetid: a31fbd95-9ace-4c3d-bbb1-51222a2272b2
ms.openlocfilehash: cef339a66458ee9657dc1706082c3c5328746dc6
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90875208"
---
# <a name="namespace-statement"></a><span data-ttu-id="6f66e-102">Namespace (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="6f66e-102">Namespace Statement</span></span>

<span data-ttu-id="6f66e-103">Declara el nombre de un espacio de nombres y hace que el código fuente que sigue a la declaración se compile dentro de ese espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="6f66e-103">Declares the name of a namespace and causes the source code that follows the declaration to be compiled within that namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f66e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6f66e-104">Syntax</span></span>  
  
```vb  
Namespace [Global.] { name | name.name }  
    [ componenttypes ]  
End Namespace  
```  
  
## <a name="parts"></a><span data-ttu-id="6f66e-105">Partes</span><span class="sxs-lookup"><span data-stu-id="6f66e-105">Parts</span></span>  

 <span data-ttu-id="6f66e-106">Global</span><span class="sxs-lookup"><span data-stu-id="6f66e-106">Global</span></span>  
 <span data-ttu-id="6f66e-107">Opcional.</span><span class="sxs-lookup"><span data-stu-id="6f66e-107">Optional.</span></span> <span data-ttu-id="6f66e-108">Permite definir un espacio de nombres fuera del espacio de nombres raíz del proyecto.</span><span class="sxs-lookup"><span data-stu-id="6f66e-108">Allows you to define a namespace out of the root namespace of your project.</span></span> <span data-ttu-id="6f66e-109">Vea [espacios de nombres en Visual Basic](../../programming-guide/program-structure/namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="6f66e-109">See [Namespaces in Visual Basic](../../programming-guide/program-structure/namespaces.md).</span></span>  
  
 `name`  
 <span data-ttu-id="6f66e-110">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="6f66e-110">Required.</span></span> <span data-ttu-id="6f66e-111">Nombre único que identifica el espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="6f66e-111">A unique name that identifies the namespace.</span></span> <span data-ttu-id="6f66e-112">Debe ser un identificador de Visual Basic válido.</span><span class="sxs-lookup"><span data-stu-id="6f66e-112">Must be a valid Visual Basic identifier.</span></span> <span data-ttu-id="6f66e-113">Para obtener más información, vea [nombres de elementos declarados](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="6f66e-113">For more information, see [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
 `componenttypes`  
 <span data-ttu-id="6f66e-114">Opcional.</span><span class="sxs-lookup"><span data-stu-id="6f66e-114">Optional.</span></span> <span data-ttu-id="6f66e-115">Elementos que componen el espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="6f66e-115">Elements that make up the namespace.</span></span> <span data-ttu-id="6f66e-116">Estos incluyen, entre otros, enumeraciones, estructuras, interfaces, clases, módulos, delegados y otros espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="6f66e-116">These include, but are not limited to, enumerations, structures, interfaces, classes, modules, delegates, and other namespaces.</span></span>  
  
 `End Namespace`  
 <span data-ttu-id="6f66e-117">Finaliza un `Namespace` bloque.</span><span class="sxs-lookup"><span data-stu-id="6f66e-117">Terminates a `Namespace` block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6f66e-118">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6f66e-118">Remarks</span></span>  

 <span data-ttu-id="6f66e-119">Los espacios de nombres se usan como sistema de la organización.</span><span class="sxs-lookup"><span data-stu-id="6f66e-119">Namespaces are used as an organizational system.</span></span> <span data-ttu-id="6f66e-120">Proporcionan una manera de clasificar y presentar los elementos de programación que se exponen a otros programas y aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="6f66e-120">They provide a way to classify and present programming elements that are exposed to other programs and applications.</span></span> <span data-ttu-id="6f66e-121">Tenga en cuenta que un espacio de nombres no es un *tipo* en el sentido de que una clase o estructura es: no puede declarar un elemento de programación para que tenga el tipo de datos de un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="6f66e-121">Note that a namespace is not a *type* in the sense that a class or structure is—you cannot declare a programming element to have the data type of a namespace.</span></span>  
  
 <span data-ttu-id="6f66e-122">Todos los elementos de programación declarados después de una `Namespace` instrucción pertenecen a ese espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="6f66e-122">All programming elements declared after a `Namespace` statement belong to that namespace.</span></span> <span data-ttu-id="6f66e-123">Visual Basic continúa compilando elementos en el último espacio de nombres declarado hasta que encuentra una `End Namespace` instrucción u otra `Namespace` instrucción.</span><span class="sxs-lookup"><span data-stu-id="6f66e-123">Visual Basic continues to compile elements into the last declared namespace until it encounters either an `End Namespace` statement or another `Namespace` statement.</span></span>  
  
 <span data-ttu-id="6f66e-124">Si ya hay un espacio de nombres definido, incluso fuera del proyecto, puede agregarle elementos de programación.</span><span class="sxs-lookup"><span data-stu-id="6f66e-124">If a namespace is already defined, even outside your project, you can add programming elements to it.</span></span> <span data-ttu-id="6f66e-125">Para ello, use una `Namespace` instrucción para dirigir Visual Basic para compilar los elementos en ese espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="6f66e-125">To do this, you use a `Namespace` statement to direct Visual Basic to compile elements into that namespace.</span></span>  
  
 <span data-ttu-id="6f66e-126">Puede usar una `Namespace` instrucción solo en el nivel de archivo o de espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="6f66e-126">You can use a `Namespace` statement only at the file or namespace level.</span></span> <span data-ttu-id="6f66e-127">Esto significa que el contexto de la *declaración* de un espacio de nombres debe ser un archivo de código fuente u otro espacio de nombres, y no puede ser una clase, una estructura, un módulo, una interfaz o un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="6f66e-127">This means the *declaration context* for a namespace must be a source file or another namespace, and cannot be a class, structure, module, interface, or procedure.</span></span> <span data-ttu-id="6f66e-128">Para obtener más información, vea [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md) (Contextos de declaración y niveles de acceso predeterminados).</span><span class="sxs-lookup"><span data-stu-id="6f66e-128">For more information, see [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="6f66e-129">Puede declarar un espacio de nombres dentro de otro.</span><span class="sxs-lookup"><span data-stu-id="6f66e-129">You can declare one namespace within another.</span></span> <span data-ttu-id="6f66e-130">No hay ningún límite estricto para los niveles de anidamiento que puede declarar, pero recuerde que cuando otro código tiene acceso a los elementos declarados en el espacio de nombres más interno, debe usar una cadena de calificación que contenga todos los nombres de espacio de nombres de la jerarquía de anidamiento.</span><span class="sxs-lookup"><span data-stu-id="6f66e-130">There is no strict limit to the levels of nesting you can declare, but remember that when other code accesses the elements declared in the innermost namespace, it must use a qualification string that contains all the namespace names in the nesting hierarchy.</span></span>  
  
## <a name="access-level"></a><span data-ttu-id="6f66e-131">Nivel de acceso</span><span class="sxs-lookup"><span data-stu-id="6f66e-131">Access Level</span></span>  

 <span data-ttu-id="6f66e-132">Los espacios de nombres se tratan como si tienen un `Public` nivel de acceso.</span><span class="sxs-lookup"><span data-stu-id="6f66e-132">Namespaces are treated as if they have a `Public` access level.</span></span> <span data-ttu-id="6f66e-133">Se puede tener acceso a un espacio de nombres desde el código en cualquier parte del mismo proyecto, desde otros proyectos que hagan referencia al proyecto y desde cualquier ensamblado compilado a partir del proyecto.</span><span class="sxs-lookup"><span data-stu-id="6f66e-133">A namespace can be accessed from code anywhere in the same project, from other projects that reference the project, and from any assembly built from the project.</span></span>  
  
 <span data-ttu-id="6f66e-134">Los elementos de programación declarados en el nivel de espacio de nombres, lo que significa que en un espacio de nombres pero no dentro de ningún otro elemento, pueden tener `Public` `Friend` acceso o.</span><span class="sxs-lookup"><span data-stu-id="6f66e-134">Programming elements declared at namespace level, meaning in a namespace but not inside any other element, can have `Public` or `Friend` access.</span></span> <span data-ttu-id="6f66e-135">Si no se especifica, el nivel de acceso de este elemento utiliza de `Friend` forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="6f66e-135">If unspecified, the access level of such an element uses `Friend` by default.</span></span> <span data-ttu-id="6f66e-136">Los elementos que se pueden declarar en el nivel de espacio de nombres incluyen clases, estructuras, módulos, interfaces, enumeraciones y delegados.</span><span class="sxs-lookup"><span data-stu-id="6f66e-136">Elements you can declare at namespace level include classes, structures, modules, interfaces, enumerations, and delegates.</span></span> <span data-ttu-id="6f66e-137">Para obtener más información, vea [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md) (Contextos de declaración y niveles de acceso predeterminados).</span><span class="sxs-lookup"><span data-stu-id="6f66e-137">For more information, see [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md).</span></span>  
  
## <a name="root-namespace"></a><span data-ttu-id="6f66e-138">Espacio de nombres raíz</span><span class="sxs-lookup"><span data-stu-id="6f66e-138">Root Namespace</span></span>  

 <span data-ttu-id="6f66e-139">Todos los nombres de espacios de nombres del proyecto se basan en un *espacio de nombres raíz*.</span><span class="sxs-lookup"><span data-stu-id="6f66e-139">All namespace names in your project are based on a *root namespace*.</span></span> <span data-ttu-id="6f66e-140">Visual Studio asigna el nombre del proyecto como el espacio de nombres raíz predeterminado para todo el código del proyecto.</span><span class="sxs-lookup"><span data-stu-id="6f66e-140">Visual Studio assigns your project name as the default root namespace for all code in your project.</span></span> <span data-ttu-id="6f66e-141">Por ejemplo, si el proyecto se llama `Payroll`, los respectivos elementos de programación pertenecerán al espacio de nombres `Payroll`.</span><span class="sxs-lookup"><span data-stu-id="6f66e-141">For example, if your project is named `Payroll`, its programming elements belong to namespace `Payroll`.</span></span> <span data-ttu-id="6f66e-142">Si declara `Namespace funding` , el nombre completo de ese espacio de nombres es `Payroll.funding` .</span><span class="sxs-lookup"><span data-stu-id="6f66e-142">If you declare `Namespace funding`, the full name of that namespace is `Payroll.funding`.</span></span>  
  
 <span data-ttu-id="6f66e-143">Si desea especificar un espacio de nombres existente en una `Namespace` instrucción, como en el ejemplo de clase de lista genérica, puede establecer el espacio de nombres raíz en un valor null.</span><span class="sxs-lookup"><span data-stu-id="6f66e-143">If you want to specify an existing namespace in a `Namespace` statement, such as in the generic list class example, you can set your root namespace to a null value.</span></span> <span data-ttu-id="6f66e-144">Para ello, haga clic en **propiedades del proyecto** en el menú **proyecto** y, a continuación, desactive la entrada **espacio de nombres raíz** para que el cuadro esté vacío.</span><span class="sxs-lookup"><span data-stu-id="6f66e-144">To do this, click **Project Properties** from the **Project** menu and then clear the **Root namespace** entry so that the box is empty.</span></span> <span data-ttu-id="6f66e-145">Si no lo hizo en el ejemplo de clase de lista genérica, el compilador Visual Basic tomaría `System.Collections.Generic` como un nuevo espacio de nombres dentro del proyecto `Payroll` , con el nombre completo de `Payroll.System.Collections.Generic` .</span><span class="sxs-lookup"><span data-stu-id="6f66e-145">If you did not do this in the generic list class example, the Visual Basic compiler would take `System.Collections.Generic` as a new namespace within project `Payroll`, with the full name of `Payroll.System.Collections.Generic`.</span></span>  
  
 <span data-ttu-id="6f66e-146">Como alternativa, puede usar la `Global` palabra clave para hacer referencia a los elementos de los espacios de nombres definidos fuera del proyecto.</span><span class="sxs-lookup"><span data-stu-id="6f66e-146">Alternatively, you can use the `Global` keyword to refer to elements of namespaces defined outside your project.</span></span> <span data-ttu-id="6f66e-147">Esto le permite conservar el nombre del proyecto como espacio de nombres raíz.</span><span class="sxs-lookup"><span data-stu-id="6f66e-147">Doing so lets you retain your project name as the root namespace.</span></span> <span data-ttu-id="6f66e-148">Esto reduce la posibilidad de combinar accidentalmente los elementos de programación con los de los espacios de nombres existentes.</span><span class="sxs-lookup"><span data-stu-id="6f66e-148">This reduces the chance of unintentionally merging your programming elements together with those of existing namespaces.</span></span> <span data-ttu-id="6f66e-149">Para obtener más información, vea la sección "palabra clave global en nombres completos" en [espacios de nombres en Visual Basic](../../programming-guide/program-structure/namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="6f66e-149">For more information, see the "Global Keyword in Fully Qualified Names" section in [Namespaces in Visual Basic](../../programming-guide/program-structure/namespaces.md).</span></span>  
  
 <span data-ttu-id="6f66e-150">La `Global` palabra clave también se puede utilizar en una instrucción de espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="6f66e-150">The `Global` keyword can also be used in a Namespace statement.</span></span> <span data-ttu-id="6f66e-151">con lo que podrá definir un espacio de nombres fuera del espacio de nombres raíz del proyecto.</span><span class="sxs-lookup"><span data-stu-id="6f66e-151">This lets you define a namespace out of the root namespace of your project.</span></span> <span data-ttu-id="6f66e-152">Para obtener más información, vea la sección "palabra clave global en instrucciones de espacio de nombres" en [espacios de nombres en Visual Basic](../../programming-guide/program-structure/namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="6f66e-152">For more information, see the "Global Keyword in Namespace Statements" section in [Namespaces in Visual Basic](../../programming-guide/program-structure/namespaces.md).</span></span>  
  
 <span data-ttu-id="6f66e-153">**Solución.**</span><span class="sxs-lookup"><span data-stu-id="6f66e-153">**Troubleshooting.**</span></span> <span data-ttu-id="6f66e-154">El espacio de nombres raíz puede producir concatenaciones inesperadas de nombres de espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="6f66e-154">The root namespace can lead to unexpected concatenations of namespace names.</span></span> <span data-ttu-id="6f66e-155">Si hace referencia a los espacios de nombres definidos fuera del proyecto, el compilador de Visual Basic puede interpretarlos como espacios de nombres anidados en el espacio de nombres raíz.</span><span class="sxs-lookup"><span data-stu-id="6f66e-155">If you make reference to namespaces defined outside your project, the Visual Basic compiler can construe them as nested namespaces in the root namespace.</span></span> <span data-ttu-id="6f66e-156">En tal caso, el compilador no reconoce ningún tipo que ya se haya definido en los espacios de nombres externos.</span><span class="sxs-lookup"><span data-stu-id="6f66e-156">In such a case, the compiler does not recognize any types that have been already defined in the external namespaces.</span></span> <span data-ttu-id="6f66e-157">Para evitar esto, establezca el espacio de nombres raíz en un valor nulo como se describe en "espacio de nombres de la raíz" o use la `Global` palabra clave para obtener acceso a los elementos de los espacios de nombres externos.</span><span class="sxs-lookup"><span data-stu-id="6f66e-157">To avoid this, either set your root namespace to a null value as described in "Root Namespace," or use the `Global` keyword to access elements of external namespaces.</span></span>  
  
## <a name="attributes-and-modifiers"></a><span data-ttu-id="6f66e-158">Atributos y modificadores</span><span class="sxs-lookup"><span data-stu-id="6f66e-158">Attributes and Modifiers</span></span>  

 <span data-ttu-id="6f66e-159">No se pueden aplicar atributos a un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="6f66e-159">You cannot apply attributes to a namespace.</span></span> <span data-ttu-id="6f66e-160">Un atributo contribuye a la información en los metadatos del ensamblado, lo que no es significativo para los clasificadores de origen, como los espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="6f66e-160">An attribute contributes information to the assembly's metadata, which is not meaningful for source classifiers such as namespaces.</span></span>  
  
 <span data-ttu-id="6f66e-161">No se puede aplicar ningún modificador de acceso o procedimiento, ni ningún otro modificador, a un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="6f66e-161">You cannot apply any access or procedure modifiers, or any other modifiers, to a namespace.</span></span> <span data-ttu-id="6f66e-162">Dado que no es un tipo, estos modificadores no son significativos.</span><span class="sxs-lookup"><span data-stu-id="6f66e-162">Because it is not a type, these modifiers are not meaningful.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6f66e-163">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6f66e-163">Example</span></span>  

 <span data-ttu-id="6f66e-164">En el siguiente ejemplo se declaran dos espacios de nombres, uno anidado en el otro.</span><span class="sxs-lookup"><span data-stu-id="6f66e-164">The following example declares two namespaces, one nested in the other.</span></span>  
  
 [!code-vb[VbVbalrStatements#43](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#43)]  
  
## <a name="example"></a><span data-ttu-id="6f66e-165">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6f66e-165">Example</span></span>  

 <span data-ttu-id="6f66e-166">En el siguiente ejemplo se declaran varios espacios de nombres anidados en una sola línea y es equivalente al ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="6f66e-166">The following example declares multiple nested namespaces on a single line, and it is equivalent to the previous example.</span></span>  
  
 [!code-vb[VbVbalrStatements#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#41)]  
  
## <a name="example"></a><span data-ttu-id="6f66e-167">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6f66e-167">Example</span></span>  

 <span data-ttu-id="6f66e-168">En el ejemplo siguiente se obtiene acceso a la clase definida en los ejemplos anteriores.</span><span class="sxs-lookup"><span data-stu-id="6f66e-168">The following example accesses the class defined in the previous examples.</span></span>  
  
 [!code-vb[VbVbalrStatements#42](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#42)]  
  
## <a name="example"></a><span data-ttu-id="6f66e-169">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6f66e-169">Example</span></span>  

 <span data-ttu-id="6f66e-170">En el ejemplo siguiente se define el esqueleto de una nueva clase de lista genérica y se agrega al <xref:System.Collections.Generic?displayProperty=nameWithType> espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="6f66e-170">The following example defines the skeleton of a new generic list class and adds it to the <xref:System.Collections.Generic?displayProperty=nameWithType> namespace.</span></span>  
  
```vb  
Namespace System.Collections.Generic  
    Class specialSortedList(Of T)  
        Inherits List(Of T)  
        ' Insert code to define the special generic list class.  
    End Class  
End Namespace  
```  
  
## <a name="see-also"></a><span data-ttu-id="6f66e-171">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6f66e-171">See also</span></span>

- [<span data-ttu-id="6f66e-172">Instrucción Imports (Tipo y espacio de nombres de .NET)</span><span class="sxs-lookup"><span data-stu-id="6f66e-172">Imports Statement (.NET Namespace and Type)</span></span>](imports-statement-net-namespace-and-type.md)
- [<span data-ttu-id="6f66e-173">Declared Element Names</span><span class="sxs-lookup"><span data-stu-id="6f66e-173">Declared Element Names</span></span>](../../programming-guide/language-features/declared-elements/declared-element-names.md)
- [<span data-ttu-id="6f66e-174">Espacios de nombres en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6f66e-174">Namespaces in Visual Basic</span></span>](../../programming-guide/program-structure/namespaces.md)
