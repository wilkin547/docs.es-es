---
title: "Tipo de parámetro &#39; &lt;parametername&gt;&#39; no es conforme a CLS"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc40028
- bc40028
helpviewer_keywords: BC40028
ms.assetid: dfa1f6f9-bb88-44ad-b85f-149144363d41
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5fc981f5de5c4baa9a47e04af16966ea06fa10ad
ms.sourcegitcommit: 685143b62385500f59bc36274b8adb191f573a16
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/09/2017
---
# <a name="type-of-parameter-39ltparameternamegt39-is-not-cls-compliant"></a><span data-ttu-id="e9f00-102">Tipo de parámetro &#39; &lt;parametername&gt;&#39; no es conforme a CLS</span><span class="sxs-lookup"><span data-stu-id="e9f00-102">Type of parameter &#39;&lt;parametername&gt;&#39; is not CLS-compliant</span></span>
<span data-ttu-id="e9f00-103">Un procedimiento está marcado como `<CLSCompliant(True)>` pero declara un parámetro con un tipo que está marcado como `<CLSCompliant(False)>`, no está marcado o no cumple los requisitos porque es un tipo no compatible.</span><span class="sxs-lookup"><span data-stu-id="e9f00-103">A procedure is marked as `<CLSCompliant(True)>` but declares a parameter with a type that is marked as `<CLSCompliant(False)>`, is not marked, or does not qualify because it is a noncompliant type.</span></span>  
  
 <span data-ttu-id="e9f00-104">Para que un procedimiento sea conforme a la [Independencia del lenguaje y componentes independientes del lenguaje](../../../../docs/standard/language-independence-and-language-independent-components.md) (CLS), solo debe usar tipos conformes a CLS.</span><span class="sxs-lookup"><span data-stu-id="e9f00-104">For a procedure to be compliant with the [Language Independence and Language-Independent Components](../../../../docs/standard/language-independence-and-language-independent-components.md) (CLS), it must use only CLS-compliant types.</span></span> <span data-ttu-id="e9f00-105">Esto se aplica a los tipos de los parámetros, el tipo de valor devuelto y los tipos de todas sus variables locales.</span><span class="sxs-lookup"><span data-stu-id="e9f00-105">This applies to the types of the parameters, the return type, and the types of all its local variables.</span></span>  
  
 <span data-ttu-id="e9f00-106">Los siguientes tipos de datos [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] no son conformes con CLS:</span><span class="sxs-lookup"><span data-stu-id="e9f00-106">The following [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] data types are not CLS-compliant:</span></span>  
  
-   [<span data-ttu-id="e9f00-107">SByte (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="e9f00-107">SByte Data Type</span></span>](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [<span data-ttu-id="e9f00-108">UInteger (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="e9f00-108">UInteger Data Type</span></span>](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [<span data-ttu-id="e9f00-109">ULong (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="e9f00-109">ULong Data Type</span></span>](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [<span data-ttu-id="e9f00-110">UShort (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="e9f00-110">UShort Data Type</span></span>](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 <span data-ttu-id="e9f00-111">Al aplicar <xref:System.CLSCompliantAttribute> a un elemento de programación, establezca el parámetro `isCompliant` del atributo en `True` o `False` para indicar conformidad o disconformidad.</span><span class="sxs-lookup"><span data-stu-id="e9f00-111">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="e9f00-112">No hay ningún valor predeterminado para este parámetro y debe proporcionar un valor.</span><span class="sxs-lookup"><span data-stu-id="e9f00-112">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="e9f00-113">Si no se aplica <xref:System.CLSCompliantAttribute> a un elemento, se considera que no es conforme.</span><span class="sxs-lookup"><span data-stu-id="e9f00-113">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="e9f00-114">De forma predeterminada, este mensaje es una advertencia.</span><span class="sxs-lookup"><span data-stu-id="e9f00-114">By default, this message is a warning.</span></span> <span data-ttu-id="e9f00-115">Para obtener información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="e9f00-115">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="e9f00-116">**Id. de error:** BC40028</span><span class="sxs-lookup"><span data-stu-id="e9f00-116">**Error ID:** BC40028</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e9f00-117">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="e9f00-117">To correct this error</span></span>  
  
-   <span data-ttu-id="e9f00-118">Si el procedimiento debe tomar un parámetro de este tipo determinado, quite el <xref:System.CLSCompliantAttribute>.</span><span class="sxs-lookup"><span data-stu-id="e9f00-118">If the procedure must take a parameter of this particular type, remove the <xref:System.CLSCompliantAttribute>.</span></span> <span data-ttu-id="e9f00-119">El procedimiento no puede ser conforme a CLS.</span><span class="sxs-lookup"><span data-stu-id="e9f00-119">The procedure cannot be CLS-compliant.</span></span>  
  
-   <span data-ttu-id="e9f00-120">Si el procedimiento debe ser conforme a CLS, cambie el tipo de este parámetro al tipo conforme a CLS más próximo.</span><span class="sxs-lookup"><span data-stu-id="e9f00-120">If the procedure must be CLS-compliant, change the type of this parameter to the closest CLS-compliant type.</span></span> <span data-ttu-id="e9f00-121">Por ejemplo, en lugar de `UInteger` , quizá pueda usar `Integer` si no necesita que el intervalo de valores esté por encima de 2.147.483.647.</span><span class="sxs-lookup"><span data-stu-id="e9f00-121">For example, in place of `UInteger` you might be able to use `Integer` if you do not need the value range above 2,147,483,647.</span></span> <span data-ttu-id="e9f00-122">Si necesita el intervalo extendido, puede reemplazar `UInteger` por `Long`.</span><span class="sxs-lookup"><span data-stu-id="e9f00-122">If you do need the extended range, you can replace `UInteger` with `Long`.</span></span>  
  
-   <span data-ttu-id="e9f00-123">Si trabaja con objetos de automatización o COM, tenga en cuenta que algunos tipos tienen anchos de datos distintos que en [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e9f00-123">If you are interfacing with Automation or COM objects, keep in mind that some types have different data widths than in the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="e9f00-124">Por ejemplo, `int` suele ser de 16 bits en otros entornos.</span><span class="sxs-lookup"><span data-stu-id="e9f00-124">For example, `int` is often 16 bits in other environments.</span></span> <span data-ttu-id="e9f00-125">Al aceptar un entero de 16 bits de ese componente, declárelo como `Short` en lugar de `Integer` en su código [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] administrado.</span><span class="sxs-lookup"><span data-stu-id="e9f00-125">If you are accepting a 16-bit integer from such a component, declare it as `Short` instead of `Integer` in your managed [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9f00-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="e9f00-126">See Also</span></span>  
 [<span data-ttu-id="e9f00-127">\<PAVE sobre > escribir código conforme a CLS</span><span class="sxs-lookup"><span data-stu-id="e9f00-127">\<PAVE OVER> Writing CLS-Compliant Code</span></span>](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3)
