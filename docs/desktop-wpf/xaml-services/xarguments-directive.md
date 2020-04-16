---
title: x:Arguments (Directiva)
ms.date: 03/30/2017
helpviewer_keywords:
- x:Arguments directive [XAML Services]
- Arguments directive in XAML [XAML Services]
- XAML [XAML Services], x:Arguments directive
ms.assetid: 87cc10b0-b610-4025-b6b0-ab27ca27c92e
ms.openlocfilehash: 5ec6e192688e1065ea847db6c175ad9da0e743fe
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432837"
---
# <a name="xarguments-directive"></a><span data-ttu-id="e9aab-102">x:Arguments (Directiva)</span><span class="sxs-lookup"><span data-stu-id="e9aab-102">x:Arguments Directive</span></span>

<span data-ttu-id="e9aab-103">Empaqueta argumentos de construcción para una declaración de elemento de objeto constructor sin parámetros en XAML o para una declaración de objeto de método de fábrica.</span><span class="sxs-lookup"><span data-stu-id="e9aab-103">Packages construction arguments for a non-parameterless constructor object element declaration in XAML, or for a factory method object declaration.</span></span>

## <a name="xaml-element-usage-nonparameterless-constructor"></a><span data-ttu-id="e9aab-104">Uso de elementos XAML (constructor sin parámetros)</span><span class="sxs-lookup"><span data-stu-id="e9aab-104">XAML Element Usage (Nonparameterless constructor)</span></span>

```xaml
<object ...>
  <x:Arguments>
    oneOrMoreObjectElements
  </x:Arguments>
</object>
```

## <a name="xaml-element-usage-factory-method"></a><span data-ttu-id="e9aab-105">Uso de elementos XAML (método de fábrica)</span><span class="sxs-lookup"><span data-stu-id="e9aab-105">XAML Element Usage (factory method)</span></span>

```xaml
<object x:FactoryMethod="methodName"...>
  <x:Arguments>
    oneOrMoreObjectElements
  </x:Arguments>
</object>
```

## <a name="xaml-values"></a><span data-ttu-id="e9aab-106">Valores XAML</span><span class="sxs-lookup"><span data-stu-id="e9aab-106">XAML Values</span></span>

|||
|-|-|
|`oneOrMoreObjectElements`|<span data-ttu-id="e9aab-107">Uno o varios elementos de objeto que especifican argumentos que se pasarán al constructor sin parámetros de respaldo o al método de fábrica.</span><span class="sxs-lookup"><span data-stu-id="e9aab-107">One or more object elements that specify arguments to be passed to the backing non-parameterless constructor or factory method.</span></span><br /><br /> <span data-ttu-id="e9aab-108">El uso típico consiste en utilizar texto de inicialización dentro de los elementos de objeto para especificar los valores de argumento reales.</span><span class="sxs-lookup"><span data-stu-id="e9aab-108">Typical usage is to use initialization text within the object elements to specify the actual argument values.</span></span> <span data-ttu-id="e9aab-109">Consulte la sección Ejemplos.</span><span class="sxs-lookup"><span data-stu-id="e9aab-109">See Examples section.</span></span><br /><br /> <span data-ttu-id="e9aab-110">El orden de los elementos es significativo.</span><span class="sxs-lookup"><span data-stu-id="e9aab-110">The order of the elements is significant.</span></span> <span data-ttu-id="e9aab-111">Los tipos XAML en orden deben coincidir con los tipos y el orden de tipos del constructor de respaldo o sobrecarga del método de fábrica.</span><span class="sxs-lookup"><span data-stu-id="e9aab-111">The XAML types in order must match the types and type order of the backing constructor or factory method overload.</span></span>|
|`methodName`|<span data-ttu-id="e9aab-112">El nombre del método de `x:Arguments` fábrica que debe procesar los argumentos.</span><span class="sxs-lookup"><span data-stu-id="e9aab-112">The name of the factory method that should process any `x:Arguments` arguments.</span></span>|

## <a name="dependencies"></a><span data-ttu-id="e9aab-113">Dependencias</span><span class="sxs-lookup"><span data-stu-id="e9aab-113">Dependencies</span></span>

<span data-ttu-id="e9aab-114">`x:FactoryMethod`puede modificar el ámbito `x:Arguments` y el comportamiento cuando se aplica.</span><span class="sxs-lookup"><span data-stu-id="e9aab-114">`x:FactoryMethod` can modify the scope and behavior where `x:Arguments` applies.</span></span>

<span data-ttu-id="e9aab-115">Si `x:FactoryMethod` no se `x:Arguments` especifica no, se aplica a las firmas alternativas (no predeterminadas) de los constructores de respaldo.</span><span class="sxs-lookup"><span data-stu-id="e9aab-115">If no `x:FactoryMethod` is specified, `x:Arguments` applies to alternate (non-default) signatures of the backing constructors.</span></span>

<span data-ttu-id="e9aab-116">Si `x:FactoryMethod` se especifica, `x:Arguments` se aplica a una sobrecarga del método con nombre.</span><span class="sxs-lookup"><span data-stu-id="e9aab-116">If `x:FactoryMethod` is specified, `x:Arguments` applies to an overload of the named method.</span></span>

