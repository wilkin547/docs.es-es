---
title: "Usar structs (Guía de programación de C#) | Microsoft Docs"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- structs [C#], using
ms.assetid: cea4a459-9eb9-442b-8d08-490e0797ba38
caps.latest.revision: 28
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 8cb5fa79de38294add5cebdd38537636591de126
ms.lasthandoff: 03/13/2017

---
# <a name="using-structs-c-programming-guide"></a>Usar structs (Guía de programación de C#)
El tipo `struct` resulta adecuado para representar objetos pequeños como `Point`, `Rectangle`y `Color`. Aunque es igual de válido representar un punto como un elemento [class](../../../csharp/language-reference/keywords/class.md) con [Propiedades implementadas automáticamente](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md), seguramente un [struct](../../../csharp/language-reference/keywords/struct.md) sea más eficaz en algunos escenarios. Por ejemplo, si declara una matriz de 1000 objetos `Point` , se asignará más memoria para hacer referencia a cada objeto y, en este caso, un struct sería menos costoso. Como [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] contiene un objeto denominado <xref:System.Drawing.Point>, el struct de este ejemplo se denomina "CoOrds".  
  
 [!code-cs[csProgGuideObjects#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_1.cs)]  
  
 Definir un constructor (sin parámetros) predeterminado para un struct es un error, como también lo es inicializar un campo de instancia en el cuerpo de un struct. Los miembros del struct solo se pueden inicializar mediante un constructor con parámetros, o bien teniendo acceso individualmente a cada miembro una vez declarado el struct. Los miembros privados o inaccesibles por cualquier otro motivo solo se pueden inicializar en un constructor.  
  
 Cuando se crea un objeto struct con el operador [new](../../../csharp/language-reference/keywords/new.md), se crea el objeto y se llama al constructor apropiado. A diferencia de las clases, se pueden crear instancias de structs sin usar el operador `new` . En tal caso, no hay ninguna llamada de constructor, con lo cual la asignación es más eficaz. Pero los campos seguirán sin asignar y el objeto no se podrá usar hasta que todos los campos se inicialicen.  
  
 Cuando un struct contiene un tipo de referencia como miembro, se debe invocar explícitamente el constructor predeterminado de ese miembro, ya que, de lo contrario, el miembro seguirá sin asignar y el struct no se podrá usar (esto genera el error del compilador CS0171).  
  
 En los structs no existe el concepto de herencia que sí hay en las clases. Así, un struct no puede heredar de otra clase o de otro struct, como tampoco puede ser la base de una clase. Pero los structs sí heredan de la clase base <xref:System.Object>. Un struct puede implementar interfaces y lo hace exactamente igual que las clases.  
  
 No se puede declarar una clase mediante la palabra clave `struct`. En C#, las clases y los structs son distintos semánticamente. Un struct es un tipo de valor, mientras que una clase es un tipo de referencia. Para obtener más información, vea [Tipos de valor](../../../csharp/language-reference/keywords/value-types.md).  
  
 A menos que necesite una semántica de tipo de referencia, es probable que el sistema controle una clase pequeña más eficazmente si se declara como un struct.  
  
## <a name="example-1"></a>Ejemplo 1  
  
### <a name="description"></a>Descripción  
 En este ejemplo se muestra la inicialización de `struct` mediante constructores predeterminados y constructores con parámetros.  
  
### <a name="code"></a>Código  
 [!code-cs[csProgGuideObjects#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_1.cs)]  
  
 [!code-cs[csProgGuideObjects#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_2.cs)]  
  
## <a name="example-2"></a>Ejemplo 2  
  
### <a name="description"></a>Descripción  
 En este ejemplo se muestra una característica única de los structs. Se crea un objeto CoOrds sin usar el operador `new` . Si reemplaza la palabra `struct` por la palabra `class`, el programa no se compilará.  
  
### <a name="code"></a>Código  
 [!code-cs[csProgGuideObjects#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_1.cs)]  
  
 [!code-cs[csProgGuideObjects#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_3.cs)]  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Clases y estructuras](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [Structs](../../../csharp/programming-guide/classes-and-structs/structs.md)
