---
title: El tipo de parámetro '<parametername>' no es compatible con CLS
ms.date: 07/20/2015
f1_keywords:
- vbc40028
- bc40028
helpviewer_keywords:
- BC40028
ms.assetid: dfa1f6f9-bb88-44ad-b85f-149144363d41
ms.openlocfilehash: 7043138f770264b73eeac79cd262104b88cd8516
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92161236"
---
# <a name="bc40028-type-of-parameter-parametername-is-not-cls-compliant"></a><span data-ttu-id="f3cc2-102">BC40028: el tipo de parámetro ' \<parametername> ' no es conforme a CLS</span><span class="sxs-lookup"><span data-stu-id="f3cc2-102">BC40028: Type of parameter '\<parametername>' is not CLS-compliant</span></span>

<span data-ttu-id="f3cc2-103">Un procedimiento está marcado como `<CLSCompliant(True)>` pero declara un parámetro con un tipo que está marcado como `<CLSCompliant(False)>` , no está marcado o no cumple los requisitos porque es un tipo no conforme.</span><span class="sxs-lookup"><span data-stu-id="f3cc2-103">A procedure is marked as `<CLSCompliant(True)>` but declares a parameter with a type that is marked as `<CLSCompliant(False)>`, is not marked, or does not qualify because it is a noncompliant type.</span></span>

 <span data-ttu-id="f3cc2-104">Para que un procedimiento sea conforme a la [Independencia del lenguaje y componentes independientes del lenguaje](../../../standard/language-independence-and-language-independent-components.md) (CLS), solo debe usar tipos conformes a CLS.</span><span class="sxs-lookup"><span data-stu-id="f3cc2-104">For a procedure to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), it must use only CLS-compliant types.</span></span> <span data-ttu-id="f3cc2-105">Esto se aplica a los tipos de los parámetros, el tipo de valor devuelto y los tipos de todas sus variables locales.</span><span class="sxs-lookup"><span data-stu-id="f3cc2-105">This applies to the types of the parameters, the return type, and the types of all its local variables.</span></span>

 <span data-ttu-id="f3cc2-106">Los siguientes tipos de datos de Visual Basic no son conformes a CLS:</span><span class="sxs-lookup"><span data-stu-id="f3cc2-106">The following Visual Basic data types are not CLS-compliant:</span></span>

- [<span data-ttu-id="f3cc2-107">Tipo de datos SByte</span><span class="sxs-lookup"><span data-stu-id="f3cc2-107">SByte Data Type</span></span>](../data-types/sbyte-data-type.md)

- [<span data-ttu-id="f3cc2-108">Tipo de datos UInteger</span><span class="sxs-lookup"><span data-stu-id="f3cc2-108">UInteger Data Type</span></span>](../data-types/uinteger-data-type.md)

- [<span data-ttu-id="f3cc2-109">Tipo de datos ULong</span><span class="sxs-lookup"><span data-stu-id="f3cc2-109">ULong Data Type</span></span>](../data-types/ulong-data-type.md)

- [<span data-ttu-id="f3cc2-110">Tipo de datos UShort</span><span class="sxs-lookup"><span data-stu-id="f3cc2-110">UShort Data Type</span></span>](../data-types/ushort-data-type.md)

 <span data-ttu-id="f3cc2-111">Al aplicar <xref:System.CLSCompliantAttribute> a un elemento de programación, establezca el parámetro `isCompliant` del atributo en `True` o `False` para indicar conformidad o disconformidad.</span><span class="sxs-lookup"><span data-stu-id="f3cc2-111">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="f3cc2-112">No hay ningún valor predeterminado para este parámetro, por lo que debe proporcionar uno.</span><span class="sxs-lookup"><span data-stu-id="f3cc2-112">There is no default for this parameter, and you must supply a value.</span></span>

 <span data-ttu-id="f3cc2-113">Si no se aplica <xref:System.CLSCompliantAttribute> a un elemento, se considera que no es conforme.</span><span class="sxs-lookup"><span data-stu-id="f3cc2-113">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>

 <span data-ttu-id="f3cc2-114">De forma predeterminada, este mensaje es una advertencia.</span><span class="sxs-lookup"><span data-stu-id="f3cc2-114">By default, this message is a warning.</span></span> <span data-ttu-id="f3cc2-115">Para obtener información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="f3cc2-115">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>

 <span data-ttu-id="f3cc2-116">**Identificador de error:** BC40028</span><span class="sxs-lookup"><span data-stu-id="f3cc2-116">**Error ID:** BC40028</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="f3cc2-117">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="f3cc2-117">To correct this error</span></span>

- <span data-ttu-id="f3cc2-118">Si el procedimiento debe tomar un parámetro de este tipo determinado, quite <xref:System.CLSCompliantAttribute> .</span><span class="sxs-lookup"><span data-stu-id="f3cc2-118">If the procedure must take a parameter of this particular type, remove the <xref:System.CLSCompliantAttribute>.</span></span> <span data-ttu-id="f3cc2-119">El procedimiento no puede ser conforme a CLS.</span><span class="sxs-lookup"><span data-stu-id="f3cc2-119">The procedure cannot be CLS-compliant.</span></span>

- <span data-ttu-id="f3cc2-120">Si el procedimiento debe ser conforme a CLS, cambie el tipo de este parámetro al tipo conforme a CLS más próximo.</span><span class="sxs-lookup"><span data-stu-id="f3cc2-120">If the procedure must be CLS-compliant, change the type of this parameter to the closest CLS-compliant type.</span></span> <span data-ttu-id="f3cc2-121">Por ejemplo, en lugar de `UInteger` , quizá pueda usar `Integer` si no necesita que el intervalo de valores esté por encima de 2.147.483.647.</span><span class="sxs-lookup"><span data-stu-id="f3cc2-121">For example, in place of `UInteger` you might be able to use `Integer` if you do not need the value range above 2,147,483,647.</span></span> <span data-ttu-id="f3cc2-122">Si necesita el intervalo extendido, puede reemplazar `UInteger` por `Long`.</span><span class="sxs-lookup"><span data-stu-id="f3cc2-122">If you do need the extended range, you can replace `UInteger` with `Long`.</span></span>

- <span data-ttu-id="f3cc2-123">Si interactúa con objetos de automatización o COM, tenga en cuenta que algunos tipos tienen distintos anchos de datos que en el .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f3cc2-123">If you are interfacing with Automation or COM objects, keep in mind that some types have different data widths than in the .NET Framework.</span></span> <span data-ttu-id="f3cc2-124">Por ejemplo, `int` suele ser de 16 bits en otros entornos.</span><span class="sxs-lookup"><span data-stu-id="f3cc2-124">For example, `int` is often 16 bits in other environments.</span></span> <span data-ttu-id="f3cc2-125">Si está aceptando un entero de 16 bits de este componente, declárelo como `Short` en lugar de `Integer` en el código de Visual Basic administrado.</span><span class="sxs-lookup"><span data-stu-id="f3cc2-125">If you are accepting a 16-bit integer from such a component, declare it as `Short` instead of `Integer` in your managed Visual Basic code.</span></span>
