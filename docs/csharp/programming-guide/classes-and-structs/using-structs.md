---
title: "Utilizar estructuras (Guía de programación de C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords: structs [C#], using
ms.assetid: cea4a459-9eb9-442b-8d08-490e0797ba38
caps.latest.revision: "28"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 94181c42ce913dc76c9a074e4bcbb8240764c896
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="using-structs-c-programming-guide"></a>Utilizar estructuras (Guía de programación de C#)
El tipo `struct` resulta adecuado para representar objetos pequeños como `Point`, `Rectangle`y `Color`. Aunque es igual de válido representar un punto como un elemento [class](../../../csharp/language-reference/keywords/class.md) con [Propiedades autoimplementadas](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md), seguramente un [struct](../../../csharp/language-reference/keywords/struct.md) sea más eficaz en algunos escenarios. Por ejemplo, si declara una matriz de 1000 objetos `Point` , se asignará más memoria para hacer referencia a cada objeto y, en este caso, un struct sería menos costoso. Como [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] contiene un objeto denominado <xref:System.Drawing.Point>, denominaremos el struct de este ejemplo "CoOrds".  
  
 [!code-csharp[csProgGuideObjects#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_1.cs)]  
  
 Definir un constructor (sin parámetros) predeterminado para un struct es un error, como también lo es inicializar un campo de instancia en el cuerpo de un struct. Puede inicializar los miembros de struct accesible desde el exterior solo mediante un constructor parametrizado, implícito, constructor predeterminado, un [inicializador de objeto](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md), o mediante el acceso a los miembros individualmente una vez declarado el struct. Los miembros privados o inaccesibles requieren el uso de constructores exclusivamente.
  
 Cuando se crea un objeto de struct mediante el [nueva](../../../csharp/language-reference/keywords/new.md) (operador), se crea y se llama al constructor adecuado según la [firma del constructor](../../../csharp/programming-guide/classes-and-structs/constructors.md#constructor-syntax). A diferencia de las clases, se pueden crear instancias de structs sin usar el operador `new` . En tal caso, no hay ninguna llamada de constructor, con lo cual la asignación es más eficaz. Pero los campos seguirán sin asignar y el objeto no se podrá usar hasta que todos los campos se inicialicen. Esto incluye la incapacidad para obtener o establecer los valores a través de las propiedades implementadas automáticamente.
 
 Si crea una instancia de un objeto de struct mediante el valor predeterminado, el constructor sin parámetros, todos los miembros se asignan según sus [valores predeterminados](../../../csharp/programming-guide/statements-expressions-operators/default-value-expressions.md).
  
 Al escribir un constructor con parámetros para un struct, debe inicializar explícitamente todos los miembros; en caso contrario, uno o más miembros permanecen sin asignar y no se puede usar la estructura, que produce el error del compilador CS0171.  
  
 En los structs no existe el concepto de herencia que sí hay en las clases. Así, un struct no puede heredar de otra clase o de otro struct, como tampoco puede ser la base de una clase. Pero los structs sí heredan de la clase base <xref:System.Object>. Un struct puede implementar interfaces y lo hace exactamente igual que las clases.  
  
 No se puede declarar una clase mediante la palabra clave `struct`. En C#, las clases y los structs son distintos semánticamente. Un struct es un tipo de valor, mientras que una clase es un tipo de referencia. Para obtener más información, vea [Tipos de valor](../../../csharp/language-reference/keywords/value-types.md).  
  
 A menos que necesite una semántica de tipo de referencia, es probable que el sistema controle una clase pequeña más eficazmente si se declara como un struct.  
  
## <a name="example-1"></a>Ejemplo 1  
  
### <a name="description"></a>Descripción  
 En este ejemplo se muestra la inicialización de `struct` mediante constructores predeterminados y constructores con parámetros.  
  
### <a name="code"></a>Código  
 [!code-csharp[csProgGuideObjects#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_1.cs)]  
  
 [!code-csharp[csProgGuideObjects#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_2.cs)]  
  
## <a name="example-2"></a>Ejemplo 2  
  
### <a name="description"></a>Descripción  
 En este ejemplo se muestra una característica única de los structs. Se crea un objeto CoOrds sin usar el operador `new` . Si reemplaza la palabra `struct` por la palabra `class`, el programa no se compilará.  
  
### <a name="code"></a>Código  
 [!code-csharp[csProgGuideObjects#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_1.cs)]  
  
 [!code-csharp[csProgGuideObjects#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_3.cs)]  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Clases y structs](../../../csharp/programming-guide/classes-and-structs/index.md)  
 [Estructuras](../../../csharp/programming-guide/classes-and-structs/structs.md)
