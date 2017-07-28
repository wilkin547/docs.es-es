---
title: "Diferencias entre plantillas de C++ y tipos genéricos de C# (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- generics [C#], vs. C++ templates
ms.assetid: 1da6beeb-d4a4-4da0-87b7-0cfbe04920b7
caps.latest.revision: 14
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
ms.openlocfilehash: 483d33531141127e083c5b75789f405427e46890
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="differences-between-c-templates-and-c-generics-c-programming-guide"></a>Diferencias entre plantillas de C++ y tipos genéricos de C# (Guía de programación de C#)
Los tipos genéricos de C# y las plantillas de C++ son dos características de lenguaje que ofrecen compatibilidad con tipos parametrizados. Pero existen muchas diferencias entre ambos. En el nivel de sintaxis, los tipos genéricos de C# resultan un enfoque más sencillo que los tipos parametrizados sin la complejidad de las plantillas de C++. Además, C# no intenta ofrecer toda la funcionalidad que ofrecen las plantillas de C++. En el nivel de implementación, la principal diferencia es que las sustituciones de tipo genérico de C# se realizan en tiempo de ejecución y, por tanto, se conserva la información de tipo genérico para los objetos con instancias. Para obtener más información, vea [Generics in the Run Time](../../../csharp/programming-guide/generics/generics-in-the-run-time.md) (Genéricos en el tiempo de ejecución).  
  
 Estas son las principales diferencias entre plantillas de C++ y tipos genéricos de C#:  
  
-   Los tipos genéricos de C# no ofrecen tanta flexibilidad como las plantillas de C++. Por ejemplo, no es posible llamar a operadores aritméticos en una clase de tipos genéricos de C#, aunque es posible llamar a operadores definidos por el usuario.  
  
-   C# no permite parámetros de plantilla sin tipo, como `template C<int i> {}`.  
  
-   C# no admite la especialización explícita; es decir, una implementación personalizada de una plantilla para un tipo específico.  
  
-   C# no admite la especialización parcial: una implementación personalizada de un subconjunto de los argumentos de tipo.  
  
-   C# no permite que el parámetro de tipo se use como clase base del tipo genérico.  
  
-   C# no permite que los parámetros de tipo tengan tipos predeterminados.  
  
-   En C#, un parámetro de tipo genérico no puede ser un tipo genérico, aunque se pueden usar tipos construidos como genéricos. C++ permite parámetros de plantilla.  
  
-   C++ permite código que podría no ser válido para todos los parámetros de tipo en la plantilla, que luego busca el tipo específico que se usa como parámetro de tipo. C# requiere que el código de una clase se escriba de manera que funcione con cualquier tipo que cumpla las restricciones. Por ejemplo, en C++ es posible escribir una función que use los operadores aritméticos `+` y `-` en objetos del parámetro de tipo, lo que producirá un error en el momento de creación de instancias de la plantilla con un tipo que no admita estos operadores. C# no permite esto; las únicas construcciones de lenguaje permitidas son las que se pueden deducir de las restricciones.  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Introducción a los genéricos](../../../csharp/programming-guide/generics/introduction-to-generics.md)   
 [Templates](/cpp/cpp/templates-cpp) (Plantillas [C++])

