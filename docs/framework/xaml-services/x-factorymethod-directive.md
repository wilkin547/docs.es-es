---
title: x:FactoryMethod (Directiva)
ms.date: 03/30/2017
helpviewer_keywords:
- XAML. x:FactoryMethod directive [XAML Services]
- FactoryMethod directive in XAML [XAML Services]
- x:FactoryMethod directive [XAML Services]
ms.assetid: 829bcbdf-5318-4afb-9a03-c310e0d2f23d
ms.openlocfilehash: 586965dd4094e81fd830a09b64604cf33f195630
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053776"
---
# <a name="xfactorymethod-directive"></a><span data-ttu-id="f4429-102">x:FactoryMethod (Directiva)</span><span class="sxs-lookup"><span data-stu-id="f4429-102">x:FactoryMethod Directive</span></span>
<span data-ttu-id="f4429-103">Especifica un método que no es un constructor que un procesador XAML debe utilizar para inicializar un objeto después de resolver su tipo de respaldo.</span><span class="sxs-lookup"><span data-stu-id="f4429-103">Specifies a method other than a constructor that a XAML processor should use to initialize an object after resolving its backing type.</span></span>  
  
## <a name="xaml-attribute-usage-no-xarguments"></a><span data-ttu-id="f4429-104">Uso de atributos XAML, no x:Arguments</span><span class="sxs-lookup"><span data-stu-id="f4429-104">XAML Attribute Usage, no x:Arguments</span></span>  
  
```xaml  
<object x:FactoryMethod="methodname"...>  
  ...  
</object>  
```  
  
## <a name="xaml-attribute-usage-xarguments-as-elements"></a><span data-ttu-id="f4429-105">Uso de atributos XAML, x:Arguments como elemento (s)</span><span class="sxs-lookup"><span data-stu-id="f4429-105">XAML Attribute Usage, x:Arguments as Element(s)</span></span>  
  
