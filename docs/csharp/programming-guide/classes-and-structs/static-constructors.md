---
title: "Constructores estáticos (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- static constructors [C#]
- constructors [C#], static
ms.assetid: 151ec95e-3c4d-4ed7-885d-95b7a3be2e7d
caps.latest.revision: 23
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
ms.openlocfilehash: 73df76c61f393bf5fe09af66935acfbac4b5663f
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="static-constructors-c-programming-guide"></a>Constructores estáticos (Guía de programación de C#)
Un constructor estático se usa para inicializar cualquier dato [estático](../../../csharp/language-reference/keywords/static.md) o realizar una acción determinada que solo debe realizarse una vez. Es llamado automáticamente antes de crear la primera instancia o de hacer referencia a cualquier miembro estático.  
  
 [!code-cs[csProgGuideObjects#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/static-constructors_1.cs)]  
  
 Los constructores estáticos tienen las propiedades siguientes:  
  
-   Un constructor estático no permite modificadores de acceso ni tiene parámetros.  
  
-   Se le llama automáticamente para inicializar la [clase](../../../csharp/language-reference/keywords/class.md) antes de crear la primera instancia o de hacer referencia a cualquier miembro estático.  
  
-   Un constructor estático no puede ser llamado directamente.  
  
-   El usuario no puede controlar cuándo se ejecuta el constructor estático en el programa.  
  
-   Los constructores estáticos se usan normalmente cuando la clase hace uso de un archivo de registro y el constructor escribe entradas en dicho archivo.  
  
-   Los constructores estáticos también son útiles al crear clases contenedoras para código no administrado, cuando el constructor puede llamar al método `LoadLibrary`.  
  
-   Si un constructor estático inicia una excepción, el motor en tiempo de ejecución no lo invocará una segunda vez y el tipo seguirá sin inicializar durante el período de duración del dominio de aplicación donde se ejecuta el programa.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo, la clase `Bus` tiene un constructor estático. Cuando se crea la primera instancia de `Bus` (`bus1`), se invoca el constructor estático para inicializar la clase. En el resultado del ejemplo, se comprueba que el constructor estático se ejecuta solo una vez, incluso si se crean dos instancias de `Bus`, y que se ejecuta antes de que se ejecute el constructor de instancia.  
  
 [!code-cs[csProgGuideObjects#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/static-constructors_2.cs)]  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Clases y estructuras](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [Constructors](../../../csharp/programming-guide/classes-and-structs/constructors.md)  (Constructores [Guía de programación de C#])  
 [Clases estáticas y sus miembros](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)   
 [Finalizadores](../../../csharp/programming-guide/classes-and-structs/destructors.md)

