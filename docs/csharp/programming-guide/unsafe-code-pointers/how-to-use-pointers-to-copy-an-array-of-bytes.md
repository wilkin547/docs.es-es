---
title: "Cómo: Utilizar punteros para copiar una matriz de bytes (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- byte arrays [C#]
- arrays [C#], byte
- pointers [C#], to copy bytes
ms.assetid: ec16fbb4-a24e-45f5-a763-9499d3fabe0a
caps.latest.revision: 21
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
ms.openlocfilehash: 808a74f75e4dcbcec47735d98063138e2c7456e5
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-use-pointers-to-copy-an-array-of-bytes--c-programming-guide"></a>Cómo: Utilizar punteros para copiar una matriz de bytes (Guía de programación de C#)
En el ejemplo siguiente se usan punteros para copiar bytes de una matriz a otra.  
  
 En este ejemplo se usa la palabra clave [unsafe](../../../csharp/language-reference/keywords/unsafe.md), que permite el uso de punteros en el método `Copy`. La instrucción [fixed](../../../csharp/language-reference/keywords/fixed-statement.md) se usa para declarar punteros a las matrices de origen y destino. Esto *ancla* la ubicación de las matrices de origen y destino en memoria, para que no puedan ser desplazadas por la recolección de elementos no utilizados. Estos bloques de memoria para las matrices se desanclan cuando finaliza el bloque `fixed`. Dado que el método `Copy` en este ejemplo usa la palabra clave `unsafe`, se debe compilar con la opción del compilador **/unsafe**. Para establecer la opción en Visual Studio, haga clic con el botón derecho en el nombre del proyecto y, después, haga clic en **Propiedades**. En la pestaña **Compilar**, seleccione **Permitir código no seguro**.  
  
## <a name="example"></a>Ejemplo  
 [!code-cs[csProgGuidePointers#3](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-use-pointers-to-copy-an-array-of-bytes_1.cs)]  
  
 [!code-cs[csProgGuidePointers#18](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-use-pointers-to-copy-an-array-of-bytes_2.cs)]  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Código no seguro y punteros](../../../csharp/programming-guide/unsafe-code-pointers/index.md)   
 [/unsafe (Opciones del compilador de C#)](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md)   
 [Recolección de elementos no utilizados](../../../standard/garbage-collection/index.md)

