---
title: "Namespace o el tipo especificado en las importaciones de nivel de proyecto &#39; &lt;nombrecompletoelemento&gt;&#39; &#39; t contienen ningún miembro público o no se encuentra"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc40057
- bc40057
helpviewer_keywords:
- BC40057
ms.assetid: 4ae3506e-2ebe-4ff3-995d-14ac60db5e9f
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0d0a164562524af239b3b130f681dbc6eff23814
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="namespace-or-type-specified-in-the-project-level-imports-39ltqualifiedelementnamegt39-doesn39t-contain-any-public-member-or-cannot-be-found"></a><span data-ttu-id="9f20c-102">Namespace o el tipo especificado en las importaciones de nivel de proyecto &#39; &lt;nombrecompletoelemento&gt;&#39; &#39; t contienen ningún miembro público o no se encuentra</span><span class="sxs-lookup"><span data-stu-id="9f20c-102">Namespace or type specified in the project-level Imports &#39;&lt;qualifiedelementname&gt;&#39; doesn&#39;t contain any public member or cannot be found</span></span>
<span data-ttu-id="9f20c-103">Namespace o el tipo especificado en las importaciones de nivel de proyecto\<nombrecompletoelemento >' no contienen ningún miembro público o no se encuentra.</span><span class="sxs-lookup"><span data-stu-id="9f20c-103">Namespace or type specified in the project-level Imports '\<qualifiedelementname>' doesn't contain any public member or cannot be found.</span></span> <span data-ttu-id="9f20c-104">Asegúrese de que el espacio de nombres o el tipo se define y contiene a al menos un miembro público.</span><span class="sxs-lookup"><span data-stu-id="9f20c-104">Make sure the namespace or the type is defined and contains at least one public member.</span></span> <span data-ttu-id="9f20c-105">Asegúrese de que el nombre de alias no contiene otros alias.</span><span class="sxs-lookup"><span data-stu-id="9f20c-105">Make sure the alias name doesn't contain other aliases.</span></span>  
  
 <span data-ttu-id="9f20c-106">Una propiedad de importación de un proyecto especifica un elemento contenedor que no se puede encontrar o no define `Public` miembros.</span><span class="sxs-lookup"><span data-stu-id="9f20c-106">An import property of a project specifies a containing element that either cannot be found or does not define any `Public` members.</span></span>  
  
 <span data-ttu-id="9f20c-107">A *que contiene el elemento* puede ser un espacio de nombres, clase, estructura, módulo, interfaz o enumeración.</span><span class="sxs-lookup"><span data-stu-id="9f20c-107">A *containing element* can be a namespace, class, structure, module, interface, or enumeration.</span></span> <span data-ttu-id="9f20c-108">El elemento contenedor incluye a miembros, como variables, procedimientos u otros elementos que lo contiene.</span><span class="sxs-lookup"><span data-stu-id="9f20c-108">The containing element contains members, such as variables, procedures, or other containing elements.</span></span>  
  
 <span data-ttu-id="9f20c-109">El propósito de la importación es permitir que el código para obtener acceso a los miembros de tipo o espacio de nombres sin tener que calificarlos.</span><span class="sxs-lookup"><span data-stu-id="9f20c-109">The purpose of importing is to allow your code to access namespace or type members without having to qualify them.</span></span> <span data-ttu-id="9f20c-110">El proyecto también necesite agregar una referencia a un tipo o espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="9f20c-110">Your project might also need to add a reference to the namespace or type.</span></span> <span data-ttu-id="9f20c-111">Para obtener más información, vea "Importar elementos contenedores" en [referencias a elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span><span class="sxs-lookup"><span data-stu-id="9f20c-111">For more information, see "Importing Containing Elements" in [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
 <span data-ttu-id="9f20c-112">Si el compilador no puede encontrar el elemento contenedor especificado, no se puede resolver las referencias que lo usan.</span><span class="sxs-lookup"><span data-stu-id="9f20c-112">If the compiler cannot find the specified containing element, then it cannot resolve references that use it.</span></span> <span data-ttu-id="9f20c-113">Si encuentra el elemento pero el elemento no exponen ninguno `Public` miembros, ninguna referencia puede ser correcta.</span><span class="sxs-lookup"><span data-stu-id="9f20c-113">If it finds the element but the element does not expose any `Public` members, then no reference can be successful.</span></span> <span data-ttu-id="9f20c-114">En cualquier caso, tiene sentido para importar el elemento.</span><span class="sxs-lookup"><span data-stu-id="9f20c-114">In either case it is meaningless to import the element.</span></span>  
  
 <span data-ttu-id="9f20c-115">Usa el **Diseñador de proyectos** para especificar los elementos que se va a importar.</span><span class="sxs-lookup"><span data-stu-id="9f20c-115">You use the **Project Designer** to specify elements to import.</span></span> <span data-ttu-id="9f20c-116">Use la **espacios de nombres importados** sección de la **referencias** página.</span><span class="sxs-lookup"><span data-stu-id="9f20c-116">Use the **Imported namespaces** section of the **References** page.</span></span> <span data-ttu-id="9f20c-117">Puede tener acceso a la **Diseñador de proyectos** haciendo doble clic en el **mi proyecto** icono en **el Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="9f20c-117">You can get to the **Project Designer** by double-clicking the **My Project** icon in **Solution Explorer**.</span></span>  
  
 <span data-ttu-id="9f20c-118">**Id. de error:** BC40057</span><span class="sxs-lookup"><span data-stu-id="9f20c-118">**Error ID:** BC40057</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="9f20c-119">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="9f20c-119">To correct this error</span></span>  
  
1.  <span data-ttu-id="9f20c-120">Abra la **Diseñador de proyectos** y cambie a la **referencia** página.</span><span class="sxs-lookup"><span data-stu-id="9f20c-120">Open the **Project Designer** and switch to the **Reference** page.</span></span>  
  
2.  <span data-ttu-id="9f20c-121">En el **espacios de nombres importados** sección, compruebe que el elemento contenedor es accesible desde el proyecto.</span><span class="sxs-lookup"><span data-stu-id="9f20c-121">In the **Imported namespaces** section, verify that the containing element is accessible from your project.</span></span>  
  
3.  <span data-ttu-id="9f20c-122">Compruebe que el elemento contenedor expone al menos una `Public` miembro.</span><span class="sxs-lookup"><span data-stu-id="9f20c-122">Verify that the containing element exposes at least one `Public` member.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f20c-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="9f20c-123">See Also</span></span>  
 [<span data-ttu-id="9f20c-124">Página Referencias, Diseñador de proyectos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9f20c-124">References Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/references-page-project-designer-visual-basic)  
 [<span data-ttu-id="9f20c-125">Administrar propiedades de soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="9f20c-125">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)  
 [<span data-ttu-id="9f20c-126">Public</span><span class="sxs-lookup"><span data-stu-id="9f20c-126">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
 [<span data-ttu-id="9f20c-127">Espacios de nombres en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9f20c-127">Namespaces in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/namespaces.md)  
 [<span data-ttu-id="9f20c-128">Referencias a elementos declarados</span><span class="sxs-lookup"><span data-stu-id="9f20c-128">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
