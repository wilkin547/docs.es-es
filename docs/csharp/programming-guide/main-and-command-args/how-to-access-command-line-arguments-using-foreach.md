---
title: 'Cómo: Obtener acceso a argumentos de la línea de comandos utilizando Foreach (Guía de programación de C#)'
ms.date: 07/20/2015
helpviewer_keywords:
- command-line arguments [C#]
ms.assetid: 89c3e335-3f5b-4e24-8c5a-b8036561fe8a
ms.openlocfilehash: 2f1723efd4056539e12605bc1a4229f94bc9e055
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-access-command-line-arguments-using-foreach-c-programming-guide"></a>Cómo: Obtener acceso a argumentos de la línea de comandos utilizando Foreach (Guía de programación de C#)
Otro enfoque para recorrer en iteración la matriz es usar la instrucción [foreach](../../../csharp/language-reference/keywords/foreach-in.md) como se muestra en este ejemplo. La instrucción `foreach` se puede utilizar para recorrer en iteración una matriz, una clase de colección de .NET Framework o cualquier clase o struct que implemente la interfaz <xref:System.Collections.IEnumerable>.  
  
> [!NOTE]
>  Al ejecutar una aplicación en Visual Studio, puede especificar argumentos de la línea de comandos en la [Página Depuración, Diseñador de proyectos](/visualstudio/ide/reference/debug-page-project-designer).  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se muestra cómo imprimir los argumentos de la línea de comandos con `foreach`.  
  
 [!code-csharp[csProgGuideMain#10](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/how-to-access-command-line-arguments-using-foreach_1.cs)]  
  
 [!code-csharp[csProgGuideMain#11](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/how-to-access-command-line-arguments-using-foreach_2.cs)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Array>  
 <xref:System.Collections>  
 [Compilar la línea de comandos con csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [foreach, in](../../../csharp/language-reference/keywords/foreach-in.md)  
 [Main() y argumentos de la línea de comandos](../../../csharp/programming-guide/main-and-command-args/index.md)  
 [Cómo: Mostrar argumentos de la línea de comandos](../../../csharp/programming-guide/main-and-command-args/how-to-display-command-line-arguments.md)  
 [Valores devueltos de Main()](../../../csharp/programming-guide/main-and-command-args/main-return-values.md)
