---
title: Utilizar controladores de excepciones filtradas por el usuario
ms.date: 03/30/2017
helpviewer_keywords:
- user-filtered exceptions
- exceptions, user-filtered
ms.assetid: aa80d155-060d-41b4-a636-1ceb424afee8
ms.openlocfilehash: 4b85c2be0ed61af38eac1b65fb70f0ef1ea4405e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95669047"
---
# <a name="using-user-filtered-exception-handlers"></a>Utilizar controladores de excepciones filtradas por el usuario

Actualmente, Visual Basic admite excepciones filtradas por el usuario. Los controladores de excepciones filtradas por usuario detectan y controlan las excepciones en función de los requisitos que se definen para la excepción. Estos controladores utilizan la instrucción **Catch** con la palabra clave **When**.  
  
 Esta técnica es útil cuando un objeto de excepción concreto corresponde a varios errores. En este caso, el objeto normalmente tiene una propiedad que contiene el código de error específico asociado con el error. Puede utilizar la propiedad de código de error en la expresión para seleccionar solo el error concreto que desea administrar en esa cláusula **Catch**.  
  
 El siguiente ejemplo de Visual Basic ilustra la instrucción **Catch/When**.  
  
```vb
Try  
    'Try statements.  
    Catch When Err = VBErr_ClassLoadException
    'Catch statements.
End Try  
```  
  
 La expresión de la cláusula filtrada por el usuario no está restringida en modo alguno. Si se produce una excepción durante la ejecución de la expresión filtrada por el usuario, esa excepción se descarta y la expresión de filtro se considera evaluada como false. En este caso, Common Language Runtime continúa la búsqueda de un controlador para la excepción actual.  
  
## <a name="combining-the-specific-exception-and-the-user-filtered-clauses"></a>Combinar la excepción específica y las cláusulas filtradas por el usuario  

 Una instrucción Catch puede contener tanto la excepción específica como las cláusulas filtradas por el usuario. El motor de tiempo de ejecución comprueba primero la excepción específica. Si la comprobación de la excepción específica es correcta, el motor de tiempo de ejecución ejecuta el filtro de usuario. El filtro genérico puede contener una referencia a la variable declarada en el filtro de clase. Tenga en cuenta que no se puede revertir el orden de las dos cláusulas de filtro.  
  
 El siguiente ejemplo de Visual Basic muestra la excepción específica `ClassLoadException` en la instrucción **Catch**, así como la cláusula filtrada por el usuario mediante la palabra clave **When**.  
  
```vb
Try  
    'Try statements.
    Catch cle As ClassLoadException When cle.IsRecoverable()  
    'Catch statements.
End Try  
```  

## <a name="see-also"></a>Vea también

- [Excepciones](index.md)
