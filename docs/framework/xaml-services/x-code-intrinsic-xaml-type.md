---
title: x:Code (Tipo XAML intrínseco)
ms.date: 03/30/2017
f1_keywords:
- Code
- x:Code
- xCode
helpviewer_keywords:
- Code directive in XAML [XAML Services]
- x:Code XAML directive element [XAML Services]
- XAML [XAML Services], x:Code directive element
ms.assetid: 87986b13-1a2e-4830-ae36-15f9dc5629e8
ms.openlocfilehash: 2b7713548b6269f079ef32b5bf1fe4fa630edcc8
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053793"
---
# <a name="xcode-intrinsic-xaml-type"></a><span data-ttu-id="f49a1-102">x:Code (Tipo XAML intrínseco)</span><span class="sxs-lookup"><span data-stu-id="f49a1-102">x:Code Intrinsic XAML Type</span></span>
<span data-ttu-id="f49a1-103">Permite colocar código dentro de un entorno de producción XAML.</span><span class="sxs-lookup"><span data-stu-id="f49a1-103">Allows placement of code within a XAML production.</span></span> <span data-ttu-id="f49a1-104">Este código se puede compilar con cualquier implementación de procesador XAML que compile XAML, o bien en la producción XAML para usos posteriores, como la interpretación de un Runtime.</span><span class="sxs-lookup"><span data-stu-id="f49a1-104">Such code can either be compiled by any XAML processor implementation that compiles XAML, or left in the XAML production for later uses such as interpretation by a runtime.</span></span>  
  
## <a name="xaml-object-element-usage"></a><span data-ttu-id="f49a1-105">Uso de elementos de objeto XAML</span><span class="sxs-lookup"><span data-stu-id="f49a1-105">XAML Object Element Usage</span></span>  
  
```xaml  
<x:Code>  
   // code instructions, usually enclosed by CDATA...  
</x:Code>  
```  
  
## <a name="remarks"></a><span data-ttu-id="f49a1-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f49a1-106">Remarks</span></span>  
 <span data-ttu-id="f49a1-107">El código dentro del `x:Code` elemento de directiva de XAML se interpreta en el espacio de nombres XML general y en los espacios de nombres XAML proporcionados.</span><span class="sxs-lookup"><span data-stu-id="f49a1-107">The code within the `x:Code` XAML directive element is still interpreted within the general XML namespace and the XAML namespaces provided.</span></span> <span data-ttu-id="f49a1-108">Por lo tanto, normalmente es necesario incluir el código utilizado para `x:Code` dentro de `CDATA` un segmento.</span><span class="sxs-lookup"><span data-stu-id="f49a1-108">Therefore, it is usually necessary to enclose the code used for `x:Code` inside a `CDATA` segment.</span></span>  
  
 <span data-ttu-id="f49a1-109">`x:Code`no está permitida para todos los mecanismos de implementación posibles de una producción de XAML.</span><span class="sxs-lookup"><span data-stu-id="f49a1-109">`x:Code` is not permitted for all possible deployment mechanisms of a XAML production.</span></span> <span data-ttu-id="f49a1-110">En marcos de trabajo específicos (por ejemplo, WPF), se debe compilar el código.</span><span class="sxs-lookup"><span data-stu-id="f49a1-110">In specific frameworks (for example WPF) the code must be compiled.</span></span> <span data-ttu-id="f49a1-111">En otros marcos, `x:Code` el uso podría no estar permitido por lo general.</span><span class="sxs-lookup"><span data-stu-id="f49a1-111">In other frameworks, `x:Code` usage might be generally disallowed.</span></span>  
  
 <span data-ttu-id="f49a1-112">En el caso de los marcos `x:Code` que permiten contenido administrado, el compilador `x:Code` de lenguaje correcto que se va a usar para el contenido está determinado por la configuración y los destinos del proyecto contenedor que se usa para compilar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f49a1-112">For frameworks that permit managed `x:Code` content, the correct language compiler to use for `x:Code` content is determined by settings and targets of the containing project that is used to compile the application.</span></span>  
  
