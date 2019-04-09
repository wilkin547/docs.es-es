---
title: x:Arguments (Directiva)
ms.date: 03/30/2017
helpviewer_keywords:
- x:Arguments directive [XAML Services]
- Arguments directive in XAML [XAML Services]
- XAML [XAML Services], x:Arguments directive
ms.assetid: 87cc10b0-b610-4025-b6b0-ab27ca27c92e
ms.openlocfilehash: a87542513ffeeec7efc526d4218f921d1b7579a1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59184852"
---
# <a name="xarguments-directive"></a>x:Arguments (Directiva)
Argumentos de construcción de paquetes para una declaración de elemento de objeto de constructor no predeterminado en XAML o para una declaración de objeto del método de fábrica.  
  
## <a name="xaml-element-usage-nondefault-constructor"></a>Uso de elementos de XAML (constructor no predeterminado)  
  
```  
<object ...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## <a name="xaml-element-usage-factory-method"></a>Uso de elementos de XAML (método de fábrica)  
  
```  
<object x:FactoryMethod="methodName"...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## <a name="xaml-values"></a>Valores XAML  
  
|||  
|-|-|  
|`oneOrMoreObjectElements`|Uno o más elementos de objeto que especifican los argumentos que se pasarán a la copia de seguridad no predeterminado constructor o método generador.<br /><br /> Uso típico es usar el texto de inicialización dentro de los elementos de objeto para especificar los valores de argumento real. Vea la sección ejemplos.<br /><br /> El orden de los elementos es significativo. Los tipos XAML en orden deben coincidir con los tipos y escriba pedido de la sobrecarga del método de constructor o fábrica de respaldo.|  
|`methodName`|El nombre del método de generador que debe procesar cualquier `x:Arguments` argumentos.|  
  
## <a name="dependencies"></a>Dependencias  
 `x:FactoryMethod` puede modificar el ámbito y comportamiento donde `x:Arguments` se aplica.  
  
 Si no hay ningún `x:FactoryMethod` se especifica, `x:Arguments` se aplica a firmas alternativas (no predeterminada) de los constructores de copia de seguridad.  
  
 Si `x:FactoryMethod` se especifica, `x:Arguments` se aplica a una sobrecarga del método con nombre.  
  
## <a name="remarks"></a>Comentarios  
 XAML 2006 puede admitir la inicialización no predeterminada a través de texto de inicialización. Sin embargo, la aplicación práctica de una técnica de construcción de texto de inicialización es limitada. Texto de inicialización se trata como una cadena de texto; por lo tanto, sólo agrega funcionalidad para la inicialización de un único parámetro, a menos que se define un convertidor de tipos para el comportamiento de construcción que pueda analizar los elementos de información personalizada y delimitadores personalizados de la cadena. Además, la cadena de texto a la lógica de objeto es potencialmente convertidor de tipos predeterminado nativo del analizador XAML determinado para el tratamiento de tipos primitivos que no sea una cadena de true.  
  
 El `x:Arguments` uso XAML no es el uso de elementos de propiedad en el sentido típico, porque el marcado de la directiva no hace referencia el tipo del elemento de objeto que contiene. Es más similar a otras directivas como `x:Code` donde el elemento demarks un intervalo en el que se debe interpretar el marcado como que no sea el valor predeterminado para el contenido secundario. En este caso, el tipo XAML de cada elemento de objeto comunica la información sobre los tipos de argumento, que se usa por los analizadores XAML para determinar qué firma del método de fábrica de constructor específico un `x:Arguments` uso está intentando hacer referencia.  
  
 `x:Arguments` para un elemento de objeto que se está construyendo debe preceder a cualquier otro elementos de propiedad, contenido, texto interno o cadenas de inicialización del elemento de objeto. Los elementos de objeto dentro de `x:Arguments` puede incluir atributos y las cadenas de inicialización, según lo permitido por ese tipo XAML y su constructor de respaldo para el método de fábrica. Para el objeto o los argumentos, puede especificar los tipos XAML personalizados o tipos XAML que de otro modo fuera de espacio de nombres XAML predeterminado haciendo referencia a asignaciones de prefijo establecido.  
  
 Procesadores XAML utilizan las siguientes directrices para determinar cómo se especifican los argumentos en `x:Arguments` debe usarse para construir un objeto. Si `x:FactoryMethod` se especifica, se compara la información a los especificados `x:FactoryMethod` (tenga en cuenta que el valor de `x:FactoryMethod` es el nombre del método y el método con nombre puede tener sobrecargas. Si `x:FactoryMethod` no se especifica, se compara con el conjunto de todas las sobrecargas de constructor público del objeto de información. Lógica de procesamiento de XAML, a continuación, compara el número de parámetros y selecciona la sobrecarga con aridad coincidente. Si hay más de una coincidencia, el procesador XAML debe comparar los tipos de los parámetros según los tipos XAML de los elementos del objeto proporcionado. Si hay aún más de una coincidencia, el comportamiento del procesador XAML es indefinido. Si un `x:FactoryMethod` se especifica, pero el método no se puede resolver, un procesador XAML debe producir una excepción.  
  
 Un uso de atributos XAML `<x:Arguments>string</x:Arguments>` es técnicamente posible. Sin embargo, esto no ofrece posibilidades más allá de lo que se podría hacer lo contrario a través de los convertidores de tipos de texto y el tipo de inicialización y con esta sintaxis no es la intención de diseño de las características de método de fábrica de XAML 2009.  
  
## <a name="examples"></a>Ejemplos  
 El ejemplo siguiente muestra un constructor no predeterminado, firma y, a continuación, el uso XAML de `x:Arguments` que tiene acceso a esa firma.  
  
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
  
 El ejemplo siguiente muestra una firma de método de fábrica de destino y, a continuación, el uso XAML de `x:Arguments` que tiene acceso a esa firma.  
  
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
  
## <a name="see-also"></a>Vea también

- [Definir tipos personalizados para usarlos con los servicios XAML de .NET Framework](defining-custom-types-for-use-with-net-framework-xaml-services.md)
- [Información general sobre XAML (WPF)](../wpf/advanced/xaml-overview-wpf.md)
