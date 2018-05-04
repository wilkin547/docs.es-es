---
title: 'Cómo: Inicializar objetos usando un inicializador de objeto (Guía de programación de C#)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- object initializers [C#], how to use
- objects [C#], initializing
ms.assetid: 4b75ebb2-2e29-43de-929c-d736a8f27ce6
caps.latest.revision: 20
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 8e9130983aabe991660ff4cca90b33609f86c158
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2018
---
# <a name="how-to-initialize-objects-by-using-an-object-initializer-c-programming-guide"></a>Cómo: Inicializar objetos usando un inicializador de objeto (Guía de programación de C#)
Puede usar inicializadores de objeto para inicializar objetos de tipo de una forma declarativa sin tener que invocar explícitamente un constructor para el tipo.  
  
 En los siguientes ejemplos se muestra cómo usar los inicializadores de objeto con objetos con nombre. El compilador procesa los inicializadores de objeto primero obteniendo acceso al constructor de instancia predeterminado y después procesando las inicializaciones de miembro. Por lo tanto, si el constructor predeterminado se declara como `private` en la clase, se producirá un error en los inicializadores de objeto que requieren acceso público.  
  
 Debe usar un inicializador de objeto si va a definir un tipo anónimo. Para obtener más información, vea [Cómo: Devolver subconjuntos de propiedades de elementos en una consulta](../../../csharp/programming-guide/classes-and-structs/how-to-return-subsets-of-element-properties-in-a-query.md).  
  
## <a name="example"></a>Ejemplo  
 En el siguiente ejemplo se muestra cómo inicializar un nuevo tipo `StudentName` usando inicializadores de objeto.  
  
 [!code-csharp[csProgGuideLINQ#35](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-initialize-objects-by-using-an-object-initializer_1.cs)]  
  
## <a name="example"></a>Ejemplo  
 En el siguiente ejemplo se muestra cómo inicializar una colección de tipos `StudentName` usando un inicializador de colección. Tenga en cuenta que un inicializador de colección es una serie de inicializadores de objeto separados por comas.  
  
 [!code-csharp[csProgGuideLINQ#36](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-initialize-objects-by-using-an-object-initializer_2.cs)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para ejecutar este código, copie y pegue la clase en un proyecto de aplicación de consola de Visual C# creado en Visual Studio.  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Inicializadores de objeto y colección](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)
