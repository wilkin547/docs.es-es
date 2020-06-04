---
title: El tipo de miembro '<membername>' no es compatible con CLS
ms.date: 07/20/2015
f1_keywords:
- bc40025
- vbc40025
helpviewer_keywords:
- BC40025
ms.assetid: adbd34bb-43d2-4266-90e7-cd1afaf49b4e
ms.openlocfilehash: 030cb31b8f1ba0e8eaa82eeb8e37153411a53404
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400310"
---
# <a name="type-of-member-membername-is-not-cls-compliant"></a><span data-ttu-id="29d19-102">El tipo de miembro '\<membername>' no es compatible con CLS</span><span class="sxs-lookup"><span data-stu-id="29d19-102">Type of member '\<membername>' is not CLS-compliant</span></span>
<span data-ttu-id="29d19-103">El tipo de datos especificado para este miembro no forma parte de la [independencia del lenguaje y de los componentes independientes del lenguaje](../../../standard/language-independence-and-language-independent-components.md) (CLS).</span><span class="sxs-lookup"><span data-stu-id="29d19-103">The data type specified for this member is not part of the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS).</span></span> <span data-ttu-id="29d19-104">Esto no es un error en el componente, porque el .NET Framework y Visual Basic admiten este tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="29d19-104">This is not an error within your component, because the .NET Framework and Visual Basic support this data type.</span></span> <span data-ttu-id="29d19-105">Sin embargo, es posible que otro componente escrito en código estrictamente conforme a CLS no admita este tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="29d19-105">However, another component written in strictly CLS-compliant code might not support this data type.</span></span> <span data-ttu-id="29d19-106">Tal componente podría no ser capaz de interactuar correctamente con el componente.</span><span class="sxs-lookup"><span data-stu-id="29d19-106">Such a component might not be able to interact successfully with your component.</span></span>  
  
 <span data-ttu-id="29d19-107">Los siguientes tipos de datos de Visual Basic no son conformes a CLS:</span><span class="sxs-lookup"><span data-stu-id="29d19-107">The following Visual Basic data types are not CLS-compliant:</span></span>  
  
- [<span data-ttu-id="29d19-108">Tipo de datos SByte</span><span class="sxs-lookup"><span data-stu-id="29d19-108">SByte Data Type</span></span>](../data-types/sbyte-data-type.md)  
  
- [<span data-ttu-id="29d19-109">Tipo de datos UInteger</span><span class="sxs-lookup"><span data-stu-id="29d19-109">UInteger Data Type</span></span>](../data-types/uinteger-data-type.md)  
  
- [<span data-ttu-id="29d19-110">Tipo de datos ULong</span><span class="sxs-lookup"><span data-stu-id="29d19-110">ULong Data Type</span></span>](../data-types/ulong-data-type.md)  
  
- [<span data-ttu-id="29d19-111">Tipo de datos UShort</span><span class="sxs-lookup"><span data-stu-id="29d19-111">UShort Data Type</span></span>](../data-types/ushort-data-type.md)  
  
 <span data-ttu-id="29d19-112">De forma predeterminada, este mensaje es una advertencia.</span><span class="sxs-lookup"><span data-stu-id="29d19-112">By default, this message is a warning.</span></span> <span data-ttu-id="29d19-113">Para obtener más información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="29d19-113">For more information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="29d19-114">**Identificador de error:** BC40025</span><span class="sxs-lookup"><span data-stu-id="29d19-114">**Error ID:** BC40025</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="29d19-115">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="29d19-115">To correct this error</span></span>  
  
- <span data-ttu-id="29d19-116">Si el componente interactúa únicamente con otros componentes de .NET Framework, o no interactúa con ningún otro componente, no es necesario cambiar nada.</span><span class="sxs-lookup"><span data-stu-id="29d19-116">If your component interfaces only with other .NET Framework components, or does not interface with any other components, you do not need to change anything.</span></span>  
  
- <span data-ttu-id="29d19-117">Si interactúa con un componente que no está escrito para el .NET Framework, es posible que pueda determinar, ya sea a través de la reflexión o desde la documentación, si admite este tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="29d19-117">If you are interfacing with a component not written for the .NET Framework, you might be able to determine, either through reflection or from documentation, whether it supports this data type.</span></span> <span data-ttu-id="29d19-118">En caso contrario, no es necesario cambiar nada.</span><span class="sxs-lookup"><span data-stu-id="29d19-118">If it does, you do not need to change anything.</span></span>  
  
- <span data-ttu-id="29d19-119">Si interactúa con un componente que no admite este tipo de datos, debe reemplazarlo por el tipo conforme a CLS más próximo.</span><span class="sxs-lookup"><span data-stu-id="29d19-119">If you are interfacing with a component that does not support this data type, you must replace it with the closest CLS-compliant type.</span></span> <span data-ttu-id="29d19-120">Por ejemplo, en lugar de `UInteger` , quizá pueda usar `Integer` si no necesita que el intervalo de valores esté por encima de 2.147.483.647.</span><span class="sxs-lookup"><span data-stu-id="29d19-120">For example, in place of `UInteger` you might be able to use `Integer` if you do not need the value range above 2,147,483,647.</span></span> <span data-ttu-id="29d19-121">Si necesita el intervalo extendido, puede reemplazar `UInteger` por `Long`.</span><span class="sxs-lookup"><span data-stu-id="29d19-121">If you do need the extended range, you can replace `UInteger` with `Long`.</span></span>  
  
- <span data-ttu-id="29d19-122">Si interactúa con objetos de automatización o COM, tenga en cuenta que algunos tipos tienen distintos anchos de datos que en el .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="29d19-122">If you are interfacing with Automation or COM objects, keep in mind that some types have different data widths than in the .NET Framework.</span></span> <span data-ttu-id="29d19-123">Por ejemplo, `uint` suele ser de 16 bits en otros entornos.</span><span class="sxs-lookup"><span data-stu-id="29d19-123">For example, `uint` is often 16 bits in other environments.</span></span> <span data-ttu-id="29d19-124">Si va a pasar un argumento de 16 bits a este componente, declárelo como `UShort` en lugar de `UInteger` en el código de Visual Basic administrado.</span><span class="sxs-lookup"><span data-stu-id="29d19-124">If you are passing a 16-bit argument to such a component, declare it as `UShort` instead of `UInteger` in your managed Visual Basic code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29d19-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="29d19-125">See also</span></span>

- [<span data-ttu-id="29d19-126">Reflexión</span><span class="sxs-lookup"><span data-stu-id="29d19-126">Reflection</span></span>](../../../framework/reflection-and-codedom/reflection.md)
