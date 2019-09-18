---
title: x:Arguments (Directiva)
ms.date: 03/30/2017
helpviewer_keywords:
- x:Arguments directive [XAML Services]
- Arguments directive in XAML [XAML Services]
- XAML [XAML Services], x:Arguments directive
ms.assetid: 87cc10b0-b610-4025-b6b0-ab27ca27c92e
ms.openlocfilehash: a18de9a07839f5b01620311832b85667680c12ad
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053834"
---
# <a name="xarguments-directive"></a><span data-ttu-id="daa58-102">x:Arguments (Directiva)</span><span class="sxs-lookup"><span data-stu-id="daa58-102">x:Arguments Directive</span></span>
<span data-ttu-id="daa58-103">Empaqueta los argumentos de una declaración de elemento de objeto constructor sin parámetros en XAML o para una declaración de objeto Factory Method.</span><span class="sxs-lookup"><span data-stu-id="daa58-103">Packages construction arguments for a non-parameterless constructor object element declaration in XAML, or for a factory method object declaration.</span></span>  
  
## <a name="xaml-element-usage-nonparameterless-constructor"></a><span data-ttu-id="daa58-104">Uso de elementos XAML (constructor sin parámetros)</span><span class="sxs-lookup"><span data-stu-id="daa58-104">XAML Element Usage (Nonparameterless constructor)</span></span>  
  
```xaml  
<object ...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## <a name="xaml-element-usage-factory-method"></a><span data-ttu-id="daa58-105">Uso de elementos XAML (Factory Method)</span><span class="sxs-lookup"><span data-stu-id="daa58-105">XAML Element Usage (factory method)</span></span>  
  
```xaml  
<object x:FactoryMethod="methodName"...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="daa58-106">Valores XAML</span><span class="sxs-lookup"><span data-stu-id="daa58-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`oneOrMoreObjectElements`|<span data-ttu-id="daa58-107">Uno o más elementos de objeto que especifican los argumentos que se van a pasar al constructor o Factory Method sin parámetros de respaldo.</span><span class="sxs-lookup"><span data-stu-id="daa58-107">One or more object elements that specify arguments to be passed to the backing non-parameterless constructor or factory method.</span></span><br /><br /> <span data-ttu-id="daa58-108">El uso típico es usar el texto de inicialización dentro de los elementos de objeto para especificar los valores de argumento reales.</span><span class="sxs-lookup"><span data-stu-id="daa58-108">Typical usage is to use initialization text within the object elements to specify the actual argument values.</span></span> <span data-ttu-id="daa58-109">Vea la sección ejemplos.</span><span class="sxs-lookup"><span data-stu-id="daa58-109">See Examples section.</span></span><br /><br /> <span data-ttu-id="daa58-110">El orden de los elementos es significativo.</span><span class="sxs-lookup"><span data-stu-id="daa58-110">The order of the elements is significant.</span></span> <span data-ttu-id="daa58-111">Los tipos XAML en orden deben coincidir con los tipos y el orden del tipo del constructor de respaldo o de Factory Method sobrecarga.</span><span class="sxs-lookup"><span data-stu-id="daa58-111">The XAML types in order must match the types and type order of the backing constructor or factory method overload.</span></span>|  
|`methodName`|<span data-ttu-id="daa58-112">Nombre del Factory Method que debe procesar cualquier `x:Arguments` argumento.</span><span class="sxs-lookup"><span data-stu-id="daa58-112">The name of the factory method that should process any `x:Arguments` arguments.</span></span>|  
  
