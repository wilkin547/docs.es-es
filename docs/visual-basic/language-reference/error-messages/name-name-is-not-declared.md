---
title: No se ha declarado el nombre '<name>'
ms.date: 10/10/2018
f1_keywords:
- bc30451
- vbc30451
helpviewer_keywords:
- BC30451
ms.assetid: 765f099b-e21e-47c6-a906-a065444e56b3
ms.openlocfilehash: 76c1ab4fb5f1f8e4c76a06110f4b0f9026cca201
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90871545"
---
# <a name="name-name-is-not-declared"></a><span data-ttu-id="7856f-102">No se ha declarado el nombre '\<name>'</span><span class="sxs-lookup"><span data-stu-id="7856f-102">Name '\<name>' is not declared</span></span>

<span data-ttu-id="7856f-103">Una instrucción hace referencia a un elemento de programación, pero el compilador no puede encontrar un elemento con ese nombre exacto.</span><span class="sxs-lookup"><span data-stu-id="7856f-103">A statement refers to a programming element, but the compiler cannot find an element with that exact name.</span></span>  
  
 <span data-ttu-id="7856f-104">**Identificador de error:** BC30451</span><span class="sxs-lookup"><span data-stu-id="7856f-104">**Error ID:** BC30451</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="7856f-105">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="7856f-105">To correct this error</span></span>  
  
1. <span data-ttu-id="7856f-106">Compruebe que el nombre de la instrucción de referencia esté bien escrito.</span><span class="sxs-lookup"><span data-stu-id="7856f-106">Check the spelling of the name in the referring statement.</span></span> <span data-ttu-id="7856f-107">Visual Basic no distingue entre mayúsculas y minúsculas, pero cualquier otra variación en la ortografía se considera un nombre completamente diferente.</span><span class="sxs-lookup"><span data-stu-id="7856f-107">Visual Basic is case-insensitive, but any other variation in the spelling is regarded as a completely different name.</span></span> <span data-ttu-id="7856f-108">Tenga en cuenta que el carácter de subrayado (`_`) es parte del nombre y, por tanto, parte de la ortografía.</span><span class="sxs-lookup"><span data-stu-id="7856f-108">Note that the underscore (`_`) is part of the name and therefore part of the spelling.</span></span>  
  
2. <span data-ttu-id="7856f-109">Compruebe que tiene el operador de acceso a miembros ( `.` ) entre un objeto y su miembro.</span><span class="sxs-lookup"><span data-stu-id="7856f-109">Check that you have the member access operator (`.`) between an object and its member.</span></span> <span data-ttu-id="7856f-110">Por ejemplo, si tiene un control <xref:System.Windows.Forms.TextBox> denominado `TextBox1`, para tener acceso a su propiedad <xref:System.Windows.Forms.TextBoxBase.Text%2A> debe escribir `TextBox1.Text`.</span><span class="sxs-lookup"><span data-stu-id="7856f-110">For example, if you have a <xref:System.Windows.Forms.TextBox> control named `TextBox1`, to access its <xref:System.Windows.Forms.TextBoxBase.Text%2A> property you should type `TextBox1.Text`.</span></span> <span data-ttu-id="7856f-111">Si en su lugar escribe `TextBox1Text`, ha creado un nombre diferente.</span><span class="sxs-lookup"><span data-stu-id="7856f-111">If instead you type `TextBox1Text`, you have created a different name.</span></span>  
  
3. <span data-ttu-id="7856f-112">Si la ortografía es correcta y la sintaxis de cualquier acceso de miembro de objeto es correcta, compruebe que se ha declarado el elemento.</span><span class="sxs-lookup"><span data-stu-id="7856f-112">If the spelling is correct and the syntax of any object member access is correct, verify that the element has been declared.</span></span> <span data-ttu-id="7856f-113">Para obtener más información, vea [elementos declarados](../../programming-guide/language-features/declared-elements/index.md).</span><span class="sxs-lookup"><span data-stu-id="7856f-113">For more information, see [Declared Elements](../../programming-guide/language-features/declared-elements/index.md).</span></span>  
  
4. <span data-ttu-id="7856f-114">Si se ha declarado el elemento de programación, compruebe que está en el ámbito.</span><span class="sxs-lookup"><span data-stu-id="7856f-114">If the programming element has been declared, check that it is in scope.</span></span> <span data-ttu-id="7856f-115">Si la instrucción de referencia está fuera de la región que declara el elemento de programación, es posible que deba calificar el nombre del elemento.</span><span class="sxs-lookup"><span data-stu-id="7856f-115">If the referring statement is outside the region declaring the programming element, you might need to qualify the element name.</span></span> <span data-ttu-id="7856f-116">Para obtener más información, consulta [Scope in Visual Basic](../../programming-guide/language-features/declared-elements/scope.md).</span><span class="sxs-lookup"><span data-stu-id="7856f-116">For more information, see [Scope in Visual Basic](../../programming-guide/language-features/declared-elements/scope.md).</span></span>  

