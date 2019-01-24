---
title: Tipo de miembro &#39; &lt;membername&gt; &#39; no es conforme a CLS
ms.date: 07/20/2015
f1_keywords:
- bc40025
- vbc40025
helpviewer_keywords:
- BC40025
ms.assetid: adbd34bb-43d2-4266-90e7-cd1afaf49b4e
ms.openlocfilehash: b304b28aa7d43a33111c49507bf02f004fcdd9c6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54603857"
---
# <a name="type-of-member-39ltmembernamegt39-is-not-cls-compliant"></a><span data-ttu-id="43d4d-102">Tipo de miembro &#39; &lt;membername&gt; &#39; no es conforme a CLS</span><span class="sxs-lookup"><span data-stu-id="43d4d-102">Type of member &#39;&lt;membername&gt;&#39; is not CLS-compliant</span></span>
<span data-ttu-id="43d4d-103">El tipo de datos especificado para este miembro no es parte de la [independencia del lenguaje y componentes independientes del lenguaje](../../../standard/language-independence-and-language-independent-components.md) (CLS).</span><span class="sxs-lookup"><span data-stu-id="43d4d-103">The data type specified for this member is not part of the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS).</span></span> <span data-ttu-id="43d4d-104">Esto no es un error en su componente, porque el [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] y Visual Basic admite este tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="43d4d-104">This is not an error within your component, because the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] and Visual Basic support this data type.</span></span> <span data-ttu-id="43d4d-105">Sin embargo, es posible que otro componente escrito en código estrictamente conforme a CLS no admite este tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="43d4d-105">However, another component written in strictly CLS-compliant code might not support this data type.</span></span> <span data-ttu-id="43d4d-106">Es posible que este componente no pueda interactuar correctamente con el componente.</span><span class="sxs-lookup"><span data-stu-id="43d4d-106">Such a component might not be able to interact successfully with your component.</span></span>  
  
 <span data-ttu-id="43d4d-107">Los siguientes tipos de datos de Visual Basic no son conformes a CLS:</span><span class="sxs-lookup"><span data-stu-id="43d4d-107">The following Visual Basic data types are not CLS-compliant:</span></span>  
  
-   [<span data-ttu-id="43d4d-108">SByte (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="43d4d-108">SByte Data Type</span></span>](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [<span data-ttu-id="43d4d-109">UInteger (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="43d4d-109">UInteger Data Type</span></span>](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [<span data-ttu-id="43d4d-110">ULong (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="43d4d-110">ULong Data Type</span></span>](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [<span data-ttu-id="43d4d-111">UShort (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="43d4d-111">UShort Data Type</span></span>](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 <span data-ttu-id="43d4d-112">De forma predeterminada, este mensaje es una advertencia.</span><span class="sxs-lookup"><span data-stu-id="43d4d-112">By default, this message is a warning.</span></span> <span data-ttu-id="43d4d-113">Para obtener más información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="43d4d-113">For more information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="43d4d-114">**Identificador de error:** BC40025</span><span class="sxs-lookup"><span data-stu-id="43d4d-114">**Error ID:** BC40025</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="43d4d-115">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="43d4d-115">To correct this error</span></span>  
  
-   <span data-ttu-id="43d4d-116">Si el componente interactúa con otros [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] componentes o no se comunica con otros componentes, no es necesario cambiar nada.</span><span class="sxs-lookup"><span data-stu-id="43d4d-116">If your component interfaces only with other [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] components, or does not interface with any other components, you do not need to change anything.</span></span>  
  
-   <span data-ttu-id="43d4d-117">Si trabaja con un componente no está escrito para la [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], es posible que pueda determinar, ya sea mediante reflexión o de documentación, si admite este tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="43d4d-117">If you are interfacing with a component not written for the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], you might be able to determine, either through reflection or from documentation, whether it supports this data type.</span></span> <span data-ttu-id="43d4d-118">Si es así, no es necesario cambiar nada.</span><span class="sxs-lookup"><span data-stu-id="43d4d-118">If it does, you do not need to change anything.</span></span>  
  
-   <span data-ttu-id="43d4d-119">Si trabaja con un componente que no admite este tipo de datos, debe reemplazar con el tipo conforme a CLS más próximo.</span><span class="sxs-lookup"><span data-stu-id="43d4d-119">If you are interfacing with a component that does not support this data type, you must replace it with the closest CLS-compliant type.</span></span> <span data-ttu-id="43d4d-120">Por ejemplo, en lugar de `UInteger` , quizá pueda usar `Integer` si no necesita que el intervalo de valores esté por encima de 2.147.483.647.</span><span class="sxs-lookup"><span data-stu-id="43d4d-120">For example, in place of `UInteger` you might be able to use `Integer` if you do not need the value range above 2,147,483,647.</span></span> <span data-ttu-id="43d4d-121">Si necesita el intervalo extendido, puede reemplazar `UInteger` por `Long`.</span><span class="sxs-lookup"><span data-stu-id="43d4d-121">If you do need the extended range, you can replace `UInteger` with `Long`.</span></span>  
  
-   <span data-ttu-id="43d4d-122">Si trabaja con objetos de automatización o COM, tenga en cuenta que algunos tipos tienen anchos de datos distintos que en [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="43d4d-122">If you are interfacing with Automation or COM objects, keep in mind that some types have different data widths than in the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="43d4d-123">Por ejemplo, `uint` suele ser de 16 bits en otros entornos.</span><span class="sxs-lookup"><span data-stu-id="43d4d-123">For example, `uint` is often 16 bits in other environments.</span></span> <span data-ttu-id="43d4d-124">Si se pasa un argumento de 16 bits a esos componentes, declárelo como `UShort` en lugar de `UInteger` en el código administrado de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="43d4d-124">If you are passing a 16-bit argument to such a component, declare it as `UShort` instead of `UInteger` in your managed Visual Basic code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43d4d-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="43d4d-125">See also</span></span>
- [<span data-ttu-id="43d4d-126">Reflexión</span><span class="sxs-lookup"><span data-stu-id="43d4d-126">Reflection</span></span>](../../../framework/reflection-and-codedom/reflection.md)

