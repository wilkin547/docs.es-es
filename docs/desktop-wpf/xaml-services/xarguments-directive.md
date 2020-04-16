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
# <a name="xarguments-directive"></a>x:Arguments (Directiva)

Empaqueta argumentos de construcción para una declaración de elemento de objeto constructor sin parámetros en XAML o para una declaración de objeto de método de fábrica.

## <a name="xaml-element-usage-nonparameterless-constructor"></a>Uso de elementos XAML (constructor sin parámetros)

```xaml
<object ...>
  <x:Arguments>
    oneOrMoreObjectElements
  </x:Arguments>
</object>
```

## <a name="xaml-element-usage-factory-method"></a>Uso de elementos XAML (método de fábrica)

```xaml
<object x:FactoryMethod="methodName"...>
  <x:Arguments>
    oneOrMoreObjectElements
  </x:Arguments>
</object>
```

## <a name="xaml-values"></a>Valores XAML

|||
|-|-|
|`oneOrMoreObjectElements`|Uno o varios elementos de objeto que especifican argumentos que se pasarán al constructor sin parámetros de respaldo o al método de fábrica.<br /><br /> El uso típico consiste en utilizar texto de inicialización dentro de los elementos de objeto para especificar los valores de argumento reales. Consulte la sección Ejemplos.<br /><br /> El orden de los elementos es significativo. Los tipos XAML en orden deben coincidir con los tipos y el orden de tipos del constructor de respaldo o sobrecarga del método de fábrica.|
|`methodName`|El nombre del método de `x:Arguments` fábrica que debe procesar los argumentos.|

## <a name="dependencies"></a>Dependencias

`x:FactoryMethod`puede modificar el ámbito `x:Arguments` y el comportamiento cuando se aplica.

Si `x:FactoryMethod` no se `x:Arguments` especifica no, se aplica a las firmas alternativas (no predeterminadas) de los constructores de respaldo.

Si `x:FactoryMethod` se especifica, `x:Arguments` se aplica a una sobrecarga del método con nombre.

## <a name="remarks"></a>Observaciones

XAML 2006 puede admitir la inicialización no predeterminada a través del texto de inicialización. Sin embargo, la aplicación práctica de una técnica de construcción de texto de inicialización es limitada. El texto de inicialización se trata como una sola cadena de texto; Por lo tanto, solo agrega capacidad para una inicialización de un solo parámetro a menos que se defina un convertidor de tipos para el comportamiento de construcción que puede analizar elementos de información personalizados y delimitadores personalizados de la cadena. Además, la cadena de texto a la lógica de objeto es potencialmente un convertidor de tipos predeterminado nativo de un analizador XAML determinado para controlar primitivas que no sean una cadena verdadera.

El `x:Arguments` uso de XAML no es el uso de elementos de propiedad en el sentido típico, porque el marcado de directiva no hace referencia al tipo del elemento de objeto contenedor. Es más similar a otras directivas, como `x:Code` donde el elemento marca un intervalo en el que el marcado debe interpretarse como distinto del valor predeterminado para el contenido secundario. En este caso, el tipo XAML de cada elemento de objeto comunica información sobre los tipos de argumento, que usan los analizadores XAML para determinar qué firma de método de generador de constructor específico intenta hacer referencia a un `x:Arguments` uso.

`x:Arguments`para un elemento de objeto que se está construyendo debe preceder a cualquier otro elemento de propiedad, contenido, texto interno o cadenas de inicialización del elemento de objeto. Los elementos `x:Arguments` de objeto dentro pueden incluir atributos y cadenas de inicialización, según lo permita ese tipo XAML y su constructor de respaldo o método de fábrica. Para el objeto o los argumentos, puede especificar tipos XAML personalizados o tipos XAML que, de lo contrario, están fuera del espacio de nombres XAML predeterminado haciendo referencia a las asignaciones de prefijos establecidas.

Los procesadores XAML usan las siguientes directrices `x:Arguments` para determinar cómo se deben usar los argumentos especificados para construir un objeto. Si `x:FactoryMethod` se especifica, la información se `x:FactoryMethod` compara con el `x:FactoryMethod` especificado (tenga en cuenta que el valor de es el nombre del método y el método con nombre puede tener sobrecargas. Si `x:FactoryMethod` no se especifica, la información se compara con el conjunto de todas las sobrecargas del constructor público del objeto. A continuación, la lógica de procesamiento XAML compara el número de parámetros y selecciona la sobrecarga con la aridad coincidente. Si hay más de una coincidencia, el procesador XAML debe comparar los tipos de los parámetros en función de los tipos XAML de los elementos de objeto proporcionados. Si todavía hay más de una coincidencia, el comportamiento del procesador XAML es indefinido. Si `x:FactoryMethod` se especifica a pero no se puede resolver el método, un procesador XAML debe producir una excepción.

Un uso `<x:Arguments>string</x:Arguments>` de atributo XAML es técnicamente posible. Sin embargo, esto no proporciona ninguna funcionalidad más allá de lo que podría hacerse de otro modo a través de los convertidores de texto y tipos de inicialización, y el uso de esta sintaxis no es la intención de diseño de las características del método de fábrica XAML 2009.

## <a name="examples"></a>Ejemplos

En el ejemplo siguiente se muestra una firma de `x:Arguments` constructor sin parámetros y, a continuación, el uso XAML de esa firma tiene acceso a esa firma.

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

En el ejemplo siguiente se muestra una firma `x:Arguments` de método de fábrica de destino y, a continuación, el uso XAML de esa firma tiene acceso a esa firma.

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

## <a name="see-also"></a>Consulte también

- [Definición de tipos personalizados para usarlos con los servicios XAML de .NET](define-custom-types.md)
- [Información general sobre XAML (WPF)](../fundamentals/xaml.md)