## <a name="remarks"></a><span data-ttu-id="e9aab-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e9aab-117">Remarks</span></span>

<span data-ttu-id="e9aab-118">XAML 2006 puede admitir la inicialización no predeterminada a través del texto de inicialización.</span><span class="sxs-lookup"><span data-stu-id="e9aab-118">XAML 2006 can support non-default initialization through initialization text.</span></span> <span data-ttu-id="e9aab-119">Sin embargo, la aplicación práctica de una técnica de construcción de texto de inicialización es limitada.</span><span class="sxs-lookup"><span data-stu-id="e9aab-119">However, the practical application of an initialization text construction technique is limited.</span></span> <span data-ttu-id="e9aab-120">El texto de inicialización se trata como una sola cadena de texto; Por lo tanto, solo agrega capacidad para una inicialización de un solo parámetro a menos que se defina un convertidor de tipos para el comportamiento de construcción que puede analizar elementos de información personalizados y delimitadores personalizados de la cadena.</span><span class="sxs-lookup"><span data-stu-id="e9aab-120">Initialization text is treated as a single text string; therefore, it only adds capability for a single parameter initialization unless a type converter is defined for the construction behavior that can parse custom information items and custom delimiters from the string.</span></span> <span data-ttu-id="e9aab-121">Además, la cadena de texto a la lógica de objeto es potencialmente un convertidor de tipos predeterminado nativo de un analizador XAML determinado para controlar primitivas que no sean una cadena verdadera.</span><span class="sxs-lookup"><span data-stu-id="e9aab-121">Also, the text string to object logic is potentially a given XAML parser's native default type converter for handling primitives other than a true string.</span></span>

<span data-ttu-id="e9aab-122">El `x:Arguments` uso de XAML no es el uso de elementos de propiedad en el sentido típico, porque el marcado de directiva no hace referencia al tipo del elemento de objeto contenedor.</span><span class="sxs-lookup"><span data-stu-id="e9aab-122">The `x:Arguments` XAML usage is not property element usage in the typical sense, because the directive markup does not reference the containing object element's type.</span></span> <span data-ttu-id="e9aab-123">Es más similar a otras directivas, como `x:Code` donde el elemento marca un intervalo en el que el marcado debe interpretarse como distinto del valor predeterminado para el contenido secundario.</span><span class="sxs-lookup"><span data-stu-id="e9aab-123">It is more akin to other directives such as `x:Code` where the element demarks a range in which the markup should be interpreted as other than the default for child contents.</span></span> <span data-ttu-id="e9aab-124">En este caso, el tipo XAML de cada elemento de objeto comunica información sobre los tipos de argumento, que usan los analizadores XAML para determinar qué firma de método de generador de constructor específico intenta hacer referencia a un `x:Arguments` uso.</span><span class="sxs-lookup"><span data-stu-id="e9aab-124">In this case, the XAML type of each object element communicates information about the argument types, which is used by XAML parsers to determine which specific constructor factory method signature an `x:Arguments` usage is attempting to reference.</span></span>

<span data-ttu-id="e9aab-125">`x:Arguments`para un elemento de objeto que se está construyendo debe preceder a cualquier otro elemento de propiedad, contenido, texto interno o cadenas de inicialización del elemento de objeto.</span><span class="sxs-lookup"><span data-stu-id="e9aab-125">`x:Arguments` for an object element being constructed must precede any other property elements, content, inner text, or initialization strings of the object element.</span></span> <span data-ttu-id="e9aab-126">Los elementos `x:Arguments` de objeto dentro pueden incluir atributos y cadenas de inicialización, según lo permita ese tipo XAML y su constructor de respaldo o método de fábrica.</span><span class="sxs-lookup"><span data-stu-id="e9aab-126">The object elements within `x:Arguments` can include attributes and initialization strings, as permitted by that XAML type and its backing constructor or factory method.</span></span> <span data-ttu-id="e9aab-127">Para el objeto o los argumentos, puede especificar tipos XAML personalizados o tipos XAML que, de lo contrario, están fuera del espacio de nombres XAML predeterminado haciendo referencia a las asignaciones de prefijos establecidas.</span><span class="sxs-lookup"><span data-stu-id="e9aab-127">For either the object or the arguments, you can specify custom XAML types or XAML types that are otherwise outside the default XAML namespace by referencing established prefix mappings.</span></span>

