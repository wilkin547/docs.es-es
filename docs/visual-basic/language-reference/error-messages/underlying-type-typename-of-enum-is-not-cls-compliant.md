---
title: El tipo subyacente <typename> de Enum no es compatible con CLS
ms.date: 07/20/2015
f1_keywords:
- vbc40032
- bc40032
helpviewer_keywords:
- BC40032
ms.assetid: 32bf1949-fd73-456c-a323-bf1ffe1320ed
ms.openlocfilehash: 79faf0038b2b313bdc21e12c8ae76854bcd6957f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406578"
---
# <a name="underlying-type-typename-of-enum-is-not-cls-compliant"></a><span data-ttu-id="ede78-102">El tipo subyacente \<typename> de Enum no es compatible con CLS</span><span class="sxs-lookup"><span data-stu-id="ede78-102">Underlying type \<typename> of Enum is not CLS-compliant</span></span>
<span data-ttu-id="ede78-103">El tipo de datos especificado para esta enumeración no forma parte de la [independencia del lenguaje y de los componentes independientes del lenguaje](../../../standard/language-independence-and-language-independent-components.md) (CLS).</span><span class="sxs-lookup"><span data-stu-id="ede78-103">The data type specified for this enumeration is not part of the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS).</span></span> <span data-ttu-id="ede78-104">Esto no es un error en el componente, porque el .NET Framework y Visual Basic admiten este tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="ede78-104">This is not an error within your component, because the .NET Framework and Visual Basic support this data type.</span></span> <span data-ttu-id="ede78-105">Sin embargo, es posible que otro componente escrito en código estrictamente conforme a CLS no admita este tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="ede78-105">However, another component written in strictly CLS-compliant code might not support this data type.</span></span> <span data-ttu-id="ede78-106">Tal componente podría no ser capaz de interactuar correctamente con el componente.</span><span class="sxs-lookup"><span data-stu-id="ede78-106">Such a component might not be able to interact successfully with your component.</span></span>  
  
 <span data-ttu-id="ede78-107">Los siguientes tipos de datos de Visual Basic no son conformes a CLS:</span><span class="sxs-lookup"><span data-stu-id="ede78-107">The following Visual Basic data types are not CLS-compliant:</span></span>  
  
- [<span data-ttu-id="ede78-108">Tipo de datos SByte</span><span class="sxs-lookup"><span data-stu-id="ede78-108">SByte Data Type</span></span>](../data-types/sbyte-data-type.md)  
  
- [<span data-ttu-id="ede78-109">Tipo de datos UInteger</span><span class="sxs-lookup"><span data-stu-id="ede78-109">UInteger Data Type</span></span>](../data-types/uinteger-data-type.md)  
  
- [<span data-ttu-id="ede78-110">Tipo de datos ULong</span><span class="sxs-lookup"><span data-stu-id="ede78-110">ULong Data Type</span></span>](../data-types/ulong-data-type.md)  
  
- [<span data-ttu-id="ede78-111">Tipo de datos UShort</span><span class="sxs-lookup"><span data-stu-id="ede78-111">UShort Data Type</span></span>](../data-types/ushort-data-type.md)  
  
 <span data-ttu-id="ede78-112">De forma predeterminada, este mensaje es una advertencia.</span><span class="sxs-lookup"><span data-stu-id="ede78-112">By default, this message is a warning.</span></span> <span data-ttu-id="ede78-113">Para obtener más información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="ede78-113">For more information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="ede78-114">**Identificador de error:** BC40032</span><span class="sxs-lookup"><span data-stu-id="ede78-114">**Error ID:** BC40032</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ede78-115">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="ede78-115">To correct this error</span></span>  
  
- <span data-ttu-id="ede78-116">Si el componente interactúa únicamente con otros componentes de .NET Framework, o no interactúa con ningún otro componente, no es necesario cambiar nada.</span><span class="sxs-lookup"><span data-stu-id="ede78-116">If your component interfaces only with other .NET Framework components, or does not interface with any other components, you do not need to change anything.</span></span>  
  
- <span data-ttu-id="ede78-117">Si interactúa con un componente que no está escrito para el .NET Framework, es posible que pueda determinar, ya sea a través de la reflexión o desde la documentación, si admite este tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="ede78-117">If you are interfacing with a component not written for the .NET Framework, you might be able to determine, either through reflection or from documentation, whether it supports this data type.</span></span> <span data-ttu-id="ede78-118">En caso contrario, no es necesario cambiar nada.</span><span class="sxs-lookup"><span data-stu-id="ede78-118">If it does, you do not need to change anything.</span></span>  
  
- <span data-ttu-id="ede78-119">Si interactúa con un componente que no admite este tipo de datos, debe reemplazarlo por el tipo conforme a CLS más próximo.</span><span class="sxs-lookup"><span data-stu-id="ede78-119">If you are interfacing with a component that does not support this data type, you must replace it with the closest CLS-compliant type.</span></span> <span data-ttu-id="ede78-120">Por ejemplo, en lugar de `UInteger` , quizá pueda usar `Integer` si no necesita que el intervalo de valores esté por encima de 2.147.483.647.</span><span class="sxs-lookup"><span data-stu-id="ede78-120">For example, in place of `UInteger` you might be able to use `Integer` if you do not need the value range above 2,147,483,647.</span></span> <span data-ttu-id="ede78-121">Si necesita el intervalo extendido, puede reemplazar `UInteger` por `Long`.</span><span class="sxs-lookup"><span data-stu-id="ede78-121">If you do need the extended range, you can replace `UInteger` with `Long`.</span></span>  
  
- <span data-ttu-id="ede78-122">Si interactúa con objetos de automatización o COM, tenga en cuenta que algunos tipos tienen distintos anchos de datos que en el .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ede78-122">If you are interfacing with Automation or COM objects, keep in mind that some types have different data widths than in the .NET Framework.</span></span> <span data-ttu-id="ede78-123">Por ejemplo, `uint` suele ser de 16 bits en otros entornos.</span><span class="sxs-lookup"><span data-stu-id="ede78-123">For example, `uint` is often 16 bits in other environments.</span></span> <span data-ttu-id="ede78-124">Si va a pasar un argumento de 16 bits a este componente, declárelo como `UShort` en lugar de `UInteger` en el código de Visual Basic administrado.</span><span class="sxs-lookup"><span data-stu-id="ede78-124">If you are passing a 16-bit argument to such a component, declare it as `UShort` instead of `UInteger` in your managed Visual Basic code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ede78-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ede78-125">See also</span></span>

- <span data-ttu-id="ede78-126">[Reflection (Visual Basic)](../../programming-guide/concepts/reflection.md) (Reflexión [Visual Basic])</span><span class="sxs-lookup"><span data-stu-id="ede78-126">[Reflection (Visual Basic)](../../programming-guide/concepts/reflection.md)</span></span>
- [<span data-ttu-id="ede78-127">Reflexión</span><span class="sxs-lookup"><span data-stu-id="ede78-127">Reflection</span></span>](../../../framework/reflection-and-codedom/reflection.md)
