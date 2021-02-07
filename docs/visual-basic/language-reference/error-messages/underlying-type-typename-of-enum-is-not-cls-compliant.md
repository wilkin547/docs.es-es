---
description: 'Más información sobre: BC40032: el tipo subyacente <typename> de la enumeración no es conforme a CLS'
title: El tipo subyacente <typename> de Enum no es compatible con CLS
ms.date: 07/20/2015
f1_keywords:
- vbc40032
- bc40032
helpviewer_keywords:
- BC40032
ms.assetid: 32bf1949-fd73-456c-a323-bf1ffe1320ed
ms.openlocfilehash: aebee5a9e0cd7f2e780d0171ad59dcfd4fd1d940
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99674797"
---
# <a name="bc40032-underlying-type-typename-of-enum-is-not-cls-compliant"></a><span data-ttu-id="42fa5-103">BC40032: el tipo subyacente \<typename> de la enumeración no es conforme a CLS</span><span class="sxs-lookup"><span data-stu-id="42fa5-103">BC40032: Underlying type \<typename> of Enum is not CLS-compliant</span></span>

<span data-ttu-id="42fa5-104">El tipo de datos especificado para esta enumeración no forma parte de la [independencia del lenguaje y](../../../standard/language-independence-and-language-independent-components.md) de los componentes de Language-Independent (CLS).</span><span class="sxs-lookup"><span data-stu-id="42fa5-104">The data type specified for this enumeration is not part of the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS).</span></span> <span data-ttu-id="42fa5-105">Esto no es un error en el componente, porque el .NET Framework y Visual Basic admiten este tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="42fa5-105">This is not an error within your component, because the .NET Framework and Visual Basic support this data type.</span></span> <span data-ttu-id="42fa5-106">Sin embargo, es posible que otro componente escrito en código estrictamente conforme a CLS no admita este tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="42fa5-106">However, another component written in strictly CLS-compliant code might not support this data type.</span></span> <span data-ttu-id="42fa5-107">Tal componente podría no ser capaz de interactuar correctamente con el componente.</span><span class="sxs-lookup"><span data-stu-id="42fa5-107">Such a component might not be able to interact successfully with your component.</span></span>

 <span data-ttu-id="42fa5-108">Los siguientes tipos de datos de Visual Basic no son conformes a CLS:</span><span class="sxs-lookup"><span data-stu-id="42fa5-108">The following Visual Basic data types are not CLS-compliant:</span></span>

- [<span data-ttu-id="42fa5-109">Tipo de datos SByte</span><span class="sxs-lookup"><span data-stu-id="42fa5-109">SByte Data Type</span></span>](../data-types/sbyte-data-type.md)

- [<span data-ttu-id="42fa5-110">Tipo de datos UInteger</span><span class="sxs-lookup"><span data-stu-id="42fa5-110">UInteger Data Type</span></span>](../data-types/uinteger-data-type.md)

- [<span data-ttu-id="42fa5-111">Tipo de datos ULong</span><span class="sxs-lookup"><span data-stu-id="42fa5-111">ULong Data Type</span></span>](../data-types/ulong-data-type.md)

- [<span data-ttu-id="42fa5-112">Tipo de datos UShort</span><span class="sxs-lookup"><span data-stu-id="42fa5-112">UShort Data Type</span></span>](../data-types/ushort-data-type.md)

 <span data-ttu-id="42fa5-113">De forma predeterminada, este mensaje es una advertencia.</span><span class="sxs-lookup"><span data-stu-id="42fa5-113">By default, this message is a warning.</span></span> <span data-ttu-id="42fa5-114">Para obtener más información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="42fa5-114">For more information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>

 <span data-ttu-id="42fa5-115">**Identificador de error:** BC40032</span><span class="sxs-lookup"><span data-stu-id="42fa5-115">**Error ID:** BC40032</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="42fa5-116">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="42fa5-116">To correct this error</span></span>

- <span data-ttu-id="42fa5-117">Si el componente interactúa únicamente con otros componentes de .NET Framework, o no interactúa con ningún otro componente, no es necesario cambiar nada.</span><span class="sxs-lookup"><span data-stu-id="42fa5-117">If your component interfaces only with other .NET Framework components, or does not interface with any other components, you do not need to change anything.</span></span>

- <span data-ttu-id="42fa5-118">Si interactúa con un componente que no está escrito para el .NET Framework, es posible que pueda determinar, ya sea a través de la reflexión o desde la documentación, si admite este tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="42fa5-118">If you are interfacing with a component not written for the .NET Framework, you might be able to determine, either through reflection or from documentation, whether it supports this data type.</span></span> <span data-ttu-id="42fa5-119">En caso contrario, no es necesario cambiar nada.</span><span class="sxs-lookup"><span data-stu-id="42fa5-119">If it does, you do not need to change anything.</span></span>

- <span data-ttu-id="42fa5-120">Si interactúa con un componente que no admite este tipo de datos, debe reemplazarlo por el tipo conforme a CLS más próximo.</span><span class="sxs-lookup"><span data-stu-id="42fa5-120">If you are interfacing with a component that does not support this data type, you must replace it with the closest CLS-compliant type.</span></span> <span data-ttu-id="42fa5-121">Por ejemplo, en lugar de `UInteger` , quizá pueda usar `Integer` si no necesita que el intervalo de valores esté por encima de 2.147.483.647.</span><span class="sxs-lookup"><span data-stu-id="42fa5-121">For example, in place of `UInteger` you might be able to use `Integer` if you do not need the value range above 2,147,483,647.</span></span> <span data-ttu-id="42fa5-122">Si necesita el intervalo extendido, puede reemplazar `UInteger` por `Long`.</span><span class="sxs-lookup"><span data-stu-id="42fa5-122">If you do need the extended range, you can replace `UInteger` with `Long`.</span></span>

- <span data-ttu-id="42fa5-123">Si interactúa con objetos de automatización o COM, tenga en cuenta que algunos tipos tienen distintos anchos de datos que en el .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="42fa5-123">If you are interfacing with Automation or COM objects, keep in mind that some types have different data widths than in the .NET Framework.</span></span> <span data-ttu-id="42fa5-124">Por ejemplo, `uint` suele ser de 16 bits en otros entornos.</span><span class="sxs-lookup"><span data-stu-id="42fa5-124">For example, `uint` is often 16 bits in other environments.</span></span> <span data-ttu-id="42fa5-125">Si va a pasar un argumento de 16 bits a este componente, declárelo como `UShort` en lugar de `UInteger` en el código de Visual Basic administrado.</span><span class="sxs-lookup"><span data-stu-id="42fa5-125">If you are passing a 16-bit argument to such a component, declare it as `UShort` instead of `UInteger` in your managed Visual Basic code.</span></span>

## <a name="see-also"></a><span data-ttu-id="42fa5-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="42fa5-126">See also</span></span>

- <span data-ttu-id="42fa5-127">[Reflection (Visual Basic)](../../programming-guide/concepts/reflection.md) (Reflexión [Visual Basic])</span><span class="sxs-lookup"><span data-stu-id="42fa5-127">[Reflection (Visual Basic)](../../programming-guide/concepts/reflection.md)</span></span>
- [<span data-ttu-id="42fa5-128">Reflexión</span><span class="sxs-lookup"><span data-stu-id="42fa5-128">Reflection</span></span>](../../../framework/reflection-and-codedom/reflection.md)
