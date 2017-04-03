---
title: "Cómo: Obtener acceso a argumentos de la línea de comandos mediante foreach (Guía de programación de C#) | Microsoft Docs"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- command-line arguments [C#]
ms.assetid: 89c3e335-3f5b-4e24-8c5a-b8036561fe8a
caps.latest.revision: 15
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
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 2f0e3bce88beafd45a21773a7b26ffb2bb41215d
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-access-command-line-arguments-using-foreach-c-programming-guide"></a>Cómo: Obtener acceso a argumentos de la línea de comandos utilizando Foreach (Guía de programación de C#)
Otro enfoque para recorrer en iteración la matriz es usar la instrucción [foreach](../../../csharp/language-reference/keywords/foreach-in.md) como se muestra en este ejemplo. La instrucción `foreach` se puede usar para recorrer en iteración una matriz, una clase de colección de .NET Framework o cualquier clase o struct que implemente la interfaz <xref:System.Collections.IEnumerable>.  
  
> [!NOTE]
>  Si se ejecuta una aplicación en Visual Studio, se pueden especificar argumentos de la línea de comandos en la [Página Depuración, Diseñador de proyectos](https://docs.microsoft.com/visualstudio/ide/reference/debug-page-project-designer).  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se muestra cómo imprimir los argumentos de la línea de comandos con `foreach`.  
  
 [!code-cs[csProgGuideMain#10](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/how-to-access-command-line-arguments-using-foreach_1.cs)]  
  
 [!code-cs[csProgGuideMain#11](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/how-to-access-command-line-arguments-using-foreach_2.cs)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Array>   
 <xref:System.Collections>   
 [Compilar la línea de comandos con csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [foreach, in](../../../csharp/language-reference/keywords/foreach-in.md)   
 [Main() y argumentos de línea de comandos](../../../csharp/programming-guide/main-and-command-args/index.md)   
 [Cómo: Mostrar argumentos de la línea de comandos](../../../csharp/programming-guide/main-and-command-args/how-to-display-command-line-arguments.md)   
 [Valores devueltos de Main()](../../../csharp/programming-guide/main-and-command-args/main-return-values.md)
