---
title: x:FactoryMethod (Directiva)
ms.date: 03/30/2017
helpviewer_keywords:
- XAML. x:FactoryMethod directive [XAML Services]
- FactoryMethod directive in XAML [XAML Services]
- x:FactoryMethod directive [XAML Services]
ms.assetid: 829bcbdf-5318-4afb-9a03-c310e0d2f23d
ms.openlocfilehash: 5e864b6f5d664b079036a5d915e2f6f81b83639f
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432789"
---
# <a name="xfactorymethod-directive"></a><span data-ttu-id="4d134-102">x:FactoryMethod (Directiva)</span><span class="sxs-lookup"><span data-stu-id="4d134-102">x:FactoryMethod Directive</span></span>
<span data-ttu-id="4d134-103">Especifica un método distinto de un constructor que un procesador XAML debe usar para inicializar un objeto después de resolver su tipo de respaldo.</span><span class="sxs-lookup"><span data-stu-id="4d134-103">Specifies a method other than a constructor that a XAML processor should use to initialize an object after resolving its backing type.</span></span>  
  
## <a name="xaml-attribute-usage-no-xarguments"></a><span data-ttu-id="4d134-104">Uso de atributos XAML, sin x:Arguments</span><span class="sxs-lookup"><span data-stu-id="4d134-104">XAML Attribute Usage, no x:Arguments</span></span>  
  
```xaml  
<object x:FactoryMethod="methodname"...>  
  ...  
</object>  
```  
  
## <a name="xaml-attribute-usage-xarguments-as-elements"></a><span data-ttu-id="4d134-105">Uso de atributos XAML, x:Arguments as Element(s)</span><span class="sxs-lookup"><span data-stu-id="4d134-105">XAML Attribute Usage, x:Arguments as Element(s)</span></span>  
  
