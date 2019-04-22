---
title: Variables de estructura (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- structures [Visual Basic], variables
- structures [Visual Basic], structure variables
- variables [Visual Basic], structure variables
- structure variables [Visual Basic]
ms.assetid: 156872f8-aabc-4454-8e2d-f2253c3c13c9
ms.openlocfilehash: 9a6e542e297a17f44d929235530ae6058cf13a36
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58816335"
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
>  En las clases y módulos, las estructuras declaradas mediante la [instrucción Dim](../../../../visual-basic/language-reference/statements/dim-statement.md) predeterminado para el acceso público. Si desea una estructura sea privada, asegúrese de que se declara mediante la [privada](../../../../visual-basic/language-reference/modifiers/private.md) palabra clave.  
  
## <a name="access-to-structure-values"></a>Acceso a los valores de la estructura  
 Para asignar y recuperar valores de los elementos de una variable de estructura, utilice la misma sintaxis que se usa para establecer y obtener propiedades de un objeto. Coloque el operador de acceso de miembro (`.`) entre el nombre de variable de estructura y el nombre del elemento. El ejemplo siguiente se obtiene acceso a elementos de las variables declaradas previamente como tipo `systemInfo`.  
  
```  
mySystem.cPU = "486"  
Dim tooOld As Boolean  
If yourSystem.purchaseDate < #1/1/1992# Then tooOld = True  
```  
  
## <a name="assigning-structure-variables"></a>Asignación de Variables de estructura  
 También puede asignar una variable a otro si ambos son del mismo tipo de estructura. Esto copia todos los elementos de una estructura a los elementos correspondientes en el otro. Esto ilustra en la siguiente declaración:  
  
```  
yourSystem = mySystem  
```  
  
 Si un elemento de estructura es un tipo de referencia, como un `String`, `Object`, o matriz, el puntero a los datos se copia. En el ejemplo anterior, si `systemInfo` había incluido una variable de objeto, a continuación, en el ejemplo anterior se habría copiado el puntero de `mySystem` a `yourSystem`, y un cambio en los datos del objeto a través de una estructura estaría activo cuando se tiene acceso a través de la otra estructura.  
  
## <a name="see-also"></a>Vea también

- [Tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [Tipos de datos básicos](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [Tipos de datos compuestos](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)
- [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [Estructuras](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Solución de problemas de tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Cómo: Declarar una estructura](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [Estructuras y otros elementos de programación](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md)
- [Estructuras y clases](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)
- [Structure (instrucción)](../../../../visual-basic/language-reference/statements/structure-statement.md)
