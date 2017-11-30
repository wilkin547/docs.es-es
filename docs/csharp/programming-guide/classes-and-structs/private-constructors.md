---
title: "Constructores privados (Guía de programación de C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- C# language, private constructors
- private constructors [C#]
ms.assetid: 29eeaa7d-8d81-453c-94b9-0e2800172621
caps.latest.revision: "19"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 79660cd4545fff43ac3dd6ab797fd20c0f882e05
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="private-constructors-c-programming-guide"></a>Constructores privados (Guía de programación de C#)
Un constructor privado es un constructor de instancia especial. Se usa generalmente en clases que contienen solo miembros estáticos. Si una clase tiene uno o más constructores privados y ningún constructor público, el resto de clases (excepto las anidadas) no podrán crear instancias de esta clase. Por ejemplo:  
  
 [!code-csharp[csProgGuideObjects#11](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/private-constructors_1.cs)]  
  
 La declaración de un constructor vacío evita la generación automática de un constructor predeterminado. Observe que si no usa un modificador de acceso en el constructor, este será privado de manera predeterminada. En cambio, normalmente se usa el modificador [private](../../../csharp/language-reference/keywords/private.md) de manera explícita para aclarar que no es posible crear una instancia de la clase.  
  
 Los constructores privados se usan para evitar la creación de instancias de una clase cuando no hay campos o métodos de instancia, por ejemplo, la clase <xref:System.Math>, o cuando se llama a un método para obtener una instancia de una clase. Si todos los métodos de la clase son estáticos, considere convertir la clase completa en estática. Para obtener más información, vea [Clases estáticas y sus miembros](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).  
  
## <a name="example"></a>Ejemplo  
 El siguiente es un ejemplo de clase que usa un constructor privado.  
  
 [!code-csharp[csProgGuideObjects#12](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/private-constructors_2.cs)]  
  
 Observe que si quita el comentario de la siguiente instrucción del ejemplo, se producirá un error porque el constructor es inaccesible debido a su nivel de protección:  
  
 [!code-csharp[csProgGuideObjects#13](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/private-constructors_3.cs)]  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Clases y structs](../../../csharp/programming-guide/classes-and-structs/index.md)  
 [Constructores](../../../csharp/programming-guide/classes-and-structs/constructors.md)  
 [Finalizadores](../../../csharp/programming-guide/classes-and-structs/destructors.md)  
 [private](../../../csharp/language-reference/keywords/private.md)  
 [public](../../../csharp/language-reference/keywords/public.md)