```xaml  
<object x:FactoryMethod="methodname"...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="4d134-106">Valores XAML</span><span class="sxs-lookup"><span data-stu-id="4d134-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`methodname`|<span data-ttu-id="4d134-107">El nombre del método de cadena de un método `object`al que llaman los procesadores XAML para inicializar la instancia especificada como .</span><span class="sxs-lookup"><span data-stu-id="4d134-107">The string method name of a method that XAML processors call to initialize the instance specified as `object`.</span></span> <span data-ttu-id="4d134-108">Vea la sección Comentarios.</span><span class="sxs-lookup"><span data-stu-id="4d134-108">See Remarks.</span></span>|  
|`oneOrMoreObjectElements`|<span data-ttu-id="4d134-109">Uno o varios elementos de objeto para objetos que especifican parámetros de método de fábrica.</span><span class="sxs-lookup"><span data-stu-id="4d134-109">One or more object elements for objects that specify factory method parameters.</span></span> <span data-ttu-id="4d134-110">El orden es significativo; significa el orden en que los argumentos deben pasarse al método de fábrica.</span><span class="sxs-lookup"><span data-stu-id="4d134-110">Order is significant; it signifies the order in which arguments should be passed to the factory method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4d134-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="4d134-111">Remarks</span></span>  
 <span data-ttu-id="4d134-112">Si `methodname` es un método de instancia, no se puede calificar.</span><span class="sxs-lookup"><span data-stu-id="4d134-112">If `methodname` is an instance method, it cannot be qualified.</span></span>  
  
 <span data-ttu-id="4d134-113">Se admiten métodos estáticos como métodos de fábrica.</span><span class="sxs-lookup"><span data-stu-id="4d134-113">Static methods as factory methods are supported.</span></span> <span data-ttu-id="4d134-114">Si `methodname` es un `methodname` método estático, `typeName.methodName` se `typeName` proporciona como una combinación, donde nombra la clase que define el método de fábrica estático.</span><span class="sxs-lookup"><span data-stu-id="4d134-114">If `methodname` is a static method, `methodname` is provided as a `typeName.methodName` combination, where `typeName` names the class that defines the static factory method.</span></span> <span data-ttu-id="4d134-115">`typeName`puede ser calificado por prefijo si se hace referencia a un tipo en un xmlns asignado.</span><span class="sxs-lookup"><span data-stu-id="4d134-115">`typeName` can be prefix-qualified if referring to a type in a mapped xmlns.</span></span> <span data-ttu-id="4d134-116">`typeName`puede ser un `typeof(object)`tipo diferente que .</span><span class="sxs-lookup"><span data-stu-id="4d134-116">`typeName` can be a different type than `typeof(object)`.</span></span>  
  
 <span data-ttu-id="4d134-117">El método factory debe ser un método público declarado del tipo que respalda el elemento de objeto relevante.</span><span class="sxs-lookup"><span data-stu-id="4d134-117">The factory method must be a declared public method of the type that backs the relevant object element.</span></span>  
  
 <span data-ttu-id="4d134-118">El método factory debe devolver una instancia que se pueda asignar al objeto relevante.</span><span class="sxs-lookup"><span data-stu-id="4d134-118">The factory method must return an instance that is assignable to the relevant object.</span></span> <span data-ttu-id="4d134-119">Los métodos de fábrica nunca deben devolver null.</span><span class="sxs-lookup"><span data-stu-id="4d134-119">Factory methods should never return null.</span></span>  
  
 <span data-ttu-id="4d134-120">`x:Arguments`opera sobre un principio de mejor coincidencia para las firmas de los métodos de fábrica.</span><span class="sxs-lookup"><span data-stu-id="4d134-120">`x:Arguments` operates on a principle of best match for signatures of factory methods.</span></span> <span data-ttu-id="4d134-121">La coincidencia evalúa primero el recuento de parámetros.</span><span class="sxs-lookup"><span data-stu-id="4d134-121">Matching evaluates the parameter count first.</span></span> <span data-ttu-id="4d134-122">Si hay más de una coincidencia posible para un recuento de parámetros, se evalúa el tipo de parámetro y se determina la mejor coincidencia.</span><span class="sxs-lookup"><span data-stu-id="4d134-122">If there is more than one possible match for a parameter count, parameter type is then evaluated and best match is determined.</span></span> <span data-ttu-id="4d134-123">Si todavía hay ambiguedad después de esta fase de evaluación, el comportamiento del procesador XAML es indefinido.</span><span class="sxs-lookup"><span data-stu-id="4d134-123">If there is still ambiguity after this phase of evaluation, XAML processor behavior is undefined.</span></span>  
  
 <span data-ttu-id="4d134-124">El `x:FactoryMethod` uso del elemento no es el uso del elemento de propiedad en el sentido típico, porque el marcado de directiva no hace referencia al tipo del elemento de objeto contenedor.</span><span class="sxs-lookup"><span data-stu-id="4d134-124">The `x:FactoryMethod` element usage is not property element usage in the typical sense, because the directive markup does not reference the containing object element's type.</span></span> <span data-ttu-id="4d134-125">Se espera que el uso de elementos sea menos común que el uso de atributos.</span><span class="sxs-lookup"><span data-stu-id="4d134-125">It is expected that element usage is less common than attribute usage.</span></span> <span data-ttu-id="4d134-126">`x:Arguments`(uso de atributos o elementos) se puede utilizar junto con `x:FactoryMethod` el uso de elementos, pero esto no se muestra específicamente en las secciones Uso.</span><span class="sxs-lookup"><span data-stu-id="4d134-126">`x:Arguments` (either attribute or element usage) can be used along with `x:FactoryMethod` element usage, but this is not specifically shown in the Usage sections.</span></span>  
  
 <span data-ttu-id="4d134-127">`x:FactoryMethod`como un elemento debe preceder a cualquier `x:Arguments` otro elemento de propiedad, debe preceder a cualquier elemento proporcionado también como y debe preceder a cualquier contenido/texto interno/texto de inicialización.</span><span class="sxs-lookup"><span data-stu-id="4d134-127">`x:FactoryMethod` as an element must precede any other property elements, must precede any `x:Arguments` also provided as elements, and must precede any content/inner text/initialization text.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d134-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4d134-128">See also</span></span>

- [<span data-ttu-id="4d134-129">x:Arguments (Directiva)</span><span class="sxs-lookup"><span data-stu-id="4d134-129">x:Arguments Directive</span></span>](xarguments-directive.md)
