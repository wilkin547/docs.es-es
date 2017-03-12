---
title: "Propiedades (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "cs.properties"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "lenguaje C#, propiedades"
  - "propiedades [C#]"
ms.assetid: e295a8a2-b357-4ee7-a12e-385a44146fa8
caps.latest.revision: 38
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 38
---
# Propiedades (Gu&#237;a de programaci&#243;n de C#)
Una propiedad es un miembro que proporciona un mecanismo flexible para leer, escribir o calcular el valor de un campo privado.  Se pueden usar las propiedades como si fueran miembros de datos públicos, pero en realidad son métodos especiales denominados *descriptores de acceso*.  Esto permite acceder fácilmente a los datos a la vez que proporciona la seguridad y la flexibilidad de los métodos.  
  
 En este ejemplo, la clase `TimePeriod` almacena un período de tiempo.  Internamente, la clase almacena el tiempo en segundos, pero una propiedad denominada `Hours` permite a un cliente especificar el tiempo en horas.  Los descriptores de acceso para la propiedad `Hours` realizan la conversión entre horas y segundos.  
  
## Ejemplo  
 [!code-cs[csProgGuideProperties#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/properties_1.cs)]  
  
## Definiciones de cuerpos de expresión  
 Es habitual tener propiedades que simplemente devuelvan de inmediato el resultado de una expresión.  Hay un acceso directo de sintaxis para definir estas propiedades mediante `=>`:  
  
```c#  
public string Name => First + " " + Last;   
```  
  
 La propiedad debe ser de solo lectura, y no se utiliza la palabra clave de descriptor de acceso `get`.  
  
## Información general sobre propiedades  
  
-   Las propiedades permiten que una clase exponga una manera pública de obtener y establecer valores, a la vez que se oculta el código de implementación o comprobación.  
  
-   Se utiliza un descriptor de acceso de propiedad [get](../../../csharp/language-reference/keywords/get.md) para devolver el valor de propiedad y un descriptor [set](../../../csharp/language-reference/keywords/set.md) para asignarle un nuevo valor.  Estos descriptores de acceso pueden tener diferentes niveles de acceso.  Para más información, vea [Restringir la accesibilidad del descriptor de acceso](../../../csharp/programming-guide/classes-and-structs/restricting-accessor-accessibility.md).  
  
-   La palabra clave [value](../../../csharp/language-reference/keywords/value.md) se utiliza para definir el valor asignado por el descriptor de acceso `set`.  
  
-   Las propiedades que no implementan un descriptor de acceso `set` son de solo lectura.  
  
-   Cuando se trate de propiedades sencillas que no requieran ningún código de descriptor de acceso personalizado, considere la posibilidad de utilizar propiedades implementadas automáticamente.  Para más información, vea [Propiedades autoimplementadas](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md).  
  
## Secciones relacionadas  
  
-   [Utilizar propiedades](../../../csharp/programming-guide/classes-and-structs/using-properties.md)  
  
-   [Propiedades de interfaz](../../../csharp/programming-guide/classes-and-structs/interface-properties.md)  
  
-   [Comparación entre propiedades e indizadores](../../../csharp/programming-guide/indexers/comparison-between-properties-and-indexers.md)  
  
-   [Restringir la accesibilidad del descriptor de acceso](../../../csharp/programming-guide/classes-and-structs/restricting-accessor-accessibility.md)  
  
-   [Propiedades autoimplementadas](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md)  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Utilizar propiedades](../../../csharp/programming-guide/classes-and-structs/using-properties.md)   
 [Indizadores](../../../csharp/programming-guide/indexers/index.md)