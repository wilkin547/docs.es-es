---
title: 'Cómo: Declarar y usar propiedades de lectura y escritura (Guía de programación de C#)'
ms.date: 07/20/2015
helpviewer_keywords:
- get accessor [C#], declaring properties
- set accessor [C#]
- properties [C#], declaring
- read/write properties [C#]
- accessors [C#], declaring properties with
ms.assetid: a4962fef-af7e-4c4b-a929-4ae4d646ab8a
ms.openlocfilehash: 77db2841d6ef9af21d38736f39e6041699ca13d5
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/09/2018
ms.locfileid: "44180267"
---
# <a name="how-to-declare-and-use-read-write-properties-c-programming-guide"></a>Cómo: Declarar y usar propiedades de lectura y escritura (Guía de programación de C#)
Las propiedades proporcionan la comodidad de los miembros de datos públicos sin los riesgos que provienen del acceso sin comprobar, sin controlar y sin proteger a los datos de un objeto. Esto se consigue mediante los *descriptores de acceso*: métodos especiales que asignan y recuperan valores del miembro de datos subyacente. El descriptor de acceso [set](../../../csharp/language-reference/keywords/set.md) permite que los miembros de datos se asignen, y el descriptor de acceso [get](../../../csharp/language-reference/keywords/get.md) recupera los valores de los miembros de datos.  
  
 En este ejemplo se muestra una clase `Person` que tiene dos propiedades: `Name` (string) y `Age` (int). Ambas propiedades proporcionan descriptores de acceso `get` y `set`, de manera que se consideran propiedades de lectura y escritura.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[csProgGuideObjects#33](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_1.cs)]  
  
## <a name="robust-programming"></a>Programación sólida  
 En el ejemplo anterior, las propiedades `Name` y `Age` son [públicas](../../../csharp/language-reference/keywords/public.md) e incluyen un descriptor de acceso `get` y `set`. Esto permite que cualquier objeto lea y escriba estas propiedades. En cambio, a veces esto es conveniente para excluir uno de los descriptores de acceso. Omitir el descriptor de acceso `set`, por ejemplo, hace que la propiedad sea de solo lectura:  
  
 [!code-csharp[csProgGuideObjects#87](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_2.cs)]  
  
 De manera alternativa, puede exponer un descriptor de acceso públicamente pero hacer que el otro sea privado o esté protegido. Para obtener más información, vea [Accesibilidad del descriptor de acceso asimétrico](../../../csharp/programming-guide/classes-and-structs/restricting-accessor-accessibility.md).  
  
 Una vez que se declaren las propiedades, pueden usarse como si fueran campos de la clase. Esto permite una sintaxis muy natural cuando ambos obtienen y establecen el valor de una propiedad, como se muestra en las instrucciones siguientes:  
  
 [!code-csharp[csProgGuideObjects#35](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_3.cs)]  
  
 Tenga en cuenta que en un método `set` de la propiedad está disponible una variable `value` especial. Esta variable contiene el valor que el usuario ha especificado, por ejemplo:  
  
 [!code-csharp[csProgGuideObjects#36](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_4.cs)]  
  
 Tenga en cuenta la sintaxis pura para incrementar la propiedad `Age` en un objeto `Person`:  
  
 [!code-csharp[csProgGuideObjects#37](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_5.cs)]  
  
 Si los métodos `set` y `get` independientes se han usado para modelar las propiedades, el código equivalente puede tener este aspecto:  
  
```csharp  
person.SetAge(person.GetAge() + 1);   
```  
  
 El método `ToString` se invalida en este ejemplo:  
  
 [!code-csharp[csProgGuideObjects#38](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_6.cs)]  
  
 Tenga en cuenta que `ToString` no se usa explícitamente en el programa. Se invoca de manera predeterminada mediante las llamadas a `WriteLine`.  
  
## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
- [Propiedades](../../../csharp/programming-guide/classes-and-structs/properties.md)  
- [Clases y structs](../../../csharp/programming-guide/classes-and-structs/index.md)
