---
title: x:FactoryMethod (Directiva)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XAML. x:FactoryMethod directive [XAML Services]
- FactoryMethod directive in XAML [XAML Services]
- x:FactoryMethod directive [XAML Services]
ms.assetid: 829bcbdf-5318-4afb-9a03-c310e0d2f23d
caps.latest.revision: "8"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 58349c5440d0062c64346933e48b64de6c4c7b60
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="xfactorymethod-directive"></a><span data-ttu-id="6bb73-102">x:FactoryMethod (Directiva)</span><span class="sxs-lookup"><span data-stu-id="6bb73-102">x:FactoryMethod Directive</span></span>
<span data-ttu-id="6bb73-103">Especifica un método que no sea un constructor que un procesador XAML debe usar para inicializar un objeto después de resolver su tipo de respaldo.</span><span class="sxs-lookup"><span data-stu-id="6bb73-103">Specifies a method other than a constructor that a XAML processor should use to initialize an object after resolving its backing type.</span></span>  
  
## <a name="xaml-attribute-usage-no-xarguments"></a><span data-ttu-id="6bb73-104">Uso de atributos XAML, sin x: Arguments</span><span class="sxs-lookup"><span data-stu-id="6bb73-104">XAML Attribute Usage, no x:Arguments</span></span>  
  
```  
<object x:FactoryMethod="methodname"...>  
  ...  
</object>  
```  
  
## <a name="xaml-attribute-usage-xarguments-as-elements"></a><span data-ttu-id="6bb73-105">Uso de atributos XAML, x: Arguments como elemento (s)</span><span class="sxs-lookup"><span data-stu-id="6bb73-105">XAML Attribute Usage, x:Arguments as Element(s)</span></span>  
  
