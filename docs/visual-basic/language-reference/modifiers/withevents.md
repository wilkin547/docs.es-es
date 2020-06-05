---
title: WithEvents
ms.date: 07/20/2015
f1_keywords:
- vb.WithEvents
- WithEvents
helpviewer_keywords:
- WithEvents keyword [Visual Basic]
ms.assetid: 19d461f5-d72f-4de9-8c1d-0a6650316990
ms.openlocfilehash: 48261e27de302c1809c9725e6e2fc0705a803930
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84386781"
---
# <a name="withevents-visual-basic"></a>WithEvents (Visual Basic)
Especifica que una o varias variables de miembro declaradas hacen referencia a una instancia de una clase que puede generar eventos.

## <a name="remarks"></a>Observaciones

Cuando una variable se define mediante `WithEvents` , puede especificar mediante declaración que un método controla los eventos de la variable mediante la `Handles` palabra clave.

Solo se puede usar `WithEvents` en el nivel de clase o módulo. Esto significa que el contexto de la declaración de una `WithEvents` variable debe ser una clase o módulo y no puede ser un archivo de código fuente, un espacio de nombres, una estructura o un procedimiento.

No se puede usar `WithEvents` en un miembro de estructura.

Solo puede declarar variables individuales, no matrices, con `WithEvents` .

## <a name="rules"></a>Reglas

**Tipos de elemento.** Debe declarar `WithEvents` variables como variables de objeto para que puedan aceptar instancias de clase. Sin embargo, no se pueden declarar como `Object` . Debe declararlos como la clase específica que puede provocar los eventos.

El `WithEvents` modificador se puede usar en este contexto: [instrucción Dim](../statements/dim-statement.md)

## <a name="example"></a>Ejemplo

```vb
Dim WithEvents app As Application
```

## <a name="see-also"></a>Consulte también

- [Asas](../statements/handles-clause.md)
- [Palabras clave](../keywords/index.md)
- [Eventos](../../programming-guide/language-features/events/index.md)
