---
title: protected (Referencia de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- protected
- protected_CSharpKeyword
helpviewer_keywords:
- protected keyword [C#]
ms.assetid: 05ce3794-6675-4025-bddb-eaaa0ec22892
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 18278ed28f899d9030d6056eca9bbe83ebec04c4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="protected-c-reference"></a>protected (Referencia de C#)
La palabra clave `protected` es un modificador de acceso de miembro. 

 > Esta página cubre `protected` acceso. El `protected` palabra clave es también parte de la [ `protected internal` ](./protected-internal.md) y [ `private protected` ](./private-protected.md) los modificadores de acceso. 

Un miembro protegido es accesible dentro de su clase y por parte de instancias de clase derivadas. 

Para obtener una comparación de `protected` con los demás modificadores de acceso, vea [Niveles de accesibilidad](../../../csharp/language-reference/keywords/accessibility-levels.md). 
  
## <a name="example"></a>Ejemplo  
 Un miembro protegido de una clase base es accesible en una clase derivada únicamente si el acceso se produce a través del tipo de clase derivada. Por ejemplo, vea el siguiente segmento de código:  
  
 [!code-csharp[csrefKeywordsModifiers#11](../../../csharp/language-reference/keywords/codesnippet/CSharp/protected_1.cs)]  
  
 La instrucción `a.x = 10` genera un error porque se ha creado en el método estático Main y no en una instancia de clase B.  
  
 Los miembros de estructura no se pueden proteger porque la estructura no puede heredarse.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo, la clase `DerivedPoint` se deriva de `Point`. Por lo tanto, puede acceder a los miembros protegidos de la clase base directamente desde la clase derivada.  
  
 [!code-csharp[csrefKeywordsModifiers#12](../../../csharp/language-reference/keywords/codesnippet/CSharp/protected_2.cs)]  
  
 Si cambia los niveles de acceso de `x` y `y` a [private](../../../csharp/language-reference/keywords/private.md), el compilador genera los mensajes de error:  
  
 `'Point.y' is inaccessible due to its protection level.`  
  
 `'Point.x' is inaccessible due to its protection level.`  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Palabras clave de C#](../../../csharp/language-reference/keywords/index.md)  
 [Modificadores de acceso](../../../csharp/language-reference/keywords/access-modifiers.md)  
 [Niveles de accesibilidad](../../../csharp/language-reference/keywords/accessibility-levels.md)  
 [Modificadores](../../../csharp/language-reference/keywords/modifiers.md)  
 [public](../../../csharp/language-reference/keywords/public.md)  
 [private](../../../csharp/language-reference/keywords/private.md)  
 [internal](../../../csharp/language-reference/keywords/internal.md)  
 [Cuestiones de seguridad para palabras clave virtuales internas](https://msdn.microsoft.com/library/heyd8kky(v=vs.110))