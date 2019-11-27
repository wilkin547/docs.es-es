---
title: Variables de estructura
ms.date: 07/20/2015
helpviewer_keywords:
- structures [Visual Basic], variables
- structures [Visual Basic], structure variables
- variables [Visual Basic], structure variables
- structure variables [Visual Basic]
ms.assetid: 156872f8-aabc-4454-8e2d-f2253c3c13c9
ms.openlocfilehash: 16b6cdc5a849b50f6caa8b7963dac5c12d63cf3e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346303"
---
# <a name="structure-variables-visual-basic"></a>Variables de estructura (Visual Basic)

Una vez creada una estructura, puede declarar variables de nivel de procedimiento y de nivel de módulo como ese tipo. Por ejemplo, puede crear una estructura que registre información sobre un sistema informático. En el siguiente ejemplo se muestra cómo hacerlo.

```vb
Public Structure systemInfo
    Public cPU As String
    Public memory As Long
    Public purchaseDate As Date
End Structure
```

Ahora puede declarar variables de ese tipo. La siguiente declaración ilustra esto.

```vb
Dim mySystem, yourSystem As systemInfo
```

> [!NOTE]
> En las clases y los módulos, las estructuras declaradas con la [instrucción Dim](../../../../visual-basic/language-reference/statements/dim-statement.md) tienen como valor predeterminado el acceso público. Si desea que una estructura sea privada, asegúrese de que la declara mediante la palabra clave [Private](../../../../visual-basic/language-reference/modifiers/private.md) .

## <a name="access-to-structure-values"></a>Acceso a los valores de la estructura

Para asignar y recuperar valores de los elementos de una variable de estructura, se usa la misma sintaxis que se usa para establecer y obtener propiedades en un objeto. Coloque el operador de acceso a miembros (`.`) entre el nombre de la variable de estructura y el nombre del elemento. En el ejemplo siguiente se obtiene acceso a los elementos de las variables declaradas previamente como tipo `systemInfo`.

```vb
mySystem.cPU = "486"
Dim tooOld As Boolean
If yourSystem.purchaseDate < #1/1/1992# Then tooOld = True
```

## <a name="assigning-structure-variables"></a>Asignar variables de estructura

También puede asignar una variable a otra si ambos son del mismo tipo de estructura. Esto copia todos los elementos de una estructura en los elementos correspondientes de la otra. La siguiente declaración ilustra esto.

```vb
yourSystem = mySystem
```

Si un elemento de estructura es un tipo de referencia, como un `String`, `Object`o una matriz, se copia el puntero a los datos. En el ejemplo anterior, si `systemInfo` hubiera incluido una variable de objeto, el ejemplo anterior habría copiado el puntero de `mySystem` a `yourSystem`y un cambio en los datos del objeto a través de una estructura sería efectivo al obtener acceso a través de la otra estructura.

## <a name="see-also"></a>Vea también

- [Tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [Tipos de datos básicos](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [Tipos de datos compuestos](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)
- [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [Estructuras](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Solución de problemas de tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Declarar una estructura](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [Estructuras y otros elementos de programación](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md)
- [Estructuras y clases](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)
- [Structure (instrucción)](../../../../visual-basic/language-reference/statements/structure-statement.md)
