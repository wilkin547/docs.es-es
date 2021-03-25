---
title: 'Visualización de argumentos de la línea de comandos: Guía de programación de C#'
description: Aprenda a mostrar argumentos de la línea de comandos. Vea un ejemplo de código y examine los recursos adicionales disponibles.
ms.date: 03/08/2021
helpviewer_keywords:
- command-line arguments [C#], displaying
ms.assetid: b8479f2d-9e05-4d38-82da-2e61246e5437
ms.openlocfilehash: 7c3e8d7f6ad2a599308057e996808509e70b7508
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "103480265"
---
# <a name="how-to-display-command-line-arguments-c-programming-guide"></a>Visualización de argumentos de la línea de comandos (Guía de programación de C#)

Los argumentos proporcionados para un archivo ejecutable en la línea de comandos son accesibles en [instrucciones de nivel superior](top-level-statements.md) o mediante un parámetro opcional para `Main`. Los argumentos se proporcionan en forma de una matriz de cadenas. Cada elemento de la matriz contiene un argumento. Se quita el espacio en blanco entre los argumentos. Por ejemplo, considere estas invocaciones de línea de comandos de un ejecutable ficticio:  
  
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
- [Main() y argumentos de la línea de comandos](./index.md)
- [Valores devueltos de Main()](./main-return-values.md)