```  
<object x:FactoryMethod="methodname"...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="6bb73-106">Valores XAML</span><span class="sxs-lookup"><span data-stu-id="6bb73-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`methodname`|<span data-ttu-id="6bb73-107">El nombre del método de cadena de un método que llamen procesadores XAML para inicializar la instancia especificada como `object`.</span><span class="sxs-lookup"><span data-stu-id="6bb73-107">The string method name of a method that XAML processors call to initialize the instance specified as `object`.</span></span> <span data-ttu-id="6bb73-108">Vea la sección Comentarios.</span><span class="sxs-lookup"><span data-stu-id="6bb73-108">See Remarks.</span></span>|  
|`oneOrMoreObjectElements`|<span data-ttu-id="6bb73-109">Uno o más elementos de objeto para los objetos que especifican los parámetros de método de fábrica.</span><span class="sxs-lookup"><span data-stu-id="6bb73-109">One or more object elements for objects that specify factory method parameters.</span></span> <span data-ttu-id="6bb73-110">El orden es importante; indica el orden en que los argumentos se deberían pasar al método de generador.</span><span class="sxs-lookup"><span data-stu-id="6bb73-110">Order is significant; it signifies the order in which arguments should be passed to the factory method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6bb73-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6bb73-111">Remarks</span></span>  
 <span data-ttu-id="6bb73-112">Si `methodname` es un método de instancia, no se puede calificar.</span><span class="sxs-lookup"><span data-stu-id="6bb73-112">If `methodname` is an instance method, it cannot be qualified.</span></span>  
  
 <span data-ttu-id="6bb73-113">Se admiten métodos estáticos como métodos de generador.</span><span class="sxs-lookup"><span data-stu-id="6bb73-113">Static methods as factory methods are supported.</span></span> <span data-ttu-id="6bb73-114">Si `methodname` es un método estático, `methodname` se proporciona como un *typeName*. *methodName* combinación, donde *typeName* nombre a la clase que define el método de generador estático.</span><span class="sxs-lookup"><span data-stu-id="6bb73-114">If `methodname` is a static method, `methodname` is provided as a *typeName*.*methodName* combination, where *typeName* names the class that defines the static factory method.</span></span> <span data-ttu-id="6bb73-115">*typeName* puede ser calificada con prefijo si se hace referencia a un tipo en un xmlns asignado.</span><span class="sxs-lookup"><span data-stu-id="6bb73-115">*typeName* can be prefix-qualified if referring to a type in a mapped xmlns.</span></span> <span data-ttu-id="6bb73-116">*typeName* puede ser un tipo diferente de `typeof(``object``)`.</span><span class="sxs-lookup"><span data-stu-id="6bb73-116">*typeName* can be a different type than `typeof(``object``)`.</span></span>  
  
 <span data-ttu-id="6bb73-117">El método de generador debe ser un método público declarado del tipo que respalda el elemento de objeto pertinente.</span><span class="sxs-lookup"><span data-stu-id="6bb73-117">The factory method must be a declared public method of the type that backs the relevant object element.</span></span>  
  
 <span data-ttu-id="6bb73-118">El método de generador debe devolver una instancia que se puede asignar al objeto pertinente.</span><span class="sxs-lookup"><span data-stu-id="6bb73-118">The factory method must return an instance that is assignable to the relevant object.</span></span> <span data-ttu-id="6bb73-119">Métodos de generador nunca deberían devolver nulos.</span><span class="sxs-lookup"><span data-stu-id="6bb73-119">Factory methods should never return null.</span></span>  
  
 <span data-ttu-id="6bb73-120">`x:Arguments`opera en un principio de mejor coincidencia para las firmas de métodos de generador.</span><span class="sxs-lookup"><span data-stu-id="6bb73-120">`x:Arguments` operates on a principle of best match for signatures of factory methods.</span></span> <span data-ttu-id="6bb73-121">Búsqueda de coincidencias, el número de parámetros evalúa primero.</span><span class="sxs-lookup"><span data-stu-id="6bb73-121">Matching evaluates the parameter count first.</span></span> <span data-ttu-id="6bb73-122">Si hay más de una coincidencia posible para un recuento de parámetros, tipo de parámetro es, a continuación, evalúa y mejor coincidencia vendrá determinada.</span><span class="sxs-lookup"><span data-stu-id="6bb73-122">If there is more than one possible match for a parameter count, parameter type is then evaluated and best match is determined.</span></span> <span data-ttu-id="6bb73-123">Si todavía no hay ambigüedad después de esta fase de evaluación, el comportamiento del procesador XAML es indefinido.</span><span class="sxs-lookup"><span data-stu-id="6bb73-123">If there is still ambiguity after this phase of evaluation, XAML processor behavior is undefined.</span></span>  
  
 <span data-ttu-id="6bb73-124">El `x:FactoryMethod` uso de elementos no es el uso de elementos de propiedad en el sentido típico, porque el marcado de la directiva no hace referencia el tipo del elemento de objeto contenedor.</span><span class="sxs-lookup"><span data-stu-id="6bb73-124">The `x:FactoryMethod` element usage is not property element usage in the typical sense, because the directive markup does not reference the containing object element's type.</span></span> <span data-ttu-id="6bb73-125">Se espera que el uso de elemento es menos común que el uso de atributos.</span><span class="sxs-lookup"><span data-stu-id="6bb73-125">It is expected that element usage is less common than attribute usage.</span></span> <span data-ttu-id="6bb73-126">`x:Arguments`(uso de atributo o elemento) que puede utilizarse junto con `x:FactoryMethod` uso de elementos, pero esto no se muestra específicamente en las secciones de uso.</span><span class="sxs-lookup"><span data-stu-id="6bb73-126">`x:Arguments` (either attribute or element usage) can be used along with `x:FactoryMethod` element usage, but this is not specifically shown in the Usage sections.</span></span>  
  
 <span data-ttu-id="6bb73-127">`x:FactoryMethod`como un elemento debe preceder a cualquier otro elemento de propiedad, debe preceder a cualquier `x:Arguments` también proporcionado como elemento y debe preceder a cualquier texto de inicialización de texto de contenido o interna.</span><span class="sxs-lookup"><span data-stu-id="6bb73-127">`x:FactoryMethod` as an element must precede any other property elements, must precede any `x:Arguments` also provided as elements, and must precede any content/inner text/initialization text.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bb73-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="6bb73-128">See Also</span></span>  
 [<span data-ttu-id="6bb73-129">x:Arguments (directiva)</span><span class="sxs-lookup"><span data-stu-id="6bb73-129">x:Arguments Directive</span></span>](../../../docs/framework/xaml-services/x-arguments-directive.md)
