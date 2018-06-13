---
title: Parámetros de métodos (Referencia de C#)
ms.date: 07/20/2015
helpviewer_keywords:
- methods [C#], parameters
- method parameters [C#]
- parameters [C#]
ms.assetid: 680e39ff-775b-48b0-9f47-4186a5bfc4a1
ms.openlocfilehash: 8a8d300661eec42030900dd9ee85a17e66aa0922
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33269351"
---
# <a name="method-parameters-c-reference"></a>Parámetros de métodos (Referencia de C#)

Los parámetros declarados para un método sin [in](../../../csharp/language-reference/keywords/in-parameter-modifier.md), [ref](../../../csharp/language-reference/keywords/ref.md) o [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) se pasan al método llamado por valor. Ese valor se puede cambiar en el método, pero el cambio se perderá cuando se devuelva el control al procedimiento que ha realizado la llamada. Si usa palabras clave de parámetros de método en la declaración del parámetro, puede modificar este comportamiento.  
  
 Esta sección describe las palabras clave que puede usar para declarar parámetros de métodos:  
  
-   [params](../../../csharp/language-reference/keywords/params.md) especifica que este parámetro puede tomar un número variable de argumentos.
  
-   [in](../../../csharp/language-reference/keywords/in-parameter-modifier.md) especifica que este parámetro se pasa por referencia, pero solo se lee mediante el método llamado.
  
-   [ref](../../../csharp/language-reference/keywords/ref.md) especifica que este parámetro se pasa por referencia y puede ser leído o escrito por el método llamado.
  
-   [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) especifica que este parámetro se pasa por referencia y se escribe mediante el método llamado.
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Palabras clave de C#](../../../csharp/language-reference/keywords/index.md)
