---
title: Variables de estructura (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- structures [Visual Basic], variables
- structures [Visual Basic], structure variables
- variables [Visual Basic], structure variables
- structure variables [Visual Basic]
ms.assetid: 156872f8-aabc-4454-8e2d-f2253c3c13c9
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ef42c44de84caffde909eb2b3e9361016a6abb97
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="structure-variables-visual-basic"></a>Variables de estructura (Visual Basic)
Una vez haya creado una estructura, puede declarar variables de nivel de procedimiento y el nivel de módulo como ese tipo. Por ejemplo, puede crear una estructura que registra la información acerca de un sistema informático. En el siguiente ejemplo se muestra cómo hacerlo.  
  
```  
Public Structure systemInfo  
    Public cPU As String  
    Public memory As Long  
    Public purchaseDate As Date  
End Structure  
```  
  
 Ahora puede declarar variables de ese tipo. Esto ilustra en la siguiente declaración:  
  
```  
Dim mySystem, yourSystem As systemInfo  
```  
  
> [!NOTE]
>  En las clases y módulos, las estructuras declaradas mediante la [Dim (instrucción)](../../../../visual-basic/language-reference/statements/dim-statement.md) predeterminado para el acceso público. Si piensa que una estructura sea privada, asegúrese de que se declara mediante la [privada](../../../../visual-basic/language-reference/modifiers/private.md) palabra clave.  
  
## <a name="access-to-structure-values"></a>Acceso a valores de estructura  
 Para asignar y recuperar valores de los elementos de una variable de estructura, utilice la misma sintaxis que se utilice para establecer y obtener propiedades de un objeto. Coloque el operador de acceso de miembro (`.`) entre el nombre de variable de estructura y el nombre del elemento. En el ejemplo siguiente se tiene acceso a elementos de las variables declaradas previamente como tipo `systemInfo`.  
  
```  
mySystem.cPU = "486"  
Dim tooOld As Boolean  
If yourSystem.purchaseDate < #1/1/1992# Then tooOld = True  
```  
  
## <a name="assigning-structure-variables"></a>Asignación de Variables de estructura  
 También puede asignar una variable a otro si ambos son del mismo tipo de estructura. Esto copia todos los elementos de una estructura en los elementos correspondientes de la otra. Esto ilustra en la siguiente declaración:  
  
```  
yourSystem = mySystem  
```  
  
 Si un elemento de estructura es un tipo de referencia, como un `String`, `Object`, o se copia la matriz, el puntero a los datos. En el ejemplo anterior, si `systemInfo` hubiera incluido una variable de objeto, a continuación, en el ejemplo anterior se habría copiado el puntero de `mySystem` a `yourSystem`, y un cambio en los datos del objeto a través de una estructura estaría activo cuando se tiene acceso a través de la otra estructura.  
  
## <a name="see-also"></a>Vea también  
 [Tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [Tipos de datos básicos](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)  
 [Tipos de datos compuestos](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)  
 [Tipos de valores y tipos de referencias](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [Estructuras](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [Solución de problemas de tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [Declarar una estructura](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)  
 [Estructuras y otros elementos de programación](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md)  
 [Estructuras y clases](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)  
 [Structure (instrucción)](../../../../visual-basic/language-reference/statements/structure-statement.md)