5. <span data-ttu-id="7856f-117">Si no usa un tipo completo o un nombre de miembro (por ejemplo, el código hace referencia a una propiedad como `MethodInfo.Name` en lugar de `System.Reflection.MethodInfo.Name` ), agregue una [instrucción Imports](../statements/imports-statement-net-namespace-and-type.md).</span><span class="sxs-lookup"><span data-stu-id="7856f-117">If you are not using a fully qualified type or type and member name (for example, your code refers to a property as `MethodInfo.Name` instead of `System.Reflection.MethodInfo.Name`), add an [Imports statement](../statements/imports-statement-net-namespace-and-type.md).</span></span>

6. <span data-ttu-id="7856f-118">Si intenta compilar un proyecto de estilo SDK (un proyecto con un \* archivo. vbproj que comienza con la línea `<Project Sdk="Microsoft.NET.Sdk">` ) y el mensaje de error hace referencia a un tipo o miembro del ensamblado Microsoft.VisualBasic.dll, configure la aplicación para que se compile con una referencia a la biblioteca en tiempo de ejecución de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="7856f-118">If you are attempting to compile an SDK-style project (a project with a \*.vbproj file that begins with the line `<Project Sdk="Microsoft.NET.Sdk">`), and the error message refers to a type or member in the Microsoft.VisualBasic.dll assembly, configure your application to compile with a reference to the Visual Basic Runtime Library.</span></span> <span data-ttu-id="7856f-119">De forma predeterminada, un subconjunto de la biblioteca se incrusta en el ensamblado en un proyecto de estilo SDK.</span><span class="sxs-lookup"><span data-stu-id="7856f-119">By default, a subset of the library is embedded in your assembly in an SDK-style project.</span></span>

   <span data-ttu-id="7856f-120">Por ejemplo, el ejemplo siguiente no se compila porque <xref:Microsoft.VisualBasic.CompilerServices.Conversions.ChangeType%2A?displayProperty=fullName> no se puede encontrar el método.</span><span class="sxs-lookup"><span data-stu-id="7856f-120">For example, the following example fails to compile because the <xref:Microsoft.VisualBasic.CompilerServices.Conversions.ChangeType%2A?displayProperty=fullName> method cannot be found.</span></span> <span data-ttu-id="7856f-121">No se incrusta en el subconjunto del tiempo de ejecución de Visual Basic incluido en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7856f-121">It is not embedded in the subset of the Visual Basic Runtime included with your application.</span></span>  

   [!code-vb[BC30451](~/samples/snippets/visualbasic/language-reference/error-messages/bc30451/program1.vb?highlight=7)]

   <span data-ttu-id="7856f-122">Para solucionar este error, agregue el `<VBRuntime>Default</VBRuntime>` elemento a la sección de proyectos `<PropertyGroup>` , como se muestra en el siguiente archivo de proyecto de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="7856f-122">To address this error, add the `<VBRuntime>Default</VBRuntime>` element to the projects `<PropertyGroup>` section, as the following Visual Basic project file shows.</span></span>

   [!code-xml[BC30451](~/samples/snippets/visualbasic/language-reference/error-messages/bc30451/vbruntime.vbproj?highlight=6)]

## <a name="see-also"></a><span data-ttu-id="7856f-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7856f-123">See also</span></span>

- [<span data-ttu-id="7856f-124">Resumen de las constantes y declaraciones</span><span class="sxs-lookup"><span data-stu-id="7856f-124">Declarations and Constants Summary</span></span>](../keywords/declarations-and-constants-summary.md)
- [<span data-ttu-id="7856f-125">Convenciones de nomenclatura de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7856f-125">Visual Basic Naming Conventions</span></span>](../../programming-guide/program-structure/naming-conventions.md)
- [<span data-ttu-id="7856f-126">Declared Element Names</span><span class="sxs-lookup"><span data-stu-id="7856f-126">Declared Element Names</span></span>](../../programming-guide/language-features/declared-elements/declared-element-names.md)
- [<span data-ttu-id="7856f-127">References to Declared Elements</span><span class="sxs-lookup"><span data-stu-id="7856f-127">References to Declared Elements</span></span>](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)
