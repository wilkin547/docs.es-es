---
title: El tipo de valor devuelto de la función '<procedurename>' no es compatible con CLS
ms.date: 07/20/2015
f1_keywords:
- bc40027
- vbc40027
helpviewer_keywords:
- BC40027
ms.assetid: 33c088c7-48e7-400c-920e-6d8967e1f3fc
ms.openlocfilehash: 9a877046a1b30e2e3773a41b8b44573e11ff1c96
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92159708"
---
# <a name="bc40027-return-type-of-function-procedurename-is-not-cls-compliant"></a><span data-ttu-id="3a315-102">BC40027: el tipo de valor devuelto de la función ' \<procedurename> ' no es conforme a CLS</span><span class="sxs-lookup"><span data-stu-id="3a315-102">BC40027: Return type of function '\<procedurename>' is not CLS-compliant</span></span>

<span data-ttu-id="3a315-103">Un `Function` procedimiento está marcado como `<CLSCompliant(True)>` pero devuelve un tipo que está marcado como `<CLSCompliant(False)>` , no está marcado o no cumple los requisitos porque es un tipo no conforme.</span><span class="sxs-lookup"><span data-stu-id="3a315-103">A `Function` procedure is marked as `<CLSCompliant(True)>` but returns a type that is marked as `<CLSCompliant(False)>`, is not marked, or does not qualify because it is a noncompliant type.</span></span>

 <span data-ttu-id="3a315-104">Para que un procedimiento sea conforme a la [Independencia del lenguaje y componentes independientes del lenguaje](../../../standard/language-independence-and-language-independent-components.md) (CLS), solo debe usar tipos conformes a CLS.</span><span class="sxs-lookup"><span data-stu-id="3a315-104">For a procedure to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), it must use only CLS-compliant types.</span></span> <span data-ttu-id="3a315-105">Esto se aplica a los tipos de los parámetros, el tipo de valor devuelto y los tipos de todas sus variables locales.</span><span class="sxs-lookup"><span data-stu-id="3a315-105">This applies to the types of the parameters, the return type, and the types of all its local variables.</span></span>

 <span data-ttu-id="3a315-106">Los siguientes tipos de datos de Visual Basic no son conformes a CLS:</span><span class="sxs-lookup"><span data-stu-id="3a315-106">The following Visual Basic data types are not CLS-compliant:</span></span>

- [<span data-ttu-id="3a315-107">Tipo de datos SByte</span><span class="sxs-lookup"><span data-stu-id="3a315-107">SByte Data Type</span></span>](../data-types/sbyte-data-type.md)

- [<span data-ttu-id="3a315-108">Tipo de datos UInteger</span><span class="sxs-lookup"><span data-stu-id="3a315-108">UInteger Data Type</span></span>](../data-types/uinteger-data-type.md)

- [<span data-ttu-id="3a315-109">Tipo de datos ULong</span><span class="sxs-lookup"><span data-stu-id="3a315-109">ULong Data Type</span></span>](../data-types/ulong-data-type.md)

- [<span data-ttu-id="3a315-110">Tipo de datos UShort</span><span class="sxs-lookup"><span data-stu-id="3a315-110">UShort Data Type</span></span>](../data-types/ushort-data-type.md)

 <span data-ttu-id="3a315-111">Al aplicar <xref:System.CLSCompliantAttribute> a un elemento de programación, establezca el parámetro `isCompliant` del atributo en `True` o `False` para indicar conformidad o disconformidad.</span><span class="sxs-lookup"><span data-stu-id="3a315-111">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="3a315-112">No hay ningún valor predeterminado para este parámetro, por lo que debe proporcionar uno.</span><span class="sxs-lookup"><span data-stu-id="3a315-112">There is no default for this parameter, and you must supply a value.</span></span>

 <span data-ttu-id="3a315-113">Si no se aplica <xref:System.CLSCompliantAttribute> a un elemento, se considera que no es conforme.</span><span class="sxs-lookup"><span data-stu-id="3a315-113">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>

 <span data-ttu-id="3a315-114">De forma predeterminada, este mensaje es una advertencia.</span><span class="sxs-lookup"><span data-stu-id="3a315-114">By default, this message is a warning.</span></span> <span data-ttu-id="3a315-115">Para obtener información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="3a315-115">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>

 <span data-ttu-id="3a315-116">**Identificador de error:** BC40027</span><span class="sxs-lookup"><span data-stu-id="3a315-116">**Error ID:** BC40027</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="3a315-117">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="3a315-117">To correct this error</span></span>

- <span data-ttu-id="3a315-118">Si el `Function` procedimiento debe devolver este tipo determinado, quite <xref:System.CLSCompliantAttribute> .</span><span class="sxs-lookup"><span data-stu-id="3a315-118">If the `Function` procedure must return this particular type, remove the <xref:System.CLSCompliantAttribute>.</span></span> <span data-ttu-id="3a315-119">El procedimiento no puede ser conforme a CLS.</span><span class="sxs-lookup"><span data-stu-id="3a315-119">The procedure cannot be CLS-compliant.</span></span>

- <span data-ttu-id="3a315-120">Si el `Function` procedimiento debe ser conforme a CLS, cambie el tipo de valor devuelto al tipo conforme a CLS más próximo.</span><span class="sxs-lookup"><span data-stu-id="3a315-120">If the `Function` procedure must be CLS-compliant, change the return type to the closest CLS-compliant type.</span></span> <span data-ttu-id="3a315-121">Por ejemplo, en lugar de `UInteger` , quizá pueda usar `Integer` si no necesita que el intervalo de valores esté por encima de 2.147.483.647.</span><span class="sxs-lookup"><span data-stu-id="3a315-121">For example, in place of `UInteger` you might be able to use `Integer` if you do not need the value range above 2,147,483,647.</span></span> <span data-ttu-id="3a315-122">Si necesita el intervalo extendido, puede reemplazar `UInteger` por `Long`.</span><span class="sxs-lookup"><span data-stu-id="3a315-122">If you do need the extended range, you can replace `UInteger` with `Long`.</span></span>

- <span data-ttu-id="3a315-123">Si interactúa con objetos de automatización o COM, tenga en cuenta que algunos tipos tienen distintos anchos de datos que en el .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3a315-123">If you are interfacing with Automation or COM objects, keep in mind that some types have different data widths than in the .NET Framework.</span></span> <span data-ttu-id="3a315-124">Por ejemplo, `int` suele ser de 16 bits en otros entornos.</span><span class="sxs-lookup"><span data-stu-id="3a315-124">For example, `int` is often 16 bits in other environments.</span></span> <span data-ttu-id="3a315-125">Si devuelve un entero de 16 bits a este componente, declárelo como `Short` en lugar de `Integer` en el código de Visual Basic administrado.</span><span class="sxs-lookup"><span data-stu-id="3a315-125">If you are returning a 16-bit integer to such a component, declare it as `Short` instead of `Integer` in your managed Visual Basic code.</span></span>
