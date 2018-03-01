---
title: "Tipo subyacente &lt;typename&gt; de enumeración no es compatible con CLS"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc40032
- bc40032
helpviewer_keywords:
- BC40032
ms.assetid: 32bf1949-fd73-456c-a323-bf1ffe1320ed
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e054f8d992154f66ab1d48a477a7e04900aa5b4d
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/21/2017
---
# <a name="underlying-type-lttypenamegt-of-enum-is-not-cls-compliant"></a><span data-ttu-id="3a20a-102">Tipo subyacente &lt;typename&gt; de enumeración no es compatible con CLS</span><span class="sxs-lookup"><span data-stu-id="3a20a-102">Underlying type &lt;typename&gt; of Enum is not CLS-compliant</span></span>
<span data-ttu-id="3a20a-103">El tipo de datos especificado para esta enumeración no es parte de la [independencia del lenguaje y componentes independientes del lenguaje](../../../standard/language-independence-and-language-independent-components.md) (CLS).</span><span class="sxs-lookup"><span data-stu-id="3a20a-103">The data type specified for this enumeration is not part of the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS).</span></span> <span data-ttu-id="3a20a-104">Esto no es un error dentro de un componente, porque la [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] y [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] admiten este tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="3a20a-104">This is not an error within your component, because the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] and [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] support this data type.</span></span> <span data-ttu-id="3a20a-105">Sin embargo, otro componente escrito en código estrictamente conforme a CLS podría no admitir este tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="3a20a-105">However, another component written in strictly CLS-compliant code might not support this data type.</span></span> <span data-ttu-id="3a20a-106">Posible que un componente de ese tipo no pueda interactuar correctamente con su componente.</span><span class="sxs-lookup"><span data-stu-id="3a20a-106">Such a component might not be able to interact successfully with your component.</span></span>  
  
 <span data-ttu-id="3a20a-107">Los siguientes tipos de datos [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] no son conformes con CLS:</span><span class="sxs-lookup"><span data-stu-id="3a20a-107">The following [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] data types are not CLS-compliant:</span></span>  
  
-   [<span data-ttu-id="3a20a-108">SByte (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="3a20a-108">SByte Data Type</span></span>](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [<span data-ttu-id="3a20a-109">UInteger (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="3a20a-109">UInteger Data Type</span></span>](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [<span data-ttu-id="3a20a-110">ULong (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="3a20a-110">ULong Data Type</span></span>](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [<span data-ttu-id="3a20a-111">UShort (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="3a20a-111">UShort Data Type</span></span>](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 <span data-ttu-id="3a20a-112">De forma predeterminada, este mensaje es una advertencia.</span><span class="sxs-lookup"><span data-stu-id="3a20a-112">By default, this message is a warning.</span></span> <span data-ttu-id="3a20a-113">Para obtener más información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [configurar advertencias en Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="3a20a-113">For more information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="3a20a-114">**Id. de error:** BC40032</span><span class="sxs-lookup"><span data-stu-id="3a20a-114">**Error ID:** BC40032</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="3a20a-115">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="3a20a-115">To correct this error</span></span>  
  
-   <span data-ttu-id="3a20a-116">Si el componente se comunica solo con otros [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] componentes o no interactúen con cualquier otro componente, no necesita cambiar nada.</span><span class="sxs-lookup"><span data-stu-id="3a20a-116">If your component interfaces only with other [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] components, or does not interface with any other components, you do not need to change anything.</span></span>  
  
-   <span data-ttu-id="3a20a-117">Si interactúa con un componente no escrito para el [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], es posible que pueda determinar, ya sea mediante reflexión o en documentación, si admite este tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="3a20a-117">If you are interfacing with a component not written for the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], you might be able to determine, either through reflection or from documentation, whether it supports this data type.</span></span> <span data-ttu-id="3a20a-118">Si es así, no es necesario cambiar nada.</span><span class="sxs-lookup"><span data-stu-id="3a20a-118">If it does, you do not need to change anything.</span></span>  
  
-   <span data-ttu-id="3a20a-119">Si interactúa con un componente que no admite este tipo de datos, debe reemplazar por el tipo conforme a CLS más próximo.</span><span class="sxs-lookup"><span data-stu-id="3a20a-119">If you are interfacing with a component that does not support this data type, you must replace it with the closest CLS-compliant type.</span></span> <span data-ttu-id="3a20a-120">Por ejemplo, en lugar de `UInteger` , quizá pueda usar `Integer` si no necesita que el intervalo de valores esté por encima de 2.147.483.647.</span><span class="sxs-lookup"><span data-stu-id="3a20a-120">For example, in place of `UInteger` you might be able to use `Integer` if you do not need the value range above 2,147,483,647.</span></span> <span data-ttu-id="3a20a-121">Si necesita el intervalo extendido, puede reemplazar `UInteger` por `Long`.</span><span class="sxs-lookup"><span data-stu-id="3a20a-121">If you do need the extended range, you can replace `UInteger` with `Long`.</span></span>  
  
-   <span data-ttu-id="3a20a-122">Si trabaja con objetos de automatización o COM, tenga en cuenta que algunos tipos tienen anchos de datos distintos que en [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3a20a-122">If you are interfacing with Automation or COM objects, keep in mind that some types have different data widths than in the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="3a20a-123">Por ejemplo, `uint` suele ser de 16 bits en otros entornos.</span><span class="sxs-lookup"><span data-stu-id="3a20a-123">For example, `uint` is often 16 bits in other environments.</span></span> <span data-ttu-id="3a20a-124">Al pasar un argumento de 16 bits a esos componentes, declárelo como `UShort` en lugar de `UInteger` en su administrado [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] código.</span><span class="sxs-lookup"><span data-stu-id="3a20a-124">If you are passing a 16-bit argument to such a component, declare it as `UShort` instead of `UInteger` in your managed [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a20a-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="3a20a-125">See Also</span></span>  
 [<span data-ttu-id="3a20a-126">Reflexión (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3a20a-126">Reflection (Visual Basic)</span></span>](../../programming-guide/concepts/reflection.md)  
 [<span data-ttu-id="3a20a-127">Reflexión</span><span class="sxs-lookup"><span data-stu-id="3a20a-127">Reflection</span></span>](../../../framework/reflection-and-codedom/reflection.md)  
 
