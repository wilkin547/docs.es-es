---
title: protected (Referencia de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- protected
- protected_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- protected keyword [C#]
ms.assetid: 05ce3794-6675-4025-bddb-eaaa0ec22892
caps.latest.revision: 20
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
ms.openlocfilehash: c3d24389f66edec313d4f5238b0aee02518e33b7
ms.contentlocale: es-es
ms.lasthandoff: 09/25/2017

---
# <a name="protected-c-reference"></a>protected (Referencia de C#)
La palabra clave `protected` es un modificador de acceso de miembro. Un miembro protegido es accesible dentro de su clase y por parte de instancias de clase derivadas. Para obtener una comparación de `protected` con los demás modificadores de acceso, vea [Niveles de accesibilidad](../../../csharp/language-reference/keywords/accessibility-levels.md).  
  
## <a name="example"></a>Ejemplo  
 Un miembro protegido de una clase base es accesible en una clase derivada únicamente si el acceso se produce a través del tipo de clase derivada. Por ejemplo, vea el siguiente segmento de código:  
  
 [!code-cs[csrefKeywordsModifiers#11](../../../csharp/language-reference/keywords/codesnippet/CSharp/protected_1.cs)]  
  
 La instrucción `a.x = 10` genera un error porque se ha creado en el método estático Main y no en una instancia de clase B.  
  
 Los miembros de estructura no se pueden proteger porque la estructura no puede heredarse.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo, la clase `DerivedPoint` se deriva de `Point`. Por lo tanto, puede acceder a los miembros protegidos de la clase base directamente desde la clase derivada.  
  
 [!code-cs[csrefKeywordsModifiers#12](../../../csharp/language-reference/keywords/codesnippet/CSharp/protected_2.cs)]  
  
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

