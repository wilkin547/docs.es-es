---
title: El tipo subyacente <typename> de Enum no es compatible con CLS
ms.date: 07/20/2015
f1_keywords:
- vbc40032
- bc40032
helpviewer_keywords:
- BC40032
ms.assetid: 32bf1949-fd73-456c-a323-bf1ffe1320ed
ms.openlocfilehash: b58759502b9297f9cd5ac89296ab147c40fc89f1
ms.sourcegitcommit: e08b319358a8025cc6aa38737854f7bdb87183d6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/29/2019
ms.locfileid: "64913359"
---
# <a name="underlying-type-typename-of-enum-is-not-cls-compliant"></a><span data-ttu-id="9456a-102">El tipo subyacente \<typename > de Enum no es conforme a CLS</span><span class="sxs-lookup"><span data-stu-id="9456a-102">Underlying type \<typename> of Enum is not CLS-compliant</span></span>
<span data-ttu-id="9456a-103">El tipo de datos especificado para esta enumeración no es parte de la [independencia del lenguaje y componentes independientes del lenguaje](../../../standard/language-independence-and-language-independent-components.md) (CLS).</span><span class="sxs-lookup"><span data-stu-id="9456a-103">The data type specified for this enumeration is not part of the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS).</span></span> <span data-ttu-id="9456a-104">Esto no es un error en su componente, porque el [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] y Visual Basic admite este tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="9456a-104">This is not an error within your component, because the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] and Visual Basic support this data type.</span></span> <span data-ttu-id="9456a-105">Sin embargo, es posible que otro componente escrito en código estrictamente conforme a CLS no admite este tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="9456a-105">However, another component written in strictly CLS-compliant code might not support this data type.</span></span> <span data-ttu-id="9456a-106">Es posible que este componente no pueda interactuar correctamente con el componente.</span><span class="sxs-lookup"><span data-stu-id="9456a-106">Such a component might not be able to interact successfully with your component.</span></span>  
  
 <span data-ttu-id="9456a-107">Los siguientes tipos de datos de Visual Basic no son conformes a CLS:</span><span class="sxs-lookup"><span data-stu-id="9456a-107">The following Visual Basic data types are not CLS-compliant:</span></span>  
  
- [<span data-ttu-id="9456a-108">SByte (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="9456a-108">SByte Data Type</span></span>](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
- [<span data-ttu-id="9456a-109">UInteger (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="9456a-109">UInteger Data Type</span></span>](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
- [<span data-ttu-id="9456a-110">ULong (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="9456a-110">ULong Data Type</span></span>](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
- [<span data-ttu-id="9456a-111">UShort (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="9456a-111">UShort Data Type</span></span>](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 <span data-ttu-id="9456a-112">De forma predeterminada, este mensaje es una advertencia.</span><span class="sxs-lookup"><span data-stu-id="9456a-112">By default, this message is a warning.</span></span> <span data-ttu-id="9456a-113">Para obtener más información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="9456a-113">For more information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="9456a-114">**Identificador de error:** BC40032</span><span class="sxs-lookup"><span data-stu-id="9456a-114">**Error ID:** BC40032</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="9456a-115">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="9456a-115">To correct this error</span></span>  
  
- <span data-ttu-id="9456a-116">Si el componente interactúa con otros [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] componentes o no se comunica con otros componentes, no es necesario cambiar nada.</span><span class="sxs-lookup"><span data-stu-id="9456a-116">If your component interfaces only with other [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] components, or does not interface with any other components, you do not need to change anything.</span></span>  
  
- <span data-ttu-id="9456a-117">Si trabaja con un componente no está escrito para la [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], es posible que pueda determinar, ya sea mediante reflexión o de documentación, si admite este tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="9456a-117">If you are interfacing with a component not written for the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], you might be able to determine, either through reflection or from documentation, whether it supports this data type.</span></span> <span data-ttu-id="9456a-118">Si es así, no es necesario cambiar nada.</span><span class="sxs-lookup"><span data-stu-id="9456a-118">If it does, you do not need to change anything.</span></span>  
  
- <span data-ttu-id="9456a-119">Si trabaja con un componente que no admite este tipo de datos, debe reemplazar con el tipo conforme a CLS más próximo.</span><span class="sxs-lookup"><span data-stu-id="9456a-119">If you are interfacing with a component that does not support this data type, you must replace it with the closest CLS-compliant type.</span></span> <span data-ttu-id="9456a-120">Por ejemplo, en lugar de `UInteger` , quizá pueda usar `Integer` si no necesita que el intervalo de valores esté por encima de 2.147.483.647.</span><span class="sxs-lookup"><span data-stu-id="9456a-120">For example, in place of `UInteger` you might be able to use `Integer` if you do not need the value range above 2,147,483,647.</span></span> <span data-ttu-id="9456a-121">Si necesita el intervalo extendido, puede reemplazar `UInteger` por `Long`.</span><span class="sxs-lookup"><span data-stu-id="9456a-121">If you do need the extended range, you can replace `UInteger` with `Long`.</span></span>  
  
- <span data-ttu-id="9456a-122">Si trabaja con objetos de automatización o COM, tenga en cuenta que algunos tipos tienen anchos de datos distintos que en [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9456a-122">If you are interfacing with Automation or COM objects, keep in mind that some types have different data widths than in the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="9456a-123">Por ejemplo, `uint` suele ser de 16 bits en otros entornos.</span><span class="sxs-lookup"><span data-stu-id="9456a-123">For example, `uint` is often 16 bits in other environments.</span></span> <span data-ttu-id="9456a-124">Si se pasa un argumento de 16 bits a esos componentes, declárelo como `UShort` en lugar de `UInteger` en el código administrado de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="9456a-124">If you are passing a 16-bit argument to such a component, declare it as `UShort` instead of `UInteger` in your managed Visual Basic code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9456a-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="9456a-125">See also</span></span>

- [<span data-ttu-id="9456a-126">Reflexión (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9456a-126">Reflection (Visual Basic)</span></span>](../../programming-guide/concepts/reflection.md)
- [<span data-ttu-id="9456a-127">Reflexión</span><span class="sxs-lookup"><span data-stu-id="9456a-127">Reflection</span></span>](../../../framework/reflection-and-codedom/reflection.md)
