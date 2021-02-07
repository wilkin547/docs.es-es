---
description: "Más información sobre: BC40028: el tipo de parámetro ' <parametername> ' no es conforme a CLS"
title: El tipo de parámetro '<parametername>' no es compatible con CLS
ms.date: 07/20/2015
f1_keywords:
- vbc40028
- bc40028
helpviewer_keywords:
- BC40028
ms.assetid: dfa1f6f9-bb88-44ad-b85f-149144363d41
ms.openlocfilehash: 5e430e55e24001d779243645cf4b409d1801d6f2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99731128"
---
# <a name="bc40028-type-of-parameter-parametername-is-not-cls-compliant"></a><span data-ttu-id="920a7-103">BC40028: el tipo de parámetro ' \<parametername> ' no es conforme a CLS</span><span class="sxs-lookup"><span data-stu-id="920a7-103">BC40028: Type of parameter '\<parametername>' is not CLS-compliant</span></span>

<span data-ttu-id="920a7-104">Un procedimiento está marcado como `<CLSCompliant(True)>` pero declara un parámetro con un tipo que está marcado como `<CLSCompliant(False)>` , no está marcado o no cumple los requisitos porque es un tipo no conforme.</span><span class="sxs-lookup"><span data-stu-id="920a7-104">A procedure is marked as `<CLSCompliant(True)>` but declares a parameter with a type that is marked as `<CLSCompliant(False)>`, is not marked, or does not qualify because it is a noncompliant type.</span></span>

 <span data-ttu-id="920a7-105">Para que un procedimiento sea conforme a la [Independencia del lenguaje y componentes independientes del lenguaje](../../../standard/language-independence-and-language-independent-components.md) (CLS), solo debe usar tipos conformes a CLS.</span><span class="sxs-lookup"><span data-stu-id="920a7-105">For a procedure to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), it must use only CLS-compliant types.</span></span> <span data-ttu-id="920a7-106">Esto se aplica a los tipos de los parámetros, el tipo de valor devuelto y los tipos de todas sus variables locales.</span><span class="sxs-lookup"><span data-stu-id="920a7-106">This applies to the types of the parameters, the return type, and the types of all its local variables.</span></span>

 <span data-ttu-id="920a7-107">Los siguientes tipos de datos de Visual Basic no son conformes a CLS:</span><span class="sxs-lookup"><span data-stu-id="920a7-107">The following Visual Basic data types are not CLS-compliant:</span></span>

- [<span data-ttu-id="920a7-108">Tipo de datos SByte</span><span class="sxs-lookup"><span data-stu-id="920a7-108">SByte Data Type</span></span>](../data-types/sbyte-data-type.md)

- [<span data-ttu-id="920a7-109">Tipo de datos UInteger</span><span class="sxs-lookup"><span data-stu-id="920a7-109">UInteger Data Type</span></span>](../data-types/uinteger-data-type.md)

- [<span data-ttu-id="920a7-110">Tipo de datos ULong</span><span class="sxs-lookup"><span data-stu-id="920a7-110">ULong Data Type</span></span>](../data-types/ulong-data-type.md)

- [<span data-ttu-id="920a7-111">Tipo de datos UShort</span><span class="sxs-lookup"><span data-stu-id="920a7-111">UShort Data Type</span></span>](../data-types/ushort-data-type.md)

 <span data-ttu-id="920a7-112">Al aplicar <xref:System.CLSCompliantAttribute> a un elemento de programación, establezca el parámetro `isCompliant` del atributo en `True` o `False` para indicar conformidad o disconformidad.</span><span class="sxs-lookup"><span data-stu-id="920a7-112">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="920a7-113">No hay ningún valor predeterminado para este parámetro, por lo que debe proporcionar uno.</span><span class="sxs-lookup"><span data-stu-id="920a7-113">There is no default for this parameter, and you must supply a value.</span></span>

 <span data-ttu-id="920a7-114">Si no se aplica <xref:System.CLSCompliantAttribute> a un elemento, se considera que no es conforme.</span><span class="sxs-lookup"><span data-stu-id="920a7-114">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>

 <span data-ttu-id="920a7-115">De forma predeterminada, este mensaje es una advertencia.</span><span class="sxs-lookup"><span data-stu-id="920a7-115">By default, this message is a warning.</span></span> <span data-ttu-id="920a7-116">Para obtener información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="920a7-116">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>

 <span data-ttu-id="920a7-117">**Identificador de error:** BC40028</span><span class="sxs-lookup"><span data-stu-id="920a7-117">**Error ID:** BC40028</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="920a7-118">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="920a7-118">To correct this error</span></span>

- <span data-ttu-id="920a7-119">Si el procedimiento debe tomar un parámetro de este tipo determinado, quite <xref:System.CLSCompliantAttribute> .</span><span class="sxs-lookup"><span data-stu-id="920a7-119">If the procedure must take a parameter of this particular type, remove the <xref:System.CLSCompliantAttribute>.</span></span> <span data-ttu-id="920a7-120">El procedimiento no puede ser conforme a CLS.</span><span class="sxs-lookup"><span data-stu-id="920a7-120">The procedure cannot be CLS-compliant.</span></span>

- <span data-ttu-id="920a7-121">Si el procedimiento debe ser conforme a CLS, cambie el tipo de este parámetro al tipo conforme a CLS más próximo.</span><span class="sxs-lookup"><span data-stu-id="920a7-121">If the procedure must be CLS-compliant, change the type of this parameter to the closest CLS-compliant type.</span></span> <span data-ttu-id="920a7-122">Por ejemplo, en lugar de `UInteger` , quizá pueda usar `Integer` si no necesita que el intervalo de valores esté por encima de 2.147.483.647.</span><span class="sxs-lookup"><span data-stu-id="920a7-122">For example, in place of `UInteger` you might be able to use `Integer` if you do not need the value range above 2,147,483,647.</span></span> <span data-ttu-id="920a7-123">Si necesita el intervalo extendido, puede reemplazar `UInteger` por `Long`.</span><span class="sxs-lookup"><span data-stu-id="920a7-123">If you do need the extended range, you can replace `UInteger` with `Long`.</span></span>

- <span data-ttu-id="920a7-124">Si interactúa con objetos de automatización o COM, tenga en cuenta que algunos tipos tienen distintos anchos de datos que en el .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="920a7-124">If you are interfacing with Automation or COM objects, keep in mind that some types have different data widths than in the .NET Framework.</span></span> <span data-ttu-id="920a7-125">Por ejemplo, `int` suele ser de 16 bits en otros entornos.</span><span class="sxs-lookup"><span data-stu-id="920a7-125">For example, `int` is often 16 bits in other environments.</span></span> <span data-ttu-id="920a7-126">Si está aceptando un entero de 16 bits de este componente, declárelo como `Short` en lugar de `Integer` en el código de Visual Basic administrado.</span><span class="sxs-lookup"><span data-stu-id="920a7-126">If you are accepting a 16-bit integer from such a component, declare it as `Short` instead of `Integer` in your managed Visual Basic code.</span></span>
