---
title: "x:Code (Tipo XAML intrínseco)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- Code
- x:Code
- xCode
helpviewer_keywords:
- Code directive in XAML [XAML Services]
- x:Code XAML directive element [XAML Services]
- XAML [XAML Services], x:Code directive element
ms.assetid: 87986b13-1a2e-4830-ae36-15f9dc5629e8
caps.latest.revision: "19"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: d1b21e2a654b18547c8da7da724c87946724f71f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="xcode-intrinsic-xaml-type"></a><span data-ttu-id="c0964-102">x:Code (Tipo XAML intrínseco)</span><span class="sxs-lookup"><span data-stu-id="c0964-102">x:Code Intrinsic XAML Type</span></span>
<span data-ttu-id="c0964-103">Permite la colocación de código dentro de una producción de XAML.</span><span class="sxs-lookup"><span data-stu-id="c0964-103">Allows placement of code within a XAML production.</span></span> <span data-ttu-id="c0964-104">O bien se puede compilar este código si cualquier implementación de procesador XAML que compila XAML o a la izquierda en la producción de XAML para usos posteriores como interpretación por un runtime.</span><span class="sxs-lookup"><span data-stu-id="c0964-104">Such code can either be compiled by any XAML processor implementation that compiles XAML, or left in the XAML production for later uses such as interpretation by a runtime.</span></span>  
  
## <a name="xaml-object-element-usage"></a><span data-ttu-id="c0964-105">Uso de elementos de objeto XAML</span><span class="sxs-lookup"><span data-stu-id="c0964-105">XAML Object Element Usage</span></span>  
  
```  
<x:Code>  
   // code instructions, usually enclosed by CDATA...  
</x:Code>  
```  
  
## <a name="remarks"></a><span data-ttu-id="c0964-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c0964-106">Remarks</span></span>  
 <span data-ttu-id="c0964-107">El código dentro de la `x:Code` elemento de directiva de XAML es sigue interpretado dentro del espacio de nombres XML general y los espacios de nombres XAML proporcionado.</span><span class="sxs-lookup"><span data-stu-id="c0964-107">The code within the `x:Code` XAML directive element is still interpreted within the general XML namespace and the XAML namespaces provided.</span></span> <span data-ttu-id="c0964-108">Por lo tanto, resulta suele ser necesario incluir el código utilizado para `x:Code` dentro de un `CDATA` segmento.</span><span class="sxs-lookup"><span data-stu-id="c0964-108">Therefore, it is usually necessary to enclose the code used for `x:Code` inside a `CDATA` segment.</span></span>  
  
 <span data-ttu-id="c0964-109">`x:Code`no se permite para todos los mecanismos de implementación posibles de una producción de XAML.</span><span class="sxs-lookup"><span data-stu-id="c0964-109">`x:Code` is not permitted for all possible deployment mechanisms of a XAML production.</span></span> <span data-ttu-id="c0964-110">En marcos concretos (por ejemplo, WPF) se debe compilar el código.</span><span class="sxs-lookup"><span data-stu-id="c0964-110">In specific frameworks (for example WPF) the code must be compiled.</span></span> <span data-ttu-id="c0964-111">En otros marcos, `x:Code` uso no podría permitirse generalmente.</span><span class="sxs-lookup"><span data-stu-id="c0964-111">In other frameworks, `x:Code` usage might be generally disallowed.</span></span>  
  
 <span data-ttu-id="c0964-112">Para los marcos de trabajo que permiten administrado `x:Code` de contenido, el compilador del lenguaje correcto que se usará para `x:Code` contenido viene determinado por la configuración y los destinos del proyecto contenedor que se utiliza para compilar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="c0964-112">For frameworks that permit managed `x:Code` content, the correct language compiler to use for `x:Code` content is determined by settings and targets of the containing project that is used to compile the application.</span></span>  
  
## <a name="wpf-usage-notes"></a><span data-ttu-id="c0964-113">Notas de uso WPF</span><span class="sxs-lookup"><span data-stu-id="c0964-113">WPF Usage Notes</span></span>  
 <span data-ttu-id="c0964-114">Código declarados dentro de `x:Code` para WPF tiene varias limitaciones importantes:</span><span class="sxs-lookup"><span data-stu-id="c0964-114">Code declared within `x:Code` for WPF has several notable limitations:</span></span>  
  
