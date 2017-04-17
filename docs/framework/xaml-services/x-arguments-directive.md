---
title: "x:Arguments Directive | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "x:Arguments directive [XAML Services]"
  - "Arguments directive in XAML [XAML Services]"
  - "XAML [XAML Services], x:Arguments directive"
ms.assetid: 87cc10b0-b610-4025-b6b0-ab27ca27c92e
caps.latest.revision: 12
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 12
---
# x:Arguments Directive
Argumentos de construcción de paquetes para una declaración de elemento de objeto de constructor no predeterminado en XAM, o para una declaración de objeto del método de generador.  
  
## Uso de elementos de XAML \(constructor no predeterminado\)  
  
```  
<object ...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## Uso de elementos de XAML \(método de generador\)  
  
```  
<object x:FactoryMethod="methodName"...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## Valores XAML  
  
|||  
|-|-|  
|`oneOrMoreObjectElements`|Uno o más elementos de objeto que especifican argumentos que se van a pasar al método generador o constructor de respaldo no predeterminado.<br /><br /> El uso típico consiste en utilizar texto de inicialización en los elementos del objeto para especificar los valores de los argumentos reales.  Vea la sección de ejemplos.<br /><br /> El orden de los elementos es significativo.  Los tipos XAML ordenados deben coincidir con los tipos del constructor de respaldo o sobrecarga de método del generador y el orden de estos.|  
|`methodName`|Nombre del método de generador que debe procesar cualquier argumento `x:Arguments`.|  
  
## Dependencias  
 `x:FactoryMethod` puede modificar el ámbito y comportamiento donde se aplica `x:Arguments`.  
  
 Si no se especifica ningún `x:FactoryMethod`, `x:Arguments` se aplica a firmas alternativas \(no predeterminadas\) de los constructores de respaldo.  
  
 Si se especifica `x:FactoryMethod`, `x:Arguments` se aplica en una sobrecarga del método con nombre.  
  
## Comentarios  
 XAML 2006 puede admitir la inicialización no predeterminada a través de texto de inicialización.  Sin embargo, se limita la aplicación práctica de una técnica de construcción de texto de inicialización.  El texto de inicialización se trata como una única cadena de texto; por lo tanto, sólo agrega la capacidad para una única inicialización de parámetro, a menos que se defina un convertidor de tipos para el comportamiento de construcción que pueda analizar los elementos de información personalizados y los delimitadores personalizados de la cadena.  Asimismo, la cadena de texto a la lógica del objeto es posiblemente un convertidor de tipos predeterminado nativo de un analizador de XAML determinado para controlar tipos primitivos que no son una cadena verdadera.  
  
 La sintaxis del XAML de `x:Arguments` no es una sintaxis de elemento de propiedad en el sentido típico, porque el marcado de la directiva no hace referencia al tipo del elemento del objeto que contiene.  Es más semejante a otras directivas como `x:Code` donde el elemento demarca un intervalo en el que el marcado se debería interpretar como un contenido distinto del contenido secundario predeterminado.  En este caso, el tipo XAML de cada elemento de objeto comunica información sobre los tipos de argumento que, a su vez, usan los analizadores XAML para determinar a qué firma específica de método de generador del constructor intenta hacer referencia un uso de `x:Arguments`.  
  
 El parámetro `x:Arguments` de un elemento de objeto en construcción debe preceder a cualquier otro elemento de propiedad, contenido, texto interno o cadenas de inicialización del elemento de objeto.  Los elementos de objeto incluidos en `x:Arguments` pueden incluir atributos y cadenas de inicialización, tal y como se permite por ese tipo XAML y su constructor de respaldo o método de generador.  Para el objeto o los argumentos, puede especificar tipos XAML personalizados o tipos XAML que, de lo contrario, se encuentren fuera del espacio de nombres XAML predeterminado haciendo referencia a asignaciones de prefijo establecidas.  
  
 Los procesadores XAML usan las siguientes directrices para determinar cómo deben usarse los argumentos especificados en `x:Arguments` para construir un objeto.  Si se especifica `x:FactoryMethod`, la información se compara con el `x:FactoryMethod` especificado \(observe que el valor de `x:FactoryMethod` es el nombre del método y el método con nombre puede tener sobrecargas.  Si no se especifica `x:FactoryMethod`, la información se compara con el conjunto de todas las sobrecargas del constructor público del objeto.  A continuación, la lógica de procesamiento de XAML compara el número de parámetros y selecciona la sobrecarga coincidente.  Si hay más de una coincidencia, el procesador XAML debe comparar los tipos de parámetros en función de los tipos XAML de los elementos de objeto especificados.  Si hay todavía más de una coincidencia, el comportamiento del procesador XAML no está definido.  Si se especifica `x:FactoryMethod` pero el método no se puede resolver, un procesador XAML debe producir una excepción.  
  
 Un uso de atributos XAML `<x:Arguments>string</x:Arguments>` es técnicamente posible.  Sin embargo, no proporciona ninguna funcionalidad aparte de lo que puede hacerse de otra manera a través del texto y los convertidores de tipos de inicialización, y el uso de esta sintaxis no es la intención del diseño de las características del método generador 2009 de XAML.  
  
## Ejemplos  
 En el ejemplo siguiente se muestra una firma de constructor no predeterminado y, a continuación, el uso de XAML de `x:Arguments` que obtiene acceso a esa firma.  
  
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
  
```  
<my:Food>  
    <x:Arguments>  
        <x:String>Apple</x:String>  
        <x:Int32>150</x:Int32>  
    </x:Arguments>  
</my:Food>  
```  
  
 En el ejemplo siguiente se muestra una firma de método del generador de destino y, a continuación, el uso de XAML de `x:Arguments` que obtiene acceso a esa firma.  
  
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
  
```  
<my:Food x:FactoryMethod="TryLookupFood">  
    <x:Arguments>  
        <x:String>Apple</x:String>  
    </x:Arguments>  
</my:Food>  
```  
  
## Vea también  
 [Defining Custom Types for Use with .NET Framework XAML Services](../../../docs/framework/xaml-services/defining-custom-types-for-use-with-net-framework-xaml-services.md)   
 [Información general sobre XAML \(WPF\)](../../../ocs/framework/wpf/advanced/xaml-overview-wpf.md)