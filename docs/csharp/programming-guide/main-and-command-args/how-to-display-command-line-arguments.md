---
title: "Cómo: Mostrar argumentos de la línea de comandos (Guía de programación de C#) | Microsoft Docs"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- command-line arguments [C#], displaying
ms.assetid: b8479f2d-9e05-4d38-82da-2e61246e5437
caps.latest.revision: 19
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
ms.openlocfilehash: e46860ecc2f5062abb440a764443ecee19c5153d
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-display-command-line-arguments-c-programming-guide"></a>Cómo: Mostrar argumentos de la línea de comandos (Guía de programación de C#)
A los argumentos proporcionados a un archivo ejecutable en la línea de comandos se puede tener acceso a través de un parámetro opcional de `Main`. Los argumentos se proporcionan en forma de una matriz de cadenas. Cada elemento de la matriz contiene un argumento. Se quita el espacio en blanco entre los argumentos. Por ejemplo, considere estas invocaciones de línea de comandos de un ejecutable ficticio:  
  
|Entrada en la línea de comandos|Matriz de cadenas que se pasa a Main|  
|----------------------------|-------------------------------------|  
|**executable.exe a b c**|"a"<br /><br /> "b"<br /><br /> "c"|  
|**executable.exe one two**|"one"<br /><br /> "two"|  
|**executable.exe "one two" three**|"one two"<br /><br /> "three"|  
  
> [!NOTE]
>  Si se ejecuta una aplicación en Visual Studio, se pueden especificar argumentos de línea de comandos en la [Página Depuración, Diseñador de proyectos](https://docs.microsoft.com/visualstudio/ide/reference/debug-page-project-designer).  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se muestran los argumentos de línea de comandos pasados a una aplicación de línea de comandos. La salida que se muestra corresponde a la primera entrada de la tabla anterior.  
  
 [!code-cs[csProgGuideMain#9](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/how-to-display-command-line-arguments_1.cs)]  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Compilar la línea de comandos con csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)   
 [Main() y argumentos de línea de comandos](../../../csharp/programming-guide/main-and-command-args/index.md)   
 [Cómo: Obtener acceso a argumentos de la línea de comandos mediante foreach](../../../csharp/programming-guide/main-and-command-args/how-to-access-command-line-arguments-using-foreach.md)   
 [Valores devueltos de Main()](../../../csharp/programming-guide/main-and-command-args/main-return-values.md)
