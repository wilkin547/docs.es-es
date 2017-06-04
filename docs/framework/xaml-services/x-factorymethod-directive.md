---
title: "x:FactoryMethod Directive | Microsoft Docs"
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
  - "XAML. x:FactoryMethod directive [XAML Services]"
  - "FactoryMethod directive in XAML [XAML Services]"
  - "x:FactoryMethod directive [XAML Services]"
ms.assetid: 829bcbdf-5318-4afb-9a03-c310e0d2f23d
caps.latest.revision: 8
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 8
---
# x:FactoryMethod Directive
Especifica un método distinto de un constructor que debería utilizar un procesador de XAML para inicializar un objeto después de resolver su tipo de respaldo.  
  
## Uso de atributos XAML, sin x:Arguments  
  
```  
<object x:FactoryMethod="methodname"...>  
  ...  
</object>  
```  
  
## Uso de atributos XAML, x:Arguments como elemento\(s\)  
  
```  
<object x:FactoryMethod="methodname"...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## Valores XAML  
  
|||  
|-|-|  
|`methodname`|El nombre del método de cadena de un método al que llaman los procesadores de XAML para inicializar la instancia especificada como `object`.  Vea la sección Comentarios.|  
|`oneOrMoreObjectElements`|Uno o varios elementos de objeto de objetos que especifican parámetros de método de generador.  El orden es importante, significa el orden en que los argumentos se deberían pasar al método del generador.|  
  
## Comentarios  
 Si `methodname` es un método de instancia, no se puede calificar.  
  
 Se admiten los métodos estáticos como métodos de generador.  Si `methodname` es un método estático, `methodname` se proporciona como una combinación de *nombreDeTipo*.*nombreDeMétodo*, donde el *nombreDeTipo* denomina la clase que define el método de generador estático.  *nombreDeTipo* puede ser calificado con un prefijo si hace referencia a un tipo en un xmlns asignado.  *nombreDeTipo* puede ser de un tipo diferente que `typeof(``object``)`.  
  
 El método de generador debe ser un método público declarado del tipo que respalda el elemento de objeto pertinente.  
  
 El método de generador debe devolver una instancia que es asignable al objeto pertinente.  Los métodos de generador nunca deberían devolver null.  
  
 `x:Arguments` funciona con un principio de mejor coincidencia para las firmas de métodos de generador.  La búsqueda evalúa primero el recuento de parámetros.  Si hay más de una posible coincidencia para un recuento de parámetros, se evalúa el tipo de parámetro y se determina la coincidencia mejor.  Si hay todavía ambigüedad después de esta fase de evaluación, el comportamiento del procesador de XAML es indefinido.  
  
 La sintaxis del elemento `x:FactoryMethod` no es una sintaxis de elemento de propiedad en el sentido típico, porque el marcado de la directiva no hace referencia al tipo del elemento del objeto que contiene.  Se espera que el uso del elemento sea menos común que el uso del atributo.  `x:Arguments` \(como atributo o elemento\) se puede utilizar junto con `x:FactoryMethod` como elemento, pero esto no se muestra específicamente en las secciones Uso.  
  
 `x:FactoryMethod` como elemento debe preceder a cualquier otro elemento de propiedad, debe preceder a cualquier `x:Arguments` también proporcionado como elemento y debe preceder a cualquier contenido, texto interno o texto de inicialización.  
  
## Vea también  
 [x:Arguments Directive](../../../docs/framework/xaml-services/x-arguments-directive.md)