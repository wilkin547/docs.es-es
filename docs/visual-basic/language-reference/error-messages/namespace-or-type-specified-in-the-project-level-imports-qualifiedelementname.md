---
title: El espacio de nombres o tipo especificado en las importaciones del proyecto '<qualifiedelementname>' no tiene miembros públicos o no se encuentra
ms.date: 07/20/2015
f1_keywords:
- vbc40057
- bc40057
helpviewer_keywords:
- BC40057
ms.assetid: 4ae3506e-2ebe-4ff3-995d-14ac60db5e9f
ms.openlocfilehash: 0ee235252d69e6f77ce53b048f45e73d0969e864
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409457"
---
# <a name="namespace-or-type-specified-in-the-project-level-imports-qualifiedelementname-doesnt-contain-any-public-member-or-cannot-be-found"></a><span data-ttu-id="4c24a-102">El espacio de nombres o tipo especificado en las importaciones del proyecto '\<qualifiedelementname>' no tiene miembros públicos o no se encuentra</span><span class="sxs-lookup"><span data-stu-id="4c24a-102">Namespace or type specified in the project-level Imports '\<qualifiedelementname>' doesn't contain any public member or cannot be found</span></span>
<span data-ttu-id="4c24a-103">El espacio de nombres o tipo especificado en las importaciones de nivel de proyecto ' \<qualifiedelementname> ' no contiene ningún miembro público o no se encuentra.</span><span class="sxs-lookup"><span data-stu-id="4c24a-103">Namespace or type specified in the project-level Imports '\<qualifiedelementname>' doesn't contain any public member or cannot be found.</span></span> <span data-ttu-id="4c24a-104">Asegúrese de que el espacio de nombres o el tipo estén definidos y que contenga al menos un miembro público.</span><span class="sxs-lookup"><span data-stu-id="4c24a-104">Make sure the namespace or the type is defined and contains at least one public member.</span></span> <span data-ttu-id="4c24a-105">Asegúrese de que el nombre de alias no contenga otros alias.</span><span class="sxs-lookup"><span data-stu-id="4c24a-105">Make sure the alias name doesn't contain other aliases.</span></span>  
  
 <span data-ttu-id="4c24a-106">Una propiedad Import de un proyecto especifica un elemento contenedor que no se puede encontrar o no define ningún `Public` miembro.</span><span class="sxs-lookup"><span data-stu-id="4c24a-106">An import property of a project specifies a containing element that either cannot be found or does not define any `Public` members.</span></span>  
  
 <span data-ttu-id="4c24a-107">Un *elemento contenedor* puede ser un espacio de nombres, una clase, una estructura, un módulo, una interfaz o una enumeración.</span><span class="sxs-lookup"><span data-stu-id="4c24a-107">A *containing element* can be a namespace, class, structure, module, interface, or enumeration.</span></span> <span data-ttu-id="4c24a-108">El elemento contenedor contiene miembros, como variables, procedimientos u otros elementos contenedores.</span><span class="sxs-lookup"><span data-stu-id="4c24a-108">The containing element contains members, such as variables, procedures, or other containing elements.</span></span>  
  
 <span data-ttu-id="4c24a-109">El propósito de la importación es permitir que el código tenga acceso a los miembros de espacio de nombres o de tipo sin tener que calificarlos.</span><span class="sxs-lookup"><span data-stu-id="4c24a-109">The purpose of importing is to allow your code to access namespace or type members without having to qualify them.</span></span> <span data-ttu-id="4c24a-110">Es posible que el proyecto también tenga que agregar una referencia al espacio de nombres o al tipo.</span><span class="sxs-lookup"><span data-stu-id="4c24a-110">Your project might also need to add a reference to the namespace or type.</span></span> <span data-ttu-id="4c24a-111">Para obtener más información, vea "importar elementos contenedores" en [referencias a elementos declarados](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span><span class="sxs-lookup"><span data-stu-id="4c24a-111">For more information, see "Importing Containing Elements" in [References to Declared Elements](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
 <span data-ttu-id="4c24a-112">Si el compilador no encuentra el elemento contenedor especificado, no puede resolver las referencias que lo usan.</span><span class="sxs-lookup"><span data-stu-id="4c24a-112">If the compiler cannot find the specified containing element, then it cannot resolve references that use it.</span></span> <span data-ttu-id="4c24a-113">Si encuentra el elemento pero el elemento no expone ningún `Public` miembro, no se puede realizar ninguna referencia correctamente.</span><span class="sxs-lookup"><span data-stu-id="4c24a-113">If it finds the element but the element does not expose any `Public` members, then no reference can be successful.</span></span> <span data-ttu-id="4c24a-114">En cualquier caso, no tiene sentido importar el elemento.</span><span class="sxs-lookup"><span data-stu-id="4c24a-114">In either case it is meaningless to import the element.</span></span>  
  
 <span data-ttu-id="4c24a-115">El diseñador de **proyectos** se usa para especificar los elementos que se van a importar.</span><span class="sxs-lookup"><span data-stu-id="4c24a-115">You use the **Project Designer** to specify elements to import.</span></span> <span data-ttu-id="4c24a-116">Use la sección **espacios de nombres importados** de la página **referencias** .</span><span class="sxs-lookup"><span data-stu-id="4c24a-116">Use the **Imported namespaces** section of the **References** page.</span></span> <span data-ttu-id="4c24a-117">Para obtener acceso al **Diseñador de proyectos** , haga doble clic en el icono **mi proyecto** en **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="4c24a-117">You can get to the **Project Designer** by double-clicking the **My Project** icon in **Solution Explorer**.</span></span>  
  
 <span data-ttu-id="4c24a-118">**Identificador de error:** BC40057</span><span class="sxs-lookup"><span data-stu-id="4c24a-118">**Error ID:** BC40057</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="4c24a-119">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="4c24a-119">To correct this error</span></span>  
  
1. <span data-ttu-id="4c24a-120">Abra el **Diseñador de proyectos** y cambie a la página de **referencia** .</span><span class="sxs-lookup"><span data-stu-id="4c24a-120">Open the **Project Designer** and switch to the **Reference** page.</span></span>  
  
2. <span data-ttu-id="4c24a-121">En la sección **espacios de nombres importados** , compruebe que el elemento contenedor es accesible desde el proyecto.</span><span class="sxs-lookup"><span data-stu-id="4c24a-121">In the **Imported namespaces** section, verify that the containing element is accessible from your project.</span></span>  
  
3. <span data-ttu-id="4c24a-122">Compruebe que el elemento contenedor expone al menos un `Public` miembro.</span><span class="sxs-lookup"><span data-stu-id="4c24a-122">Verify that the containing element exposes at least one `Public` member.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c24a-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4c24a-123">See also</span></span>

- [<span data-ttu-id="4c24a-124">Página Referencias, Diseñador de proyectos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4c24a-124">References Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/references-page-project-designer-visual-basic)
- [<span data-ttu-id="4c24a-125">Administrar propiedades de soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="4c24a-125">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
- [<span data-ttu-id="4c24a-126">Público</span><span class="sxs-lookup"><span data-stu-id="4c24a-126">Public</span></span>](../modifiers/public.md)
- [<span data-ttu-id="4c24a-127">Espacios de nombres en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4c24a-127">Namespaces in Visual Basic</span></span>](../../programming-guide/program-structure/namespaces.md)
- [<span data-ttu-id="4c24a-128">References to Declared Elements</span><span class="sxs-lookup"><span data-stu-id="4c24a-128">References to Declared Elements</span></span>](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)
