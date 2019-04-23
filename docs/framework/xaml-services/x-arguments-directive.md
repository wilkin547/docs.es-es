---
title: x:Arguments (Directiva)
ms.date: 03/30/2017
helpviewer_keywords:
- x:Arguments directive [XAML Services]
- Arguments directive in XAML [XAML Services]
- XAML [XAML Services], x:Arguments directive
ms.assetid: 87cc10b0-b610-4025-b6b0-ab27ca27c92e
ms.openlocfilehash: a87542513ffeeec7efc526d4218f921d1b7579a1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59184852"
---
# <a name="xarguments-directive"></a><span data-ttu-id="bb3ca-102">x:Arguments (Directiva)</span><span class="sxs-lookup"><span data-stu-id="bb3ca-102">x:Arguments Directive</span></span>
<span data-ttu-id="bb3ca-103">Argumentos de construcción de paquetes para una declaración de elemento de objeto de constructor no predeterminado en XAML o para una declaración de objeto del método de fábrica.</span><span class="sxs-lookup"><span data-stu-id="bb3ca-103">Packages construction arguments for a non-default constructor object element declaration in XAML, or for a factory method object declaration.</span></span>  
  
## <a name="xaml-element-usage-nondefault-constructor"></a><span data-ttu-id="bb3ca-104">Uso de elementos de XAML (constructor no predeterminado)</span><span class="sxs-lookup"><span data-stu-id="bb3ca-104">XAML Element Usage (Nondefault constructor)</span></span>  
  
```  
<object ...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## <a name="xaml-element-usage-factory-method"></a><span data-ttu-id="bb3ca-105">Uso de elementos de XAML (método de fábrica)</span><span class="sxs-lookup"><span data-stu-id="bb3ca-105">XAML Element Usage (factory method)</span></span>  
  
```  
<object x:FactoryMethod="methodName"...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="bb3ca-106">Valores XAML</span><span class="sxs-lookup"><span data-stu-id="bb3ca-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`oneOrMoreObjectElements`|<span data-ttu-id="bb3ca-107">Uno o más elementos de objeto que especifican los argumentos que se pasarán a la copia de seguridad no predeterminado constructor o método generador.</span><span class="sxs-lookup"><span data-stu-id="bb3ca-107">One or more object elements that specify arguments to be passed to the backing non-default constructor or factory method.</span></span><br /><br /> <span data-ttu-id="bb3ca-108">Uso típico es usar el texto de inicialización dentro de los elementos de objeto para especificar los valores de argumento real.</span><span class="sxs-lookup"><span data-stu-id="bb3ca-108">Typical usage is to use initialization text within the object elements to specify the actual argument values.</span></span> <span data-ttu-id="bb3ca-109">Vea la sección ejemplos.</span><span class="sxs-lookup"><span data-stu-id="bb3ca-109">See Examples section.</span></span><br /><br /> <span data-ttu-id="bb3ca-110">El orden de los elementos es significativo.</span><span class="sxs-lookup"><span data-stu-id="bb3ca-110">The order of the elements is significant.</span></span> <span data-ttu-id="bb3ca-111">Los tipos XAML en orden deben coincidir con los tipos y escriba pedido de la sobrecarga del método de constructor o fábrica de respaldo.</span><span class="sxs-lookup"><span data-stu-id="bb3ca-111">The XAML types in order must match the types and type order of the backing constructor or factory method overload.</span></span>|  
|`methodName`|<span data-ttu-id="bb3ca-112">El nombre del método de generador que debe procesar cualquier `x:Arguments` argumentos.</span><span class="sxs-lookup"><span data-stu-id="bb3ca-112">The name of the factory method that should process any `x:Arguments` arguments.</span></span>|  
  
## <a name="dependencies"></a><span data-ttu-id="bb3ca-113">Dependencias</span><span class="sxs-lookup"><span data-stu-id="bb3ca-113">Dependencies</span></span>  
 <span data-ttu-id="bb3ca-114">`x:FactoryMethod` puede modificar el ámbito y comportamiento donde `x:Arguments` se aplica.</span><span class="sxs-lookup"><span data-stu-id="bb3ca-114">`x:FactoryMethod` can modify the scope and behavior where `x:Arguments` applies.</span></span>  
  
 <span data-ttu-id="bb3ca-115">Si no hay ningún `x:FactoryMethod` se especifica, `x:Arguments` se aplica a firmas alternativas (no predeterminada) de los constructores de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="bb3ca-115">If no `x:FactoryMethod` is specified, `x:Arguments` applies to alternate (non-default) signatures of the backing constructors.</span></span>  
  
 <span data-ttu-id="bb3ca-116">Si `x:FactoryMethod` se especifica, `x:Arguments` se aplica a una sobrecarga del método con nombre.</span><span class="sxs-lookup"><span data-stu-id="bb3ca-116">If `x:FactoryMethod` is specified, `x:Arguments` applies to an overload of the named method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bb3ca-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bb3ca-117">Remarks</span></span>  
 <span data-ttu-id="bb3ca-118">XAML 2006 puede admitir la inicialización no predeterminada a través de texto de inicialización.</span><span class="sxs-lookup"><span data-stu-id="bb3ca-118">XAML 2006 can support non-default initialization through initialization text.</span></span> <span data-ttu-id="bb3ca-119">Sin embargo, la aplicación práctica de una técnica de construcción de texto de inicialización es limitada.</span><span class="sxs-lookup"><span data-stu-id="bb3ca-119">However, the practical application of an initialization text construction technique is limited.</span></span> <span data-ttu-id="bb3ca-120">Texto de inicialización se trata como una cadena de texto; por lo tanto, sólo agrega funcionalidad para la inicialización de un único parámetro, a menos que se define un convertidor de tipos para el comportamiento de construcción que pueda analizar los elementos de información personalizada y delimitadores personalizados de la cadena.</span><span class="sxs-lookup"><span data-stu-id="bb3ca-120">Initialization text is treated as a single text string; therefore, it only adds capability for a single parameter initialization unless a type converter is defined for the construction behavior that can parse custom information items and custom delimiters from the string.</span></span> <span data-ttu-id="bb3ca-121">Además, la cadena de texto a la lógica de objeto es potencialmente convertidor de tipos predeterminado nativo del analizador XAML determinado para el tratamiento de tipos primitivos que no sea una cadena de true.</span><span class="sxs-lookup"><span data-stu-id="bb3ca-121">Also, the text string to object logic is potentially a given XAML parser's native default type converter for handling primitives other than a true string.</span></span>  
  
 <span data-ttu-id="bb3ca-122">El `x:Arguments` uso XAML no es el uso de elementos de propiedad en el sentido típico, porque el marcado de la directiva no hace referencia el tipo del elemento de objeto que contiene.</span><span class="sxs-lookup"><span data-stu-id="bb3ca-122">The `x:Arguments` XAML usage is not property element usage in the typical sense, because the directive markup does not reference the containing object element's type.</span></span> <span data-ttu-id="bb3ca-123">Es más similar a otras directivas como `x:Code` donde el elemento demarks un intervalo en el que se debe interpretar el marcado como que no sea el valor predeterminado para el contenido secundario.</span><span class="sxs-lookup"><span data-stu-id="bb3ca-123">It is more akin to other directives such as `x:Code` where the element demarks a range in which the markup should be interpreted as other than the default for child contents.</span></span> <span data-ttu-id="bb3ca-124">En este caso, el tipo XAML de cada elemento de objeto comunica la información sobre los tipos de argumento, que se usa por los analizadores XAML para determinar qué firma del método de fábrica de constructor específico un `x:Arguments` uso está intentando hacer referencia.</span><span class="sxs-lookup"><span data-stu-id="bb3ca-124">In this case, the XAML type of each object element communicates information about the argument types, which is used by XAML parsers to determine which specific constructor factory method signature an `x:Arguments` usage is attempting to reference.</span></span>  
  
 <span data-ttu-id="bb3ca-125">`x:Arguments` para un elemento de objeto que se está construyendo debe preceder a cualquier otro elementos de propiedad, contenido, texto interno o cadenas de inicialización del elemento de objeto.</span><span class="sxs-lookup"><span data-stu-id="bb3ca-125">`x:Arguments` for an object element being constructed must precede any other property elements, content, inner text, or initialization strings of the object element.</span></span> <span data-ttu-id="bb3ca-126">Los elementos de objeto dentro de `x:Arguments` puede incluir atributos y las cadenas de inicialización, según lo permitido por ese tipo XAML y su constructor de respaldo para el método de fábrica.</span><span class="sxs-lookup"><span data-stu-id="bb3ca-126">The object elements within `x:Arguments` can include attributes and initialization strings, as permitted by that XAML type and its backing constructor or factory method.</span></span> <span data-ttu-id="bb3ca-127">Para el objeto o los argumentos, puede especificar los tipos XAML personalizados o tipos XAML que de otro modo fuera de espacio de nombres XAML predeterminado haciendo referencia a asignaciones de prefijo establecido.</span><span class="sxs-lookup"><span data-stu-id="bb3ca-127">For either the object or the arguments, you can specify custom XAML types or XAML types that are otherwise outside the default XAML namespace by referencing established prefix mappings.</span></span>  
  
 <span data-ttu-id="bb3ca-128">Procesadores XAML utilizan las siguientes directrices para determinar cómo se especifican los argumentos en `x:Arguments` debe usarse para construir un objeto.</span><span class="sxs-lookup"><span data-stu-id="bb3ca-128">XAML processors use the following guidelines to determine how the arguments specified in `x:Arguments` should be used to construct an object.</span></span> <span data-ttu-id="bb3ca-129">Si `x:FactoryMethod` se especifica, se compara la información a los especificados `x:FactoryMethod` (tenga en cuenta que el valor de `x:FactoryMethod` es el nombre del método y el método con nombre puede tener sobrecargas.</span><span class="sxs-lookup"><span data-stu-id="bb3ca-129">If `x:FactoryMethod` is specified, information is compared to the specified `x:FactoryMethod` (note that the value of `x:FactoryMethod` is the method name, and the named method can have overloads.</span></span> <span data-ttu-id="bb3ca-130">Si `x:FactoryMethod` no se especifica, se compara con el conjunto de todas las sobrecargas de constructor público del objeto de información.</span><span class="sxs-lookup"><span data-stu-id="bb3ca-130">If `x:FactoryMethod` is not specified, information is compared to the set of all public constructor overloads of the object.</span></span> <span data-ttu-id="bb3ca-131">Lógica de procesamiento de XAML, a continuación, compara el número de parámetros y selecciona la sobrecarga con aridad coincidente.</span><span class="sxs-lookup"><span data-stu-id="bb3ca-131">XAML processing logic then compares the number of parameters and selects the overload with matching arity.</span></span> <span data-ttu-id="bb3ca-132">Si hay más de una coincidencia, el procesador XAML debe comparar los tipos de los parámetros según los tipos XAML de los elementos del objeto proporcionado.</span><span class="sxs-lookup"><span data-stu-id="bb3ca-132">If there is more than one match, the XAML processor should compare the types of the parameters based on the XAML types of the provided object elements.</span></span> <span data-ttu-id="bb3ca-133">Si hay aún más de una coincidencia, el comportamiento del procesador XAML es indefinido.</span><span class="sxs-lookup"><span data-stu-id="bb3ca-133">If there is still more than one match, the XAML processor behavior is undefined.</span></span> <span data-ttu-id="bb3ca-134">Si un `x:FactoryMethod` se especifica, pero el método no se puede resolver, un procesador XAML debe producir una excepción.</span><span class="sxs-lookup"><span data-stu-id="bb3ca-134">If a `x:FactoryMethod` is specified but the method cannot be resolved, a XAML processor should throw an exception.</span></span>  
  
 <span data-ttu-id="bb3ca-135">Un uso de atributos XAML `<x:Arguments>string</x:Arguments>` es técnicamente posible.</span><span class="sxs-lookup"><span data-stu-id="bb3ca-135">A XAML attribute usage `<x:Arguments>string</x:Arguments>` is technically possible.</span></span> <span data-ttu-id="bb3ca-136">Sin embargo, esto no ofrece posibilidades más allá de lo que se podría hacer lo contrario a través de los convertidores de tipos de texto y el tipo de inicialización y con esta sintaxis no es la intención de diseño de las características de método de fábrica de XAML 2009.</span><span class="sxs-lookup"><span data-stu-id="bb3ca-136">However, this provides no capabilities beyond what could be done otherwise through initialization text and type converters, and using this syntax is not the design intention of the XAML 2009 factory method features.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="bb3ca-137">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="bb3ca-137">Examples</span></span>  
 <span data-ttu-id="bb3ca-138">El ejemplo siguiente muestra un constructor no predeterminado, firma y, a continuación, el uso XAML de `x:Arguments` que tiene acceso a esa firma.</span><span class="sxs-lookup"><span data-stu-id="bb3ca-138">The following example shows a non-default constructor signature, then the XAML usage of `x:Arguments` that accesses that signature.</span></span>  
  
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
  
 <span data-ttu-id="bb3ca-139">El ejemplo siguiente muestra una firma de método de fábrica de destino y, a continuación, el uso XAML de `x:Arguments` que tiene acceso a esa firma.</span><span class="sxs-lookup"><span data-stu-id="bb3ca-139">The following example shows a target factory method signature, then the XAML usage of `x:Arguments` that accesses that signature.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="bb3ca-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="bb3ca-140">See also</span></span>

- [<span data-ttu-id="bb3ca-141">Definir tipos personalizados para usarlos con los servicios XAML de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="bb3ca-141">Defining Custom Types for Use with .NET Framework XAML Services</span></span>](defining-custom-types-for-use-with-net-framework-xaml-services.md)
- [<span data-ttu-id="bb3ca-142">Información general sobre XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="bb3ca-142">XAML Overview (WPF)</span></span>](../wpf/advanced/xaml-overview-wpf.md)
