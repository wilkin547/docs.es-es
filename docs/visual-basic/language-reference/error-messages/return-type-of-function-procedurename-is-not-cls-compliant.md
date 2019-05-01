---
title: El tipo de valor devuelto de la función '<procedurename>' no es compatible con CLS
ms.date: 07/20/2015
f1_keywords:
- bc40027
- vbc40027
helpviewer_keywords:
- BC40027
ms.assetid: 33c088c7-48e7-400c-920e-6d8967e1f3fc
ms.openlocfilehash: 5e746981d10ba8e662aebf86f67f08856ba37199
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62013751"
---
# <a name="return-type-of-function-procedurename-is-not-cls-compliant"></a><span data-ttu-id="03076-102">Tipo de función de valor devuelto '\<NombreDeProcedimiento >' no es conforme a CLS</span><span class="sxs-lookup"><span data-stu-id="03076-102">Return type of function '\<procedurename>' is not CLS-compliant</span></span>
<span data-ttu-id="03076-103">Un `Function` procedimiento está marcado como `<CLSCompliant(True)>` pero devuelve un tipo que está marcado como `<CLSCompliant(False)>`, no está marcado o no cumple los requisitos porque es un tipo no conforme.</span><span class="sxs-lookup"><span data-stu-id="03076-103">A `Function` procedure is marked as `<CLSCompliant(True)>` but returns a type that is marked as `<CLSCompliant(False)>`, is not marked, or does not qualify because it is a noncompliant type.</span></span>  
  
 <span data-ttu-id="03076-104">Para que un procedimiento sea conforme a la [Independencia del lenguaje y componentes independientes del lenguaje](../../../standard/language-independence-and-language-independent-components.md) (CLS), solo debe usar tipos conformes a CLS.</span><span class="sxs-lookup"><span data-stu-id="03076-104">For a procedure to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), it must use only CLS-compliant types.</span></span> <span data-ttu-id="03076-105">Esto se aplica a los tipos de los parámetros, el tipo de valor devuelto y los tipos de todas sus variables locales.</span><span class="sxs-lookup"><span data-stu-id="03076-105">This applies to the types of the parameters, the return type, and the types of all its local variables.</span></span>  
  
 <span data-ttu-id="03076-106">Los siguientes tipos de datos de Visual Basic no son conformes a CLS:</span><span class="sxs-lookup"><span data-stu-id="03076-106">The following Visual Basic data types are not CLS-compliant:</span></span>  
  
- [<span data-ttu-id="03076-107">SByte (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="03076-107">SByte Data Type</span></span>](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
- [<span data-ttu-id="03076-108">UInteger (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="03076-108">UInteger Data Type</span></span>](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
- [<span data-ttu-id="03076-109">ULong (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="03076-109">ULong Data Type</span></span>](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
- [<span data-ttu-id="03076-110">UShort (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="03076-110">UShort Data Type</span></span>](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 <span data-ttu-id="03076-111">Al aplicar <xref:System.CLSCompliantAttribute> a un elemento de programación, establezca el parámetro `isCompliant` del atributo en `True` o `False` para indicar conformidad o disconformidad.</span><span class="sxs-lookup"><span data-stu-id="03076-111">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="03076-112">No hay ningún valor predeterminado para este parámetro, por lo que debe proporcionar uno.</span><span class="sxs-lookup"><span data-stu-id="03076-112">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="03076-113">Si no se aplica <xref:System.CLSCompliantAttribute> a un elemento, se considera que no es conforme.</span><span class="sxs-lookup"><span data-stu-id="03076-113">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="03076-114">De forma predeterminada, este mensaje es una advertencia.</span><span class="sxs-lookup"><span data-stu-id="03076-114">By default, this message is a warning.</span></span> <span data-ttu-id="03076-115">Para obtener más información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="03076-115">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="03076-116">**Identificador de error:** BC40027</span><span class="sxs-lookup"><span data-stu-id="03076-116">**Error ID:** BC40027</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="03076-117">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="03076-117">To correct this error</span></span>  
  
- <span data-ttu-id="03076-118">Si el `Function` procedimiento debe devolver este tipo determinado, quite el <xref:System.CLSCompliantAttribute>.</span><span class="sxs-lookup"><span data-stu-id="03076-118">If the `Function` procedure must return this particular type, remove the <xref:System.CLSCompliantAttribute>.</span></span> <span data-ttu-id="03076-119">El procedimiento no puede ser conforme a CLS.</span><span class="sxs-lookup"><span data-stu-id="03076-119">The procedure cannot be CLS-compliant.</span></span>  
  
- <span data-ttu-id="03076-120">Si el `Function` procedimiento debe ser conforme a CLS, cambie el tipo de valor devuelto al tipo conforme a CLS más próximo.</span><span class="sxs-lookup"><span data-stu-id="03076-120">If the `Function` procedure must be CLS-compliant, change the return type to the closest CLS-compliant type.</span></span> <span data-ttu-id="03076-121">Por ejemplo, en lugar de `UInteger` , quizá pueda usar `Integer` si no necesita que el intervalo de valores esté por encima de 2.147.483.647.</span><span class="sxs-lookup"><span data-stu-id="03076-121">For example, in place of `UInteger` you might be able to use `Integer` if you do not need the value range above 2,147,483,647.</span></span> <span data-ttu-id="03076-122">Si necesita el intervalo extendido, puede reemplazar `UInteger` por `Long`.</span><span class="sxs-lookup"><span data-stu-id="03076-122">If you do need the extended range, you can replace `UInteger` with `Long`.</span></span>  
  
- <span data-ttu-id="03076-123">Si trabaja con objetos de automatización o COM, tenga en cuenta que algunos tipos tienen anchos de datos distintos que en [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="03076-123">If you are interfacing with Automation or COM objects, keep in mind that some types have different data widths than in the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="03076-124">Por ejemplo, `int` suele ser de 16 bits en otros entornos.</span><span class="sxs-lookup"><span data-stu-id="03076-124">For example, `int` is often 16 bits in other environments.</span></span> <span data-ttu-id="03076-125">Si va a devolver un entero de 16 bits a esos componentes, declárelo como `Short` en lugar de `Integer` en el código administrado de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="03076-125">If you are returning a 16-bit integer to such a component, declare it as `Short` instead of `Integer` in your managed Visual Basic code.</span></span>