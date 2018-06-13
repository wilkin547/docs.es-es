---
title: Namespace o el tipo especificado en las importaciones &#39; &lt;nombrecompletoelemento&gt; &#39; &#39;t contienen ningún miembro público o no se encuentra
ms.date: 07/20/2015
f1_keywords:
- bc40056
- vbc40056
helpviewer_keywords:
- BC40056
ms.assetid: b59f5754-444f-4378-9272-9678b437e84a
ms.openlocfilehash: 8be0df5cbe4b8d4a640c9b6c2e126b3828254fd6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33595110"
---
# <a name="namespace-or-type-specified-in-the-imports-39ltqualifiedelementnamegt39-doesn39t-contain-any-public-member-or-cannot-be-found"></a><span data-ttu-id="e5b1c-102">Namespace o el tipo especificado en las importaciones &#39; &lt;nombrecompletoelemento&gt; &#39; &#39;t contienen ningún miembro público o no se encuentra</span><span class="sxs-lookup"><span data-stu-id="e5b1c-102">Namespace or type specified in the Imports &#39;&lt;qualifiedelementname&gt;&#39; doesn&#39;t contain any public member or cannot be found</span></span>
<span data-ttu-id="e5b1c-103">Namespace o el tipo especificado en las importaciones\<nombrecompletoelemento >' no contienen ningún miembro público o no se encuentra.</span><span class="sxs-lookup"><span data-stu-id="e5b1c-103">Namespace or type specified in the Imports '\<qualifiedelementname>' doesn't contain any public member or cannot be found.</span></span> <span data-ttu-id="e5b1c-104">Asegúrese de que el espacio de nombres o el tipo se define y contiene a al menos un miembro público.</span><span class="sxs-lookup"><span data-stu-id="e5b1c-104">Make sure the namespace or the type is defined and contains at least one public member.</span></span> <span data-ttu-id="e5b1c-105">Asegúrese de que el nombre de alias no contiene otros alias.</span><span class="sxs-lookup"><span data-stu-id="e5b1c-105">Make sure the alias name doesn't contain other aliases.</span></span>  
  
 <span data-ttu-id="e5b1c-106">Un `Imports` instrucción especifica un elemento contenedor que no se puede encontrar o no define `Public` miembros.</span><span class="sxs-lookup"><span data-stu-id="e5b1c-106">An `Imports` statement specifies a containing element that either cannot be found or does not define any `Public` members.</span></span>  
  
 <span data-ttu-id="e5b1c-107">A *que contiene el elemento* puede ser un espacio de nombres, clase, estructura, módulo, interfaz o enumeración.</span><span class="sxs-lookup"><span data-stu-id="e5b1c-107">A *containing element* can be a namespace, class, structure, module, interface, or enumeration.</span></span> <span data-ttu-id="e5b1c-108">El elemento contenedor incluye a miembros, como variables, procedimientos u otros elementos que lo contiene.</span><span class="sxs-lookup"><span data-stu-id="e5b1c-108">The containing element contains members, such as variables, procedures, or other containing elements.</span></span>  
  
 <span data-ttu-id="e5b1c-109">El propósito de la importación es permitir que el código para obtener acceso a los miembros de tipo o espacio de nombres sin tener que calificarlos.</span><span class="sxs-lookup"><span data-stu-id="e5b1c-109">The purpose of importing is to allow your code to access namespace or type members without having to qualify them.</span></span> <span data-ttu-id="e5b1c-110">El proyecto también necesite agregar una referencia a un tipo o espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="e5b1c-110">Your project might also need to add a reference to the namespace or type.</span></span> <span data-ttu-id="e5b1c-111">Para obtener más información, vea "Importar elementos contenedores" en [referencias a elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span><span class="sxs-lookup"><span data-stu-id="e5b1c-111">For more information, see "Importing Containing Elements" in [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
 <span data-ttu-id="e5b1c-112">Si el compilador no puede encontrar el elemento contenedor especificado, no se puede resolver las referencias que lo usan.</span><span class="sxs-lookup"><span data-stu-id="e5b1c-112">If the compiler cannot find the specified containing element, then it cannot resolve references that use it.</span></span> <span data-ttu-id="e5b1c-113">Si encuentra el elemento pero el elemento no exponen ninguno `Public` miembros, ninguna referencia puede ser correcta.</span><span class="sxs-lookup"><span data-stu-id="e5b1c-113">If it finds the element but the element does not expose any `Public` members, then no reference can be successful.</span></span> <span data-ttu-id="e5b1c-114">En cualquier caso, tiene sentido para importar el elemento.</span><span class="sxs-lookup"><span data-stu-id="e5b1c-114">In either case it is meaningless to import the element.</span></span>  
  
 <span data-ttu-id="e5b1c-115">Tenga en cuenta que si importa un elemento contenedor y asignarles un alias de importación, a continuación, no puede utilizar ese alias de importación para importar ningún otro elemento.</span><span class="sxs-lookup"><span data-stu-id="e5b1c-115">Keep in mind that if you import a containing element and assign an import alias to it, then you cannot use that import alias to import another element.</span></span> <span data-ttu-id="e5b1c-116">El código siguiente genera un error del compilador.</span><span class="sxs-lookup"><span data-stu-id="e5b1c-116">The following code generates a compiler error.</span></span>  
  
 <span data-ttu-id="e5b1c-117">`Imports`   `winfrm`   `= System.Windows.Forms`</span><span class="sxs-lookup"><span data-stu-id="e5b1c-117">`Imports`   `winfrm`   `= System.Windows.Forms`</span></span>  
  
 <span data-ttu-id="e5b1c-118">`' The following statement is`   `INVALID`   `because it reuses an import alias.`</span><span class="sxs-lookup"><span data-stu-id="e5b1c-118">`' The following statement is`   `INVALID`   `because it reuses an import alias.`</span></span>  
  
 <span data-ttu-id="e5b1c-119">`Imports behav =`   `winfrm`  `.Design.Behavior`</span><span class="sxs-lookup"><span data-stu-id="e5b1c-119">`Imports behav =`   `winfrm`  `.Design.Behavior`</span></span>  
  
 <span data-ttu-id="e5b1c-120">**Id. de error:** BC40056</span><span class="sxs-lookup"><span data-stu-id="e5b1c-120">**Error ID:** BC40056</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e5b1c-121">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="e5b1c-121">To correct this error</span></span>  
  
1.  <span data-ttu-id="e5b1c-122">Compruebe que el elemento contenedor es accesible desde el proyecto.</span><span class="sxs-lookup"><span data-stu-id="e5b1c-122">Verify that the containing element is accessible from your project.</span></span>  
  
2.  <span data-ttu-id="e5b1c-123">Compruebe que la especificación del elemento contenedor no incluye ningún alias de importación de importación en otro.</span><span class="sxs-lookup"><span data-stu-id="e5b1c-123">Verify that the specification of the containing element does not include any import alias from another import.</span></span>  
  
3.  <span data-ttu-id="e5b1c-124">Compruebe que el elemento contenedor expone al menos una `Public` miembro.</span><span class="sxs-lookup"><span data-stu-id="e5b1c-124">Verify that the containing element exposes at least one `Public` member.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5b1c-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="e5b1c-125">See Also</span></span>  
 [<span data-ttu-id="e5b1c-126">Imports (instrucción), espacio de nombres y tipo .NET</span><span class="sxs-lookup"><span data-stu-id="e5b1c-126">Imports Statement (.NET Namespace and Type)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)  
 [<span data-ttu-id="e5b1c-127">Namespace (instrucción)</span><span class="sxs-lookup"><span data-stu-id="e5b1c-127">Namespace Statement</span></span>](../../../visual-basic/language-reference/statements/namespace-statement.md)  
 [<span data-ttu-id="e5b1c-128">Public</span><span class="sxs-lookup"><span data-stu-id="e5b1c-128">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
 [<span data-ttu-id="e5b1c-129">Espacios de nombres en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e5b1c-129">Namespaces in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/namespaces.md)  
 [<span data-ttu-id="e5b1c-130">Referencias a elementos declarados</span><span class="sxs-lookup"><span data-stu-id="e5b1c-130">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
