---
title: "Cómo: Utilizar punteros para copiar una matriz de bytes (Guía de programación de C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- byte arrays [C#]
- arrays [C#], byte
- pointers [C#], to copy bytes
ms.assetid: ec16fbb4-a24e-45f5-a763-9499d3fabe0a
caps.latest.revision: "21"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 375cab76063e4c77515d6b05b42f2d97ff3efc44
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-pointers-to-copy-an-array-of-bytes--c-programming-guide"></a>Cómo: Utilizar punteros para copiar una matriz de bytes (Guía de programación de C#)
En el ejemplo siguiente se usan punteros para copiar bytes de una matriz a otra.  
  
 En este ejemplo se usa la palabra clave [unsafe](../../../csharp/language-reference/keywords/unsafe.md), que permite el uso de punteros en el método `Copy`. La instrucción [fixed](../../../csharp/language-reference/keywords/fixed-statement.md) se usa para declarar punteros a las matrices de origen y destino. Esto *ancla* la ubicación de las matrices de origen y destino en memoria, para que no puedan ser desplazadas por la recolección de elementos no utilizados. Estos bloques de memoria para las matrices se desanclan cuando finaliza el bloque `fixed`. Dado que el método `Copy` en este ejemplo usa la palabra clave `unsafe`, se debe compilar con la opción del compilador **/unsafe**. Para establecer la opción en Visual Studio, haga clic con el botón derecho en el nombre del proyecto y, después, haga clic en **Propiedades**. En la pestaña **Compilar**, seleccione **Permitir código no seguro**.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[csProgGuidePointers#3](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-use-pointers-to-copy-an-array-of-bytes_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#18](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-use-pointers-to-copy-an-array-of-bytes_2.cs)]  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Código no seguro y punteros](../../../csharp/programming-guide/unsafe-code-pointers/index.md)  
 [/unsafe (Opciones del compilador de C#)](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md)  
 [Recolección de elementos no utilizados](../../../standard/garbage-collection/index.md)
