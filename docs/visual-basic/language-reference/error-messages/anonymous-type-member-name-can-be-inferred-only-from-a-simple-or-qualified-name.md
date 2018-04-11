---
title: El nombre de miembro de tipo anónimo sólo se puede inferir a partir de un nombre simple o completo sin argumentos
ms.date: 07/20/2015
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc36556
- bc36556
helpviewer_keywords:
- BC36556
ms.assetid: e3ba1f33-3a71-4f03-9b04-ed5ec17de17c
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 7068928a17ee5fdb7bf6b5e0a40aaa7e5ef32f11
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="anonymous-type-member-name-can-be-inferred-only-from-a-simple-or-qualified-name-with-no-arguments"></a>El nombre de miembro de tipo anónimo sólo se puede inferir a partir de un nombre simple o completo sin argumentos
No se puede inferir un nombre de miembro de tipo anónimo en una expresión compleja.  
  
```vb  
Dim numbers() As Integer = {1, 2, 3, 4, 5}  
' Not valid.  
' Dim instanceName1 = New With {numbers(3)}  
```  
  
 Para obtener más información acerca de los orígenes desde el que los tipos anónimos pueden y no pueden deducir tipos y nombres de miembro, vea [Cómo: deducir los nombres de propiedad y los tipos en declaraciones de tipos anónimos](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md).  
  
 **Id. de error:** BC36556  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Asigne la expresión a un nombre de miembro, como se muestra en el código siguiente:  
  
    ```  
    Dim instanceName2 = New With {.number = numbers(3)}  
    ```  
  
## <a name="see-also"></a>Vea también  
 [Tipos anónimos](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)  
 [Deducir tipos y nombres de propiedades en declaraciones de tipos anónimos](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)
