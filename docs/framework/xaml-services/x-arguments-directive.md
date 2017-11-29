---
title: x:Arguments (Directiva)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- x:Arguments directive [XAML Services]
- Arguments directive in XAML [XAML Services]
- XAML [XAML Services], x:Arguments directive
ms.assetid: 87cc10b0-b610-4025-b6b0-ab27ca27c92e
caps.latest.revision: "12"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: 00f605bba709f0ce5f3238ccc3c6ac6cd962f0a4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="xarguments-directive"></a>x:Arguments (Directiva)
Argumentos de construcción de paquetes de una declaración de elemento de objeto de constructor no predeterminado en XAML o de una declaración de objeto del método de fábrica.  
  
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
|`oneOrMoreObjectElements`|Uno o más elementos de objeto que especifican argumentos que se pasan a la copia de seguridad no predeterminado constructor o método generador.<br /><br /> Uso habitual consiste en usar texto de inicialización de los elementos de objeto para especificar los valores de argumento real. Vea la sección ejemplos.<br /><br /> El orden de los elementos es significativo. Los tipos XAML en orden deben coinciden con los tipos y tipo de orden de la sobrecarga del método de constructor o un generador de respaldo.|  
|`methodName`|El nombre del método de generador que debe procesar cualquier `x:Arguments` argumentos.|  
  
## <a name="dependencies"></a>Dependencias  
 `x:FactoryMethod`puede modificar el ámbito y comportamiento donde `x:Arguments` se aplica.  
  
 Si no hay ningún `x:FactoryMethod` se especifica, `x:Arguments` se aplica a firmas alternativas de (no predeterminada) de los constructores de copias de seguridad.  
  
 Si `x:FactoryMethod` se especifica, `x:Arguments` se aplica a una sobrecarga del método con nombre.  
  
## <a name="remarks"></a>Comentarios  
 XAML 2006 puede admitir la inicialización no predeterminada a través de texto de inicialización. Sin embargo, la aplicación práctica de una técnica de construcción de texto de inicialización es limitada. Texto de inicialización se trata como una cadena de texto; por lo tanto, solo agrega capacidad para la inicialización de un único parámetro, salvo que se define un convertidor de tipos para el comportamiento de construcción que puede analizar los elementos de información personalizada y delimitadores personalizados de la cadena. Además, la cadena de texto a la lógica de objeto es potencialmente convertidor de tipos predeterminado nativo del analizador XAML determinado para el tratamiento de tipos primitivos que no sea una cadena es true.  
  
 El `x:Arguments` uso de XAML no es el uso de elementos de propiedad en el sentido típico, porque el marcado de la directiva no hace referencia el tipo del elemento de objeto contenedor. Es más similar a otras directivas como `x:Code` donde el elemento demarks un intervalo en el que el marcado debe interpretarse como que no sea el valor predeterminado para el contenido secundario. En este caso, el tipo XAML de cada elemento de objeto comunica información sobre los tipos de argumento, que es utilizado por los analizadores XAML para determinar qué firma del método de fábrica de constructor específico un `x:Arguments` uso está intentando hacer referencia.  
  
 `x:Arguments`para un elemento de objeto que se está construyendo debe preceder a los otros elementos de propiedad, el contenido, texto interno o cadenas de inicialización del elemento de objeto. Los elementos de objeto dentro de `x:Arguments` puede incluir atributos y cadenas de inicialización, según lo permitido por ese tipo XAML y su constructor de respaldo para el método de fábrica. Para el objeto o los argumentos, puede especificar tipos XAML personalizados o tipos XAML que resulten fuera del espacio de nombres XAML predeterminado haciendo referencia a las asignaciones de prefijo establecido.  
  
 Los procesadores XAML usan las siguientes directrices para determinar cómo se especifican los argumentos en `x:Arguments` debe usarse para construir un objeto. Si `x:FactoryMethod` se especifica, se compara la información a los especificados `x:FactoryMethod` (tenga en cuenta que el valor de `x:FactoryMethod` es el nombre del método y el método con nombre puede tener sobrecargas. Si `x:FactoryMethod` no se especifica, la información se compara con el conjunto de todas las sobrecargas de constructor público del objeto. Lógica de procesamiento de XAML, a continuación, compara el número de parámetros y selecciona la sobrecarga con aridad coincidente. Si hay más de una coincidencia, el procesador XAML debe comparar los tipos de los parámetros en función de los tipos XAML de los elementos de objeto. Si hay todavía más de una coincidencia, el comportamiento del procesador XAML es indefinido. Si un `x:FactoryMethod` se especifica, pero el método no se puede resolver, un procesador XAML debe producir una excepción.  
  
 Un uso de atributos XAML `<x:Arguments>string</x:Arguments>` es técnicamente posible. Sin embargo, esto no proporciona ningún capacidades más allá de lo que podría hacer lo contrario a través de los convertidores de texto y el tipo de inicialización, y el uso de esta sintaxis no es la intención de diseño de las características de método de fábrica de XAML 2009.  
  
## <a name="examples"></a>Ejemplos  
 En el ejemplo siguiente se muestra un constructor no predeterminado, firma y, a continuación, el uso XAML de `x:Arguments` que tiene acceso a esa firma.  
  
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
  
 En el ejemplo siguiente se muestra una firma de método de fábrica de destino y, a continuación, el uso XAML de `x:Arguments` que tiene acceso a esa firma.  
  
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
 [Definir tipos personalizados para usarlos con los servicios XAML de .NET Framework](../../../docs/framework/xaml-services/defining-custom-types-for-use-with-net-framework-xaml-services.md)  
 [Información general sobre XAML (WPF)](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