## <a name="wpf-usage-notes"></a><span data-ttu-id="f49a1-113">Notas de uso de WPF</span><span class="sxs-lookup"><span data-stu-id="f49a1-113">WPF Usage Notes</span></span>  
 <span data-ttu-id="f49a1-114">El código declarado `x:Code` en para WPF tiene varias limitaciones importantes:</span><span class="sxs-lookup"><span data-stu-id="f49a1-114">Code declared within `x:Code` for WPF has several notable limitations:</span></span>  
  
- <span data-ttu-id="f49a1-115">El `x:Code` elemento de Directiva debe ser un elemento secundario inmediato del elemento raíz de la producción XAML.</span><span class="sxs-lookup"><span data-stu-id="f49a1-115">The `x:Code` directive element must be an immediate child element of the root element of the XAML production.</span></span>  
  
- <span data-ttu-id="f49a1-116">se debe proporcionar la [Directiva x:Class](x-class-directive.md) en el elemento raíz primario.</span><span class="sxs-lookup"><span data-stu-id="f49a1-116">[x:Class Directive](x-class-directive.md) must be provided on the parent root element.</span></span>  
  
- <span data-ttu-id="f49a1-117">El código colocado dentro `x:Code` de se tratará mediante compilación para que esté dentro del ámbito de la clase parcial que ya se está creando para esa página XAML.</span><span class="sxs-lookup"><span data-stu-id="f49a1-117">The code placed within `x:Code` will be treated by compilation to be within the scope of the partial class that is already being created for that XAML page.</span></span> <span data-ttu-id="f49a1-118">Por lo tanto, todo el código que defina debe ser miembro o variables de esa clase parcial.</span><span class="sxs-lookup"><span data-stu-id="f49a1-118">Therefore all code you define must be members or variables of that partial class.</span></span>  
  
- <span data-ttu-id="f49a1-119">No se pueden definir clases adicionales, aparte de anidar una clase dentro de la clase parcial (se permite el anidamiento, pero no es típico porque no se puede hacer referencia a las clases anidadas en XAML).</span><span class="sxs-lookup"><span data-stu-id="f49a1-119">You cannot define additional classes, other than by nesting a class inside the partial class (nesting is allowed, but it is not typical because nested classes cannot be referenced in XAML).</span></span> <span data-ttu-id="f49a1-120">Los espacios de nombres CLR distintos del espacio de nombres que se usa para la clase parcial existente no se pueden definir ni agregar a.</span><span class="sxs-lookup"><span data-stu-id="f49a1-120">CLR namespaces other than the namespace that is used for the existing partial class cannot be defined or added to.</span></span>  
  
- <span data-ttu-id="f49a1-121">Todas las referencias a entidades de código fuera del espacio de nombres CLR de clase parcial deben ser completas.</span><span class="sxs-lookup"><span data-stu-id="f49a1-121">References to code entities outside the partial class CLR namespace must all be fully qualified.</span></span> <span data-ttu-id="f49a1-122">Si los miembros que se declaran son invalidaciones de los miembros reemplazables de clase parcial, debe especificarse con la palabra clave override específica del lenguaje.</span><span class="sxs-lookup"><span data-stu-id="f49a1-122">If members being declared are overrides to the partial class overridable members, this must be specified with the language-specific override keyword.</span></span> <span data-ttu-id="f49a1-123">Si los miembros declarados en el ámbito entran en `x:Code` conflicto con los miembros de la clase parcial creada fuera del código XAML, de tal forma que el compilador notifique el conflicto, el archivo XAML no se puede compilar ni cargar.</span><span class="sxs-lookup"><span data-stu-id="f49a1-123">If members declared in `x:Code` scope conflict with members of the partial class created out of the XAML, in such a way that the compiler reports the conflict, the XAML file cannot compile or load.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f49a1-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="f49a1-124">See also</span></span>

- [<span data-ttu-id="f49a1-125">x:Class (Directiva)</span><span class="sxs-lookup"><span data-stu-id="f49a1-125">x:Class Directive</span></span>](x-class-directive.md)
- [<span data-ttu-id="f49a1-126">Código subyacente y XAML en WPF</span><span class="sxs-lookup"><span data-stu-id="f49a1-126">Code-Behind and XAML in WPF</span></span>](../wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [<span data-ttu-id="f49a1-127">Información general sobre XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="f49a1-127">XAML Overview (WPF)</span></span>](../wpf/advanced/xaml-overview-wpf.md)
