---
title: volatile (Referencia de C#) | Microsoft Docs
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- volatile_CSharpKeyword
- volatile
dev_langs:
- CSharp
helpviewer_keywords:
- volatile keyword [C#]
ms.assetid: 78089bc7-7b38-4cfd-9e49-87ac036af009
caps.latest.revision: 29
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
ms.translationtype: Human Translation
ms.sourcegitcommit: fe32676f0e39ed109a68f39584cf41aec5f5ce90
ms.openlocfilehash: 801187b1fcc25a1eea1f40ec8ac4c67af42e5880
ms.contentlocale: es-es
ms.lasthandoff: 05/10/2017

---
# <a name="volatile-c-reference"></a>volatile (Referencia de C#)
La palabra clave `volatile` indica que un campo puede ser modificado por varios subprocesos que se ejecutan al mismo tiempo. Los campos declarados como `volatile` no están sujetos a optimizaciones del compilador que dan por hecho el acceso por parte de un único subproceso. Esto garantiza que el valor más actualizado esté presente en el campo en todo momento.  
  
 El modificador `volatile` normalmente se usa para un campo al que acceden varios subprocesos sin emplear la instrucción [lock](../../../csharp/language-reference/keywords/lock-statement.md) para serializar el acceso.  
  
 La palabra clave `volatile` se puede aplicar a campos de estos tipos:  
  
-   Tipos de referencia.  
  
-   Tipos de puntero (en un contexto no seguro). Observe que aunque el propio puntero puede ser volatile, no el objeto al que apunta. Es decir, no puede declarar un "puntero a volatile".  
  
-   Tipos como sbyte, byte, short, ushort, int, uint, char, float y bool.  
  
-   Un tipo enum con uno de los siguientes tipos base: byte, sbyte, short, ushort, int o uint.  
  
-   Parámetros de tipo genérico que se sabe que son tipos de referencia.  
  
-   <xref:System.IntPtr> y <xref:System.UIntPtr>.  
  
 La palabra clave volatile solo puede aplicarse a campos de una clase o estructura. Las variables locales no se pueden declarar como `volatile`.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo declarar una variable de campo pública como `volatile`.  
  
 [!code-cs[csrefKeywordsModifiers#24](../../../csharp/language-reference/keywords/codesnippet/CSharp/volatile_1.cs)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo crear un subproceso auxiliar o de trabajo y usarlo para realizar el procesamiento en paralelo con el del subproceso principal. Para obtener información general sobre multithreading, vea [Subprocesamiento](../../../standard/threading/index.md) y [Subprocesamiento](http://msdn.microsoft.com/library/552f6c68-dbdb-4327-ae36-32cf9063d88c).  
  
 [!code-cs[csProgGuideThreading#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/volatile_2.cs)]  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C#](../../../csharp/language-reference/keywords/index.md)   
 [Modificadores](../../../csharp/language-reference/keywords/modifiers.md)