## <a name="dependencies"></a><span data-ttu-id="daa58-113">Dependencias</span><span class="sxs-lookup"><span data-stu-id="daa58-113">Dependencies</span></span>  
 <span data-ttu-id="daa58-114">`x:FactoryMethod`puede modificar el ámbito y el comportamiento `x:Arguments` donde se aplica.</span><span class="sxs-lookup"><span data-stu-id="daa58-114">`x:FactoryMethod` can modify the scope and behavior where `x:Arguments` applies.</span></span>  
  
 <span data-ttu-id="daa58-115">Si no `x:FactoryMethod` se especifica, `x:Arguments` se aplica a las firmas alternativas (no predeterminadas) de los constructores de respaldo.</span><span class="sxs-lookup"><span data-stu-id="daa58-115">If no `x:FactoryMethod` is specified, `x:Arguments` applies to alternate (non-default) signatures of the backing constructors.</span></span>  
  
 <span data-ttu-id="daa58-116">Si `x:FactoryMethod` se especifica, `x:Arguments` se aplica a una sobrecarga del método con nombre.</span><span class="sxs-lookup"><span data-stu-id="daa58-116">If `x:FactoryMethod` is specified, `x:Arguments` applies to an overload of the named method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="daa58-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="daa58-117">Remarks</span></span>  
 <span data-ttu-id="daa58-118">XAML 2006 puede admitir la inicialización no predeterminada a través del texto de inicialización.</span><span class="sxs-lookup"><span data-stu-id="daa58-118">XAML 2006 can support non-default initialization through initialization text.</span></span> <span data-ttu-id="daa58-119">Sin embargo, la aplicación práctica de una técnica de construcción de texto de inicialización es limitada.</span><span class="sxs-lookup"><span data-stu-id="daa58-119">However, the practical application of an initialization text construction technique is limited.</span></span> <span data-ttu-id="daa58-120">El texto de inicialización se trata como una sola cadena de texto; por lo tanto, solo agrega funcionalidad para la inicialización de un solo parámetro, a menos que se defina un convertidor de tipos para el comportamiento de construcción que puede analizar elementos de información personalizados y delimitadores personalizados de la cadena.</span><span class="sxs-lookup"><span data-stu-id="daa58-120">Initialization text is treated as a single text string; therefore, it only adds capability for a single parameter initialization unless a type converter is defined for the construction behavior that can parse custom information items and custom delimiters from the string.</span></span> <span data-ttu-id="daa58-121">Además, la cadena de texto a la lógica del objeto es potencialmente un convertidor de tipos predeterminado nativo del analizador XAML para controlar los primitivos que no sean una cadena true.</span><span class="sxs-lookup"><span data-stu-id="daa58-121">Also, the text string to object logic is potentially a given XAML parser's native default type converter for handling primitives other than a true string.</span></span>  
  
 <span data-ttu-id="daa58-122">El `x:Arguments` uso de XAML no es el uso de elementos de propiedad en el sentido típico, porque el marcado de directivas no hace referencia al tipo del elemento de objeto contenedor.</span><span class="sxs-lookup"><span data-stu-id="daa58-122">The `x:Arguments` XAML usage is not property element usage in the typical sense, because the directive markup does not reference the containing object element's type.</span></span> <span data-ttu-id="daa58-123">Es más similar a otras directivas, `x:Code` como cuando el elemento marca un intervalo en el que el marcado debe interpretarse como distinto del predeterminado para el contenido secundario.</span><span class="sxs-lookup"><span data-stu-id="daa58-123">It is more akin to other directives such as `x:Code` where the element demarks a range in which the markup should be interpreted as other than the default for child contents.</span></span> <span data-ttu-id="daa58-124">En este caso, el tipo XAML de cada elemento de objeto comunica información sobre los tipos de argumento, que los analizadores XAML usan para determinar qué constructor específico Factory Method firma a `x:Arguments` la que está intentando hacer referencia un uso.</span><span class="sxs-lookup"><span data-stu-id="daa58-124">In this case, the XAML type of each object element communicates information about the argument types, which is used by XAML parsers to determine which specific constructor factory method signature an `x:Arguments` usage is attempting to reference.</span></span>  
  
 <span data-ttu-id="daa58-125">`x:Arguments`para que un elemento de objeto que se está construyendo debe preceder a cualquier otro elemento de propiedad, contenido, texto interno o cadena de inicialización del elemento de objeto.</span><span class="sxs-lookup"><span data-stu-id="daa58-125">`x:Arguments` for an object element being constructed must precede any other property elements, content, inner text, or initialization strings of the object element.</span></span> <span data-ttu-id="daa58-126">Los elementos de objeto `x:Arguments` dentro de pueden incluir atributos y cadenas de inicialización, según lo permitido por ese tipo XAML y su constructor de respaldo o Factory Method.</span><span class="sxs-lookup"><span data-stu-id="daa58-126">The object elements within `x:Arguments` can include attributes and initialization strings, as permitted by that XAML type and its backing constructor or factory method.</span></span> <span data-ttu-id="daa58-127">En el caso del objeto o de los argumentos, puede especificar tipos XAML personalizados o tipos XAML que, de otro modo, se encuentran fuera del espacio de nombres XAML predeterminado haciendo referencia a las asignaciones de prefijo establecidas.</span><span class="sxs-lookup"><span data-stu-id="daa58-127">For either the object or the arguments, you can specify custom XAML types or XAML types that are otherwise outside the default XAML namespace by referencing established prefix mappings.</span></span>  
  
 <span data-ttu-id="daa58-128">Los procesadores XAML usan las siguientes directrices para determinar cómo se deben usar `x:Arguments` los argumentos especificados en para construir un objeto.</span><span class="sxs-lookup"><span data-stu-id="daa58-128">XAML processors use the following guidelines to determine how the arguments specified in `x:Arguments` should be used to construct an object.</span></span> <span data-ttu-id="daa58-129">Si `x:FactoryMethod` se especifica, la información se compara con la `x:FactoryMethod` especificada (tenga en cuenta que `x:FactoryMethod` el valor de es el nombre del método y el método con nombre puede tener sobrecargas.</span><span class="sxs-lookup"><span data-stu-id="daa58-129">If `x:FactoryMethod` is specified, information is compared to the specified `x:FactoryMethod` (note that the value of `x:FactoryMethod` is the method name, and the named method can have overloads.</span></span> <span data-ttu-id="daa58-130">Si `x:FactoryMethod` no se especifica, la información se compara con el conjunto de todas las sobrecargas del constructor público del objeto.</span><span class="sxs-lookup"><span data-stu-id="daa58-130">If `x:FactoryMethod` is not specified, information is compared to the set of all public constructor overloads of the object.</span></span> <span data-ttu-id="daa58-131">A continuación, la lógica de procesamiento de XAML compara el número de parámetros y selecciona la sobrecarga con aridad coincidente.</span><span class="sxs-lookup"><span data-stu-id="daa58-131">XAML processing logic then compares the number of parameters and selects the overload with matching arity.</span></span> <span data-ttu-id="daa58-132">Si hay más de una coincidencia, el procesador XAML debe comparar los tipos de los parámetros en función de los tipos XAML de los elementos de objeto proporcionados.</span><span class="sxs-lookup"><span data-stu-id="daa58-132">If there is more than one match, the XAML processor should compare the types of the parameters based on the XAML types of the provided object elements.</span></span> <span data-ttu-id="daa58-133">Si todavía hay más de una coincidencia, el comportamiento del procesador XAML es indefinido.</span><span class="sxs-lookup"><span data-stu-id="daa58-133">If there is still more than one match, the XAML processor behavior is undefined.</span></span> <span data-ttu-id="daa58-134">Si se `x:FactoryMethod` especifica un, pero el método no se puede resolver, un procesador XAML debe producir una excepción.</span><span class="sxs-lookup"><span data-stu-id="daa58-134">If a `x:FactoryMethod` is specified but the method cannot be resolved, a XAML processor should throw an exception.</span></span>  
  
 <span data-ttu-id="daa58-135">Técnicamente es posible el `<x:Arguments>string</x:Arguments>` uso de atributos XAML.</span><span class="sxs-lookup"><span data-stu-id="daa58-135">A XAML attribute usage `<x:Arguments>string</x:Arguments>` is technically possible.</span></span> <span data-ttu-id="daa58-136">Sin embargo, esto no proporciona ninguna funcionalidad más allá de lo que se podía hacer de otro modo mediante el texto de inicialización y convertidores de tipos, y el uso de esta sintaxis no es la intención de diseño de las características de Factory Method de XAML 2009.</span><span class="sxs-lookup"><span data-stu-id="daa58-136">However, this provides no capabilities beyond what could be done otherwise through initialization text and type converters, and using this syntax is not the design intention of the XAML 2009 factory method features.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="daa58-137">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="daa58-137">Examples</span></span>  
 <span data-ttu-id="daa58-138">En el ejemplo siguiente se muestra una firma de constructor sin parámetros y, a continuación, `x:Arguments` el uso de XAML de que tiene acceso a esa firma.</span><span class="sxs-lookup"><span data-stu-id="daa58-138">The following example shows a non-parameterless constructor signature, then the XAML usage of `x:Arguments` that accesses that signature.</span></span>  
  
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
  
 <span data-ttu-id="daa58-139">En el ejemplo siguiente se muestra un destino Factory Method firma y, a continuación `x:Arguments` , el uso de XAML de que tiene acceso a esa firma.</span><span class="sxs-lookup"><span data-stu-id="daa58-139">The following example shows a target factory method signature, then the XAML usage of `x:Arguments` that accesses that signature.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="daa58-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="daa58-140">See also</span></span>

- [<span data-ttu-id="daa58-141">Definir tipos personalizados para usarlos con los servicios XAML de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="daa58-141">Defining Custom Types for Use with .NET Framework XAML Services</span></span>](defining-custom-types-for-use-with-net-framework-xaml-services.md)
- [<span data-ttu-id="daa58-142">Información general sobre XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="daa58-142">XAML Overview (WPF)</span></span>](../wpf/advanced/xaml-overview-wpf.md)
