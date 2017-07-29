---
title: "Propiedades (Guía de programación de C#)"
ms.date: 2017-03-10
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- cs.properties
dev_langs:
- CSharp
helpviewer_keywords:
- properties [C#]
- C# language, properties
ms.assetid: e295a8a2-b357-4ee7-a12e-385a44146fa8
caps.latest.revision: 38
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 127299a617cacee15f87964a12bb3877a2586204
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="properties-c-programming-guide"></a>Propiedades (Guía de programación de C#)

Una propiedad es un miembro que proporciona un mecanismo flexible para leer, escribir o calcular el valor de un campo privado. Las propiedades se pueden usar como si fueran miembros de datos públicos, pero en realidad son métodos especiales denominados *descriptores de acceso*. Esto permite acceder fácilmente a los datos a la vez que proporciona la seguridad y la flexibilidad de los métodos.  

## <a name="properties-overview"></a>Información general sobre propiedades  
  
- Las propiedades permiten que una clase exponga una manera pública de obtener y establecer valores, a la vez que se oculta el código de implementación o comprobación.  
  
- Para devolver el valor de la propiedad se usa un descriptor de acceso de propiedad [get](../../../csharp/language-reference/keywords/get.md), mientras que para asignar un nuevo valor se emplea un descriptor de acceso de propiedad [set](../../../csharp/language-reference/keywords/set.md). Estos descriptores de acceso pueden tener diferentes niveles de acceso. Para más información, vea [Restringir la accesibilidad del descriptor de acceso](../../../csharp/programming-guide/classes-and-structs/restricting-accessor-accessibility.md).  
  
- La palabra clave [value](../../../csharp/language-reference/keywords/value.md) se usa para definir el valor que va a asignar el descriptor de acceso `set`.  
- Las propiedades pueden ser *de lectura y escritura* (en ambos casos tienen un descriptor de acceso `get` y `set`), *de solo lectura* (tienen un descriptor de acceso `get`, pero no `set`) o *de solo escritura* (tienen un descriptor de acceso `set`, pero no `get`). Las propiedades de solo escritura son poco frecuentes y se suelen usar para restringir el acceso a datos confidenciales.

- Las propiedades simples que no necesitan ningún código de descriptor de acceso personalizado se pueden implementar como definiciones de cuerpos de expresión o como [propiedades implementadas automáticamente](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md).
 
## <a name="properties-with-backing-fields"></a>Propiedades con campos de respaldo

Un patrón básico para implementar una propiedad conlleva el uso de un campo de respaldo privado para establecer y recuperar el valor de la propiedad. El descriptor de acceso `get` devuelve el valor del campo privado y el descriptor de acceso `set` puede realizar alguna validación de datos antes de asignar un valor al campo privado. Ambos descriptores de acceso además pueden realizar algún cálculo o conversión en los datos antes de que se almacenen o se devuelvan.

En el ejemplo siguiente se muestra este patrón. En este ejemplo, la clase `TimePeriod` representa un intervalo de tiempo. Internamente, la clase almacena el intervalo de tiempo en segundos en un campo privado denominado `seconds`. Una propiedad de lectura y escritura denominada `Hours` permite al cliente especificar el intervalo de tiempo en horas. Los descriptores de acceso `get` y `set` realizan la conversión necesaria entre horas y segundos. Además, el descriptor de acceso `set` valida los datos e inicia una excepción @System.ArgumentOutOfRangeException si el número de horas no es válido. 
   
 [!code-cs[Properties#1](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/properties-1.cs)]  
  
## <a name="expression-body-definitions"></a>Definiciones de cuerpos de expresión  

 Los descriptores de acceso de propiedad suelen constar de instrucciones de una sola línea que simplemente asignan o devuelven el resultado de una expresión. Puede implementar estas propiedades como miembros con forma de expresión. Las definiciones de cuerpos de expresión constan del símbolo `=>` seguido de la expresión que se va a asignar a la propiedad o a recuperar de ella.

 A partir de C# 6, las propiedades de solo lectura pueden implementar el descriptor de acceso `get` como miembro con forma de expresión. En este caso, no se usan ni la palabra clave del descriptor de acceso `get` ni la palabra clave `return`. En el ejemplo siguiente se implementa la propiedad de solo lectura `Name` como miembro con forma de expresión.

 [!code-cs[Properties#2](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/properties-2.cs)]  

 A partir de C# 7, los descriptores de acceso `get` y `set` se pueden implementar como miembros con forma de expresión. En este caso, las palabras clave `get` y `set` deben estar presentes. En el ejemplo siguiente se muestra el uso de definiciones de cuerpos de expresión para ambos descriptores de acceso. Observe que no se usa la palabra clave `return` con el descriptor de acceso `get`.
 
  [!code-cs[Properties#3](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/properties-3.cs)]  

## <a name="auto-implemented-properties"></a>Propiedades implementadas automáticamente

En algunos casos, los descriptores de acceso de propiedad `get` y `set` simplemente asignan un valor a un campo de respaldo o recuperan un valor de él sin incluir ninguna lógica adicional. Mediante las propiedades implementadas automáticamente, puede simplificar el código y conseguir que el compilador de C# le proporcione el campo de respaldo de forma transparente. 

Si una propiedad tiene un descriptor de acceso `get` y `set`, ambos deben ser implementados automáticamente. Una propiedad implementada automáticamente se define mediante las palabras clave `get` y `set` sin proporcionar ninguna implementación. El ejemplo siguiente repite el anterior, salvo que `Name` y `Price` son propiedades implementadas automáticamente. Observe que en el ejemplo también se quita el constructor parametrizado, por lo que los objetos `SaleItem` ahora se inicializan con una llamada al constructor predeterminado y un [inicializador de objeto](object-and-collection-initializers.md).

  [!code-cs[Properties#4](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/properties-4.cs)]  

## <a name="related-sections"></a>Secciones relacionadas  
  
-   [Utilizar propiedades](../../../csharp/programming-guide/classes-and-structs/using-properties.md)  
  
-   [Propiedades de interfaz](../../../csharp/programming-guide/classes-and-structs/interface-properties.md)  
  
-   [Comparación entre propiedades e indizadores](../../../csharp/programming-guide/indexers/comparison-between-properties-and-indexers.md)  
  
-   [Restringir la accesibilidad del descriptor de acceso](../../../csharp/programming-guide/classes-and-structs/restricting-accessor-accessibility.md)  
  
-   [Propiedades autoimplementadas](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md)  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Utilizar propiedades](../../../csharp/programming-guide/classes-and-structs/using-properties.md)   
 [Indizadores](../../../csharp/programming-guide/indexers/index.md)   
 [get (palabra clave)](../../../csharp/language-reference/keywords/get.md)    
 [set (palabra clave)](../../../csharp/language-reference/keywords/set.md)    

