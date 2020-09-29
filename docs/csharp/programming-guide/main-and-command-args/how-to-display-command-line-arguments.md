---
title: 'Visualización de argumentos de la línea de comandos: Guía de programación de C#'
description: Aprenda a mostrar argumentos de la línea de comandos. Vea un ejemplo de código y examine los recursos adicionales disponibles.
ms.date: 07/20/2015
helpviewer_keywords:
- command-line arguments [C#], displaying
ms.assetid: b8479f2d-9e05-4d38-82da-2e61246e5437
ms.openlocfilehash: 717e27c23724e63c03a38b028ef99dc6530b4745
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91195485"
---
# <a name="how-to-display-command-line-arguments-c-programming-guide"></a>Visualización de argumentos de la línea de comandos (Guía de programación de C#)

El acceso a los argumentos proporcionados para un archivo ejecutable en la línea de comandos se puede realizar a través de un parámetro opcional para `Main`. Los argumentos se proporcionan en forma de una matriz de cadenas. Cada elemento de la matriz contiene un argumento. Se quita el espacio en blanco entre los argumentos. Por ejemplo, considere estas invocaciones de línea de comandos de un ejecutable ficticio:  
  
|Entrada en la línea de comandos|Matriz de cadenas que se pasa a Main|  
|----------------------------|-------------------------------------|  
|**executable.exe a b c**|"a"<br /><br /> "b"<br /><br /> "c"|  
|**executable.exe one two**|"one"<br /><br /> "two"|  
|**executable.exe "one two" three**|"one two"<br /><br /> "three"|  
  
> [!NOTE]
> Si se ejecuta una aplicación en Visual Studio, se pueden especificar argumentos de línea de comandos en la [Página Depuración, Diseñador de proyectos](/visualstudio/ide/reference/debug-page-project-designer).  
  
## <a name="example"></a>Ejemplo  

 En este ejemplo se muestran los argumentos de la línea de comandos pasados a una aplicación de la línea de comandos. La salida que se muestra corresponde a la primera entrada de la tabla anterior.  
  
 [!code-csharp[csProgGuideMain#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class1.cs#9)]  
  
## <a name="see-also"></a>Consulte también

- [Guía de programación de C#](../index.md)
- [Compilar la línea de comandos con csc.exe](../../language-reference/compiler-options/command-line-building-with-csc-exe.md)
- [Main() y argumentos de línea de comandos](./index.md)
- [Valores devueltos de Main()](./main-return-values.md)