<span data-ttu-id="e9aab-128">Los procesadores XAML usan las siguientes directrices `x:Arguments` para determinar cómo se deben usar los argumentos especificados para construir un objeto.</span><span class="sxs-lookup"><span data-stu-id="e9aab-128">XAML processors use the following guidelines to determine how the arguments specified in `x:Arguments` should be used to construct an object.</span></span> <span data-ttu-id="e9aab-129">Si `x:FactoryMethod` se especifica, la información se `x:FactoryMethod` compara con el `x:FactoryMethod` especificado (tenga en cuenta que el valor de es el nombre del método y el método con nombre puede tener sobrecargas.</span><span class="sxs-lookup"><span data-stu-id="e9aab-129">If `x:FactoryMethod` is specified, information is compared to the specified `x:FactoryMethod` (note that the value of `x:FactoryMethod` is the method name, and the named method can have overloads.</span></span> <span data-ttu-id="e9aab-130">Si `x:FactoryMethod` no se especifica, la información se compara con el conjunto de todas las sobrecargas del constructor público del objeto.</span><span class="sxs-lookup"><span data-stu-id="e9aab-130">If `x:FactoryMethod` is not specified, information is compared to the set of all public constructor overloads of the object.</span></span> <span data-ttu-id="e9aab-131">A continuación, la lógica de procesamiento XAML compara el número de parámetros y selecciona la sobrecarga con la aridad coincidente.</span><span class="sxs-lookup"><span data-stu-id="e9aab-131">XAML processing logic then compares the number of parameters and selects the overload with matching arity.</span></span> <span data-ttu-id="e9aab-132">Si hay más de una coincidencia, el procesador XAML debe comparar los tipos de los parámetros en función de los tipos XAML de los elementos de objeto proporcionados.</span><span class="sxs-lookup"><span data-stu-id="e9aab-132">If there is more than one match, the XAML processor should compare the types of the parameters based on the XAML types of the provided object elements.</span></span> <span data-ttu-id="e9aab-133">Si todavía hay más de una coincidencia, el comportamiento del procesador XAML es indefinido.</span><span class="sxs-lookup"><span data-stu-id="e9aab-133">If there is still more than one match, the XAML processor behavior is undefined.</span></span> <span data-ttu-id="e9aab-134">Si `x:FactoryMethod` se especifica a pero no se puede resolver el método, un procesador XAML debe producir una excepción.</span><span class="sxs-lookup"><span data-stu-id="e9aab-134">If a `x:FactoryMethod` is specified but the method cannot be resolved, a XAML processor should throw an exception.</span></span>

<span data-ttu-id="e9aab-135">Un uso `<x:Arguments>string</x:Arguments>` de atributo XAML es técnicamente posible.</span><span class="sxs-lookup"><span data-stu-id="e9aab-135">A XAML attribute usage `<x:Arguments>string</x:Arguments>` is technically possible.</span></span> <span data-ttu-id="e9aab-136">Sin embargo, esto no proporciona ninguna funcionalidad más allá de lo que podría hacerse de otro modo a través de los convertidores de texto y tipos de inicialización, y el uso de esta sintaxis no es la intención de diseño de las características del método de fábrica XAML 2009.</span><span class="sxs-lookup"><span data-stu-id="e9aab-136">However, this provides no capabilities beyond what could be done otherwise through initialization text and type converters, and using this syntax is not the design intention of the XAML 2009 factory method features.</span></span>

## <a name="examples"></a><span data-ttu-id="e9aab-137">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="e9aab-137">Examples</span></span>

<span data-ttu-id="e9aab-138">En el ejemplo siguiente se muestra una firma de `x:Arguments` constructor sin parámetros y, a continuación, el uso XAML de esa firma tiene acceso a esa firma.</span><span class="sxs-lookup"><span data-stu-id="e9aab-138">The following example shows a non-parameterless constructor signature, then the XAML usage of `x:Arguments` that accesses that signature.</span></span>

```csharp
public class Food {
  private string _name;
  private Int32 _calories;
  public Food(string name, Int32 calories) {
      _name=name;
      _calories=calories;
  }
}
```

```xaml
<my:Food>
  <x:Arguments>
      <x:String>Apple</x:String>
      <x:Int32>150</x:Int32>
  </x:Arguments>
</my:Food>
```

<span data-ttu-id="e9aab-139">En el ejemplo siguiente se muestra una firma `x:Arguments` de método de fábrica de destino y, a continuación, el uso XAML de esa firma tiene acceso a esa firma.</span><span class="sxs-lookup"><span data-stu-id="e9aab-139">The following example shows a target factory method signature, then the XAML usage of `x:Arguments` that accesses that signature.</span></span>

```csharp
public Food TryLookupFood(string name)
{
switch (name) {
  case "Apple": return new Food("Apple",150);
  case "Chocolate": return new Food("Chocolate",200);
  case "Cheese": return new Food("Cheese", 450);
  default: {return new Food(name,0);
}
}
```

```xaml
<my:Food x:FactoryMethod="TryLookupFood">
  <x:Arguments>
      <x:String>Apple</x:String>
  </x:Arguments>
</my:Food>
```

## <a name="see-also"></a><span data-ttu-id="e9aab-140">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e9aab-140">See also</span></span>

- [<span data-ttu-id="e9aab-141">Definición de tipos personalizados para usarlos con los servicios XAML de .NET</span><span class="sxs-lookup"><span data-stu-id="e9aab-141">Defining Custom Types for Use with .NET XAML Services</span></span>](define-custom-types.md)
- [<span data-ttu-id="e9aab-142">Información general sobre XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="e9aab-142">XAML Overview (WPF)</span></span>](../fundamentals/xaml.md)
