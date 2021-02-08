---
description: 'Más información sobre: BC40042: el tipo de valor opcional para el parámetro opcional <parametername> no es conforme a CLS'
title: El tipo de valor opcional para el parámetro opcional <parametername> no es compatible con CLS
ms.date: 07/20/2015
f1_keywords:
- BC40042
- vbc40042
helpviewer_keywords:
- BC40042
ms.assetid: 1d6eae29-4ad3-4434-bde4-a53b6051adf5
ms.openlocfilehash: 44dee07120ebcd99be69257aef6a334f9067cdb3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99774868"
---
# <a name="bc40042-type-of-optional-value-for-optional-parameter-parametername-is-not-cls-compliant"></a><span data-ttu-id="6647e-103">BC40042: el tipo de valor opcional para el parámetro opcional \<parametername> no es conforme a CLS</span><span class="sxs-lookup"><span data-stu-id="6647e-103">BC40042: Type of optional value for optional parameter \<parametername> is not CLS-compliant</span></span>

<span data-ttu-id="6647e-104">Un procedimiento se marca como `<CLSCompliant(True)>`, pero declara un parámetro [opcional](../modifiers/optional.md) con valor predeterminado de un tipo no conforme.</span><span class="sxs-lookup"><span data-stu-id="6647e-104">A procedure is marked as `<CLSCompliant(True)>` but declares an [Optional](../modifiers/optional.md) parameter with default value of a noncompliant type.</span></span>

 <span data-ttu-id="6647e-105">Para que un procedimiento sea conforme a la [Independencia del lenguaje y componentes independientes del lenguaje](../../../standard/language-independence-and-language-independent-components.md) (CLS), solo debe usar tipos conformes a CLS.</span><span class="sxs-lookup"><span data-stu-id="6647e-105">For a procedure to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), it must use only CLS-compliant types.</span></span> <span data-ttu-id="6647e-106">Esto se aplica a los tipos de los parámetros, el tipo de valor devuelto y los tipos de todas sus variables locales.</span><span class="sxs-lookup"><span data-stu-id="6647e-106">This applies to the types of the parameters, the return type, and the types of all its local variables.</span></span> <span data-ttu-id="6647e-107">También se aplica a los valores predeterminados de parámetros opcionales.</span><span class="sxs-lookup"><span data-stu-id="6647e-107">It also applies to the default values of optional parameters.</span></span>

 <span data-ttu-id="6647e-108">Los siguientes tipos de datos de Visual Basic no son conformes a CLS:</span><span class="sxs-lookup"><span data-stu-id="6647e-108">The following Visual Basic data types are not CLS-compliant:</span></span>

- [<span data-ttu-id="6647e-109">Tipo de datos SByte</span><span class="sxs-lookup"><span data-stu-id="6647e-109">SByte Data Type</span></span>](../data-types/sbyte-data-type.md)

- [<span data-ttu-id="6647e-110">Tipo de datos UInteger</span><span class="sxs-lookup"><span data-stu-id="6647e-110">UInteger Data Type</span></span>](../data-types/uinteger-data-type.md)

- [<span data-ttu-id="6647e-111">Tipo de datos ULong</span><span class="sxs-lookup"><span data-stu-id="6647e-111">ULong Data Type</span></span>](../data-types/ulong-data-type.md)

- [<span data-ttu-id="6647e-112">Tipo de datos UShort</span><span class="sxs-lookup"><span data-stu-id="6647e-112">UShort Data Type</span></span>](../data-types/ushort-data-type.md)

 <span data-ttu-id="6647e-113">Al aplicar el atributo <xref:System.CLSCompliantAttribute> a un elemento de programación, establezca el parámetro `isCompliant` del atributo como `True` o `False` para indicar compatibilidad o incompatibilidad.</span><span class="sxs-lookup"><span data-stu-id="6647e-113">When you apply the <xref:System.CLSCompliantAttribute> attribute to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="6647e-114">No hay ningún valor predeterminado para este parámetro, por lo que debe proporcionar uno.</span><span class="sxs-lookup"><span data-stu-id="6647e-114">There is no default for this parameter, and you must supply a value.</span></span>

 <span data-ttu-id="6647e-115">Si no aplica <xref:System.CLSCompliantAttribute> a un elemento, se considera que no es conforme.</span><span class="sxs-lookup"><span data-stu-id="6647e-115">If you do not apply <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>

 <span data-ttu-id="6647e-116">De forma predeterminada, este mensaje es una advertencia.</span><span class="sxs-lookup"><span data-stu-id="6647e-116">By default, this message is a warning.</span></span> <span data-ttu-id="6647e-117">Para obtener información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="6647e-117">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>

 <span data-ttu-id="6647e-118">**Id. de error:** BC40042</span><span class="sxs-lookup"><span data-stu-id="6647e-118">**Error ID:** BC40042</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="6647e-119">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="6647e-119">To correct this error</span></span>

- <span data-ttu-id="6647e-120">Si el parámetro opcional debe tener un valor predeterminado de este tipo determinado, quite <xref:System.CLSCompliantAttribute> .</span><span class="sxs-lookup"><span data-stu-id="6647e-120">If the optional parameter must have a default value of this particular type, remove <xref:System.CLSCompliantAttribute>.</span></span> <span data-ttu-id="6647e-121">El procedimiento no puede ser conforme a CLS.</span><span class="sxs-lookup"><span data-stu-id="6647e-121">The procedure cannot be CLS-compliant.</span></span>

- <span data-ttu-id="6647e-122">Si el procedimiento debe ser conforme a CLS, cambie el tipo de este valor predeterminado al tipo conforme a CLS más próximo.</span><span class="sxs-lookup"><span data-stu-id="6647e-122">If the procedure must be CLS-compliant, change the type of this default value to the closest CLS-compliant type.</span></span> <span data-ttu-id="6647e-123">Por ejemplo, en lugar de `UInteger` , quizá pueda usar `Integer` si no necesita que el intervalo de valores esté por encima de 2.147.483.647.</span><span class="sxs-lookup"><span data-stu-id="6647e-123">For example, in place of `UInteger` you might be able to use `Integer` if you do not need the value range above 2,147,483,647.</span></span> <span data-ttu-id="6647e-124">Si necesita el intervalo extendido, puede reemplazar `UInteger` por `Long`.</span><span class="sxs-lookup"><span data-stu-id="6647e-124">If you do need the extended range, you can replace `UInteger` with `Long`.</span></span>

- <span data-ttu-id="6647e-125">Si interactúa con objetos de automatización o COM, tenga en cuenta que algunos tipos tienen distintos anchos de datos que en el .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6647e-125">If you are interfacing with Automation or COM objects, keep in mind that some types have different data widths than in the .NET Framework.</span></span> <span data-ttu-id="6647e-126">Por ejemplo, `int` suele ser de 16 bits en otros entornos.</span><span class="sxs-lookup"><span data-stu-id="6647e-126">For example, `int` is often 16 bits in other environments.</span></span> <span data-ttu-id="6647e-127">Si está aceptando un entero de 16 bits de este componente, declárelo como `Short` en lugar de `Integer` en el código de Visual Basic administrado.</span><span class="sxs-lookup"><span data-stu-id="6647e-127">If you are accepting a 16-bit integer from such a component, declare it as `Short` instead of `Integer` in your managed Visual Basic code.</span></span>