-   <span data-ttu-id="c0964-115">El `x:Code` elemento de directiva debe ser un elemento secundario inmediato del elemento raíz de la producción de XAML.</span><span class="sxs-lookup"><span data-stu-id="c0964-115">The `x:Code` directive element must be an immediate child element of the root element of the XAML production.</span></span>  
  
-   <span data-ttu-id="c0964-116">[x: Class Directive](../../../docs/framework/xaml-services/x-class-directive.md) debe proporcionarse en el elemento raíz primario.</span><span class="sxs-lookup"><span data-stu-id="c0964-116">[x:Class Directive](../../../docs/framework/xaml-services/x-class-directive.md) must be provided on the parent root element.</span></span>  
  
-   <span data-ttu-id="c0964-117">El código se coloca dentro de `x:Code` tratará la compilación para estar dentro del ámbito de la clase parcial que ya se está creando para esa página XAML.</span><span class="sxs-lookup"><span data-stu-id="c0964-117">The code placed within `x:Code` will be treated by compilation to be within the scope of the partial class that is already being created for that XAML page.</span></span> <span data-ttu-id="c0964-118">Por lo tanto, todo el código que defina debe ser miembros o variables de esa clase parcial.</span><span class="sxs-lookup"><span data-stu-id="c0964-118">Therefore all code you define must be members or variables of that partial class.</span></span>  
  
-   <span data-ttu-id="c0964-119">No se puede definir clases adicionales, no sea anidando una clase dentro de la clase parcial (está permitido el anidamiento, pero no es normal, porque no se pueden hacer referencia a las clases anidadas en XAML).</span><span class="sxs-lookup"><span data-stu-id="c0964-119">You cannot define additional classes, other than by nesting a class inside the partial class (nesting is allowed, but it is not typical because nested classes cannot be referenced in XAML).</span></span> <span data-ttu-id="c0964-120">Espacios de nombres CLR que no sea el espacio de nombres que se usa para la clase parcial existente se no se define o agregar a.</span><span class="sxs-lookup"><span data-stu-id="c0964-120">CLR namespaces other than the namespace that is used for the existing partial class cannot be defined or added to.</span></span>  
  
-   <span data-ttu-id="c0964-121">Las referencias a entidades de código fuera del espacio de nombres CLR de clase parcial deben ser completas.</span><span class="sxs-lookup"><span data-stu-id="c0964-121">References to code entities outside the partial class CLR namespace must all be fully qualified.</span></span> <span data-ttu-id="c0964-122">Si los miembros que se declara son invalidaciones para los miembros reemplazables de clase parcial, éste debe especificarse con la palabra clave override específicos del idioma.</span><span class="sxs-lookup"><span data-stu-id="c0964-122">If members being declared are overrides to the partial class overridable members, this must be specified with the language-specific override keyword.</span></span> <span data-ttu-id="c0964-123">Si los miembros declarados en `x:Code` ámbito entran en conflicto con los miembros de la clase parcial creados fuera de XAML, de tal manera que el compilador informa de los conflictos, el archivo XAML no se cargará ni compilará.</span><span class="sxs-lookup"><span data-stu-id="c0964-123">If members declared in `x:Code` scope conflict with members of the partial class created out of the XAML, in such a way that the compiler reports the conflict, the XAML file cannot compile or load.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0964-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="c0964-124">See Also</span></span>  
 [<span data-ttu-id="c0964-125">x:Class (Directiva)</span><span class="sxs-lookup"><span data-stu-id="c0964-125">x:Class Directive</span></span>](../../../docs/framework/xaml-services/x-class-directive.md)  
 [<span data-ttu-id="c0964-126">Código subyacente y XAML en WPF</span><span class="sxs-lookup"><span data-stu-id="c0964-126">Code-Behind and XAML in WPF</span></span>](../../../docs/framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)  
 [<span data-ttu-id="c0964-127">Información general sobre XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="c0964-127">XAML Overview (WPF)</span></span>](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
