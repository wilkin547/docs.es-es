---
description: "Más información acerca de: BC40057: el espacio de nombres o tipo especificado en las importaciones de nivel de proyecto ' <qualifiedelementname> ' no contiene ningún miembro público o no se encuentra"
title: El espacio de nombres o tipo especificado en las importaciones del proyecto '<qualifiedelementname>' no tiene miembros públicos o no se encuentra
ms.date: 07/20/2015
f1_keywords:
- vbc40057
- bc40057
helpviewer_keywords:
- BC40057
ms.assetid: 4ae3506e-2ebe-4ff3-995d-14ac60db5e9f
ms.openlocfilehash: 66ae40ca6a2feff78f80bdbc8886387e801f7db2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795695"
---
# <a name="bc40057-namespace-or-type-specified-in-the-project-level-imports-qualifiedelementname-doesnt-contain-any-public-member-or-cannot-be-found"></a><span data-ttu-id="8ea74-103">BC40057: el espacio de nombres o tipo especificado en las importaciones de nivel de proyecto ' \<qualifiedelementname> ' no contiene ningún miembro público o no se encuentra.</span><span class="sxs-lookup"><span data-stu-id="8ea74-103">BC40057: Namespace or type specified in the project-level Imports '\<qualifiedelementname>' doesn't contain any public member or cannot be found</span></span>

<span data-ttu-id="8ea74-104">El espacio de nombres o tipo especificado en las importaciones de nivel de proyecto ' \<qualifiedelementname> ' no contiene ningún miembro público o no se encuentra.</span><span class="sxs-lookup"><span data-stu-id="8ea74-104">Namespace or type specified in the project-level Imports '\<qualifiedelementname>' doesn't contain any public member or cannot be found.</span></span> <span data-ttu-id="8ea74-105">Asegúrese de que el espacio de nombres o el tipo estén definidos y que contenga al menos un miembro público.</span><span class="sxs-lookup"><span data-stu-id="8ea74-105">Make sure the namespace or the type is defined and contains at least one public member.</span></span> <span data-ttu-id="8ea74-106">Asegúrese de que el nombre de alias no contenga otros alias.</span><span class="sxs-lookup"><span data-stu-id="8ea74-106">Make sure the alias name doesn't contain other aliases.</span></span>

 <span data-ttu-id="8ea74-107">Una propiedad Import de un proyecto especifica un elemento contenedor que no se puede encontrar o no define ningún `Public` miembro.</span><span class="sxs-lookup"><span data-stu-id="8ea74-107">An import property of a project specifies a containing element that either cannot be found or does not define any `Public` members.</span></span>

 <span data-ttu-id="8ea74-108">Un *elemento contenedor* puede ser un espacio de nombres, una clase, una estructura, un módulo, una interfaz o una enumeración.</span><span class="sxs-lookup"><span data-stu-id="8ea74-108">A *containing element* can be a namespace, class, structure, module, interface, or enumeration.</span></span> <span data-ttu-id="8ea74-109">El elemento contenedor contiene miembros, como variables, procedimientos u otros elementos contenedores.</span><span class="sxs-lookup"><span data-stu-id="8ea74-109">The containing element contains members, such as variables, procedures, or other containing elements.</span></span>

 <span data-ttu-id="8ea74-110">El propósito de la importación es permitir que el código tenga acceso a los miembros de espacio de nombres o de tipo sin tener que calificarlos.</span><span class="sxs-lookup"><span data-stu-id="8ea74-110">The purpose of importing is to allow your code to access namespace or type members without having to qualify them.</span></span> <span data-ttu-id="8ea74-111">Es posible que el proyecto también tenga que agregar una referencia al espacio de nombres o al tipo.</span><span class="sxs-lookup"><span data-stu-id="8ea74-111">Your project might also need to add a reference to the namespace or type.</span></span> <span data-ttu-id="8ea74-112">Para obtener más información, vea "importar elementos contenedores" en [referencias a elementos declarados](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span><span class="sxs-lookup"><span data-stu-id="8ea74-112">For more information, see "Importing Containing Elements" in [References to Declared Elements](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>

 <span data-ttu-id="8ea74-113">Si el compilador no encuentra el elemento contenedor especificado, no puede resolver las referencias que lo usan.</span><span class="sxs-lookup"><span data-stu-id="8ea74-113">If the compiler cannot find the specified containing element, then it cannot resolve references that use it.</span></span> <span data-ttu-id="8ea74-114">Si encuentra el elemento pero el elemento no expone ningún `Public` miembro, no se puede realizar ninguna referencia correctamente.</span><span class="sxs-lookup"><span data-stu-id="8ea74-114">If it finds the element but the element does not expose any `Public` members, then no reference can be successful.</span></span> <span data-ttu-id="8ea74-115">En cualquier caso, no tiene sentido importar el elemento.</span><span class="sxs-lookup"><span data-stu-id="8ea74-115">In either case it is meaningless to import the element.</span></span>

 <span data-ttu-id="8ea74-116">El diseñador de **proyectos** se usa para especificar los elementos que se van a importar.</span><span class="sxs-lookup"><span data-stu-id="8ea74-116">You use the **Project Designer** to specify elements to import.</span></span> <span data-ttu-id="8ea74-117">Use la sección **espacios de nombres importados** de la página **referencias** .</span><span class="sxs-lookup"><span data-stu-id="8ea74-117">Use the **Imported namespaces** section of the **References** page.</span></span> <span data-ttu-id="8ea74-118">Para obtener acceso al **Diseñador de proyectos** , haga doble clic en el icono **mi proyecto** en **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="8ea74-118">You can get to the **Project Designer** by double-clicking the **My Project** icon in **Solution Explorer**.</span></span>

 <span data-ttu-id="8ea74-119">**Identificador de error:** BC40057</span><span class="sxs-lookup"><span data-stu-id="8ea74-119">**Error ID:** BC40057</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="8ea74-120">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="8ea74-120">To correct this error</span></span>

1. <span data-ttu-id="8ea74-121">Abra el **Diseñador de proyectos** y cambie a la página de **referencia** .</span><span class="sxs-lookup"><span data-stu-id="8ea74-121">Open the **Project Designer** and switch to the **Reference** page.</span></span>

2. <span data-ttu-id="8ea74-122">En la sección **espacios de nombres importados** , compruebe que el elemento contenedor es accesible desde el proyecto.</span><span class="sxs-lookup"><span data-stu-id="8ea74-122">In the **Imported namespaces** section, verify that the containing element is accessible from your project.</span></span>

3. <span data-ttu-id="8ea74-123">Compruebe que el elemento contenedor expone al menos un `Public` miembro.</span><span class="sxs-lookup"><span data-stu-id="8ea74-123">Verify that the containing element exposes at least one `Public` member.</span></span>

## <a name="see-also"></a><span data-ttu-id="8ea74-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8ea74-124">See also</span></span>

- [<span data-ttu-id="8ea74-125">Página Referencias, Diseñador de proyectos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8ea74-125">References Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/references-page-project-designer-visual-basic)
- [<span data-ttu-id="8ea74-126">Administrar propiedades de soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="8ea74-126">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
- [<span data-ttu-id="8ea74-127">Público</span><span class="sxs-lookup"><span data-stu-id="8ea74-127">Public</span></span>](../modifiers/public.md)
- [<span data-ttu-id="8ea74-128">Espacios de nombres en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8ea74-128">Namespaces in Visual Basic</span></span>](../../programming-guide/program-structure/namespaces.md)
- [<span data-ttu-id="8ea74-129">References to Declared Elements</span><span class="sxs-lookup"><span data-stu-id="8ea74-129">References to Declared Elements</span></span>](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)