```xaml  
<object x:FactoryMethod="methodname"...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="f4429-106">Valores XAML</span><span class="sxs-lookup"><span data-stu-id="f4429-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`methodname`|<span data-ttu-id="f4429-107">El nombre del método de cadena de un método que los procesadores XAML llaman para inicializar `object`la instancia especificada como.</span><span class="sxs-lookup"><span data-stu-id="f4429-107">The string method name of a method that XAML processors call to initialize the instance specified as `object`.</span></span> <span data-ttu-id="f4429-108">Vea la sección Comentarios.</span><span class="sxs-lookup"><span data-stu-id="f4429-108">See Remarks.</span></span>|  
|`oneOrMoreObjectElements`|<span data-ttu-id="f4429-109">Uno o más elementos de objeto para los objetos que especifican Factory Method parámetros.</span><span class="sxs-lookup"><span data-stu-id="f4429-109">One or more object elements for objects that specify factory method parameters.</span></span> <span data-ttu-id="f4429-110">El orden es significativo; indica el orden en que los argumentos se deben pasar a la Factory Method.</span><span class="sxs-lookup"><span data-stu-id="f4429-110">Order is significant; it signifies the order in which arguments should be passed to the factory method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f4429-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f4429-111">Remarks</span></span>  
 <span data-ttu-id="f4429-112">Si `methodname` es un método de instancia, no se puede calificar.</span><span class="sxs-lookup"><span data-stu-id="f4429-112">If `methodname` is an instance method, it cannot be qualified.</span></span>  
  
 <span data-ttu-id="f4429-113">Se admiten métodos estáticos como métodos de generador.</span><span class="sxs-lookup"><span data-stu-id="f4429-113">Static methods as factory methods are supported.</span></span> <span data-ttu-id="f4429-114">Si `methodname` es un método estático, `methodname` se proporciona como un *TypeName*.la combinación MethodName, donde *TypeName* nombra la clase que define el Factory Method estático.</span><span class="sxs-lookup"><span data-stu-id="f4429-114">If `methodname` is a static method, `methodname` is provided as a *typeName*.*methodName* combination, where *typeName* names the class that defines the static factory method.</span></span> <span data-ttu-id="f4429-115">*TypeName* se puede calificar como prefijo si se hace referencia a un tipo en un xmlns asignado.</span><span class="sxs-lookup"><span data-stu-id="f4429-115">*typeName* can be prefix-qualified if referring to a type in a mapped xmlns.</span></span> <span data-ttu-id="f4429-116">*TypeName* puede ser un tipo distinto de `typeof(object)`.</span><span class="sxs-lookup"><span data-stu-id="f4429-116">*typeName* can be a different type than `typeof(object)`.</span></span>  
  
 <span data-ttu-id="f4429-117">El Factory Method debe ser un método público declarado del tipo que respalda el elemento de objeto pertinente.</span><span class="sxs-lookup"><span data-stu-id="f4429-117">The factory method must be a declared public method of the type that backs the relevant object element.</span></span>  
  
 <span data-ttu-id="f4429-118">El Factory Method debe devolver una instancia de que se pueda asignar al objeto correspondiente.</span><span class="sxs-lookup"><span data-stu-id="f4429-118">The factory method must return an instance that is assignable to the relevant object.</span></span> <span data-ttu-id="f4429-119">Los métodos de generador nunca deben devolver null.</span><span class="sxs-lookup"><span data-stu-id="f4429-119">Factory methods should never return null.</span></span>  
  
 <span data-ttu-id="f4429-120">`x:Arguments`funciona en un principio de la mejor coincidencia para las signaturas de los métodos de generador.</span><span class="sxs-lookup"><span data-stu-id="f4429-120">`x:Arguments` operates on a principle of best match for signatures of factory methods.</span></span> <span data-ttu-id="f4429-121">La búsqueda de coincidencias evalúa primero el número de parámetros.</span><span class="sxs-lookup"><span data-stu-id="f4429-121">Matching evaluates the parameter count first.</span></span> <span data-ttu-id="f4429-122">Si hay más de una coincidencia posible para el recuento de parámetros, se evalúa el tipo de parámetro y se determina la mejor coincidencia.</span><span class="sxs-lookup"><span data-stu-id="f4429-122">If there is more than one possible match for a parameter count, parameter type is then evaluated and best match is determined.</span></span> <span data-ttu-id="f4429-123">Si todavía hay ambigüedad después de esta fase de evaluación, el comportamiento del procesador XAML es indefinido.</span><span class="sxs-lookup"><span data-stu-id="f4429-123">If there is still ambiguity after this phase of evaluation, XAML processor behavior is undefined.</span></span>  
  
 <span data-ttu-id="f4429-124">El `x:FactoryMethod` uso del elemento no es el uso del elemento de propiedad en el sentido típico, porque el marcado de directivas no hace referencia al tipo del elemento de objeto contenedor.</span><span class="sxs-lookup"><span data-stu-id="f4429-124">The `x:FactoryMethod` element usage is not property element usage in the typical sense, because the directive markup does not reference the containing object element's type.</span></span> <span data-ttu-id="f4429-125">Se espera que el uso de elementos sea menos común que el uso de atributos.</span><span class="sxs-lookup"><span data-stu-id="f4429-125">It is expected that element usage is less common than attribute usage.</span></span> <span data-ttu-id="f4429-126">`x:Arguments`(el uso de atributo o elemento) se puede usar junto `x:FactoryMethod` con el uso de elementos, pero esto no se muestra específicamente en las secciones de uso.</span><span class="sxs-lookup"><span data-stu-id="f4429-126">`x:Arguments` (either attribute or element usage) can be used along with `x:FactoryMethod` element usage, but this is not specifically shown in the Usage sections.</span></span>  
  
 <span data-ttu-id="f4429-127">`x:FactoryMethod`Dado que un elemento debe preceder a cualquier otro elemento de propiedad `x:Arguments` , debe preceder a cualquier elemento que se proporcione también como elemento y debe preceder a cualquier texto de contenido/texto interno/inicialización.</span><span class="sxs-lookup"><span data-stu-id="f4429-127">`x:FactoryMethod` as an element must precede any other property elements, must precede any `x:Arguments` also provided as elements, and must precede any content/inner text/initialization text.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4429-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="f4429-128">See also</span></span>

- [<span data-ttu-id="f4429-129">x:Arguments (directiva)</span><span class="sxs-lookup"><span data-stu-id="f4429-129">x:Arguments Directive</span></span>](x-arguments-directive.md)
