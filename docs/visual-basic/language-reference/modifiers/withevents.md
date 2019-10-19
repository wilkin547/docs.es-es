---
title: WithEvents (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.WithEvents
- WithEvents
helpviewer_keywords:
- WithEvents keyword [Visual Basic]
ms.assetid: 19d461f5-d72f-4de9-8c1d-0a6650316990
ms.openlocfilehash: 50d5a768393e90d28d150b451405e35e6f4c7953
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583042"
---
# <a name="withevents-visual-basic"></a>WithEvents (Visual Basic)
Especifica que una o varias variables de miembro declaradas hacen referencia a una instancia de una clase que puede generar eventos.

## <a name="remarks"></a>Comentarios

Cuando una variable se define utilizando `WithEvents`, puede especificar mediante declaración que un método controla los eventos de la variable mediante la palabra clave `Handles`.

Solo se puede usar `WithEvents` en el nivel de clase o módulo. Esto significa que el contexto de la declaración de una variable `WithEvents` debe ser una clase o módulo y no puede ser un archivo de código fuente, un espacio de nombres, una estructura o un procedimiento.

No se puede usar `WithEvents` en un miembro de estructura.

Solo se pueden declarar variables individuales, no matrices, con `WithEvents`.

## <a name="rules"></a>Reglas

**Tipos de elemento.** Debe declarar `WithEvents` variables como variables de objeto para que puedan aceptar instancias de clase. Sin embargo, no puede declararlos como `Object`. Debe declararlos como la clase específica que puede provocar los eventos.

El modificador `WithEvents` se puede usar en este contexto: [instrucción Dim](../../../visual-basic/language-reference/statements/dim-statement.md)

## <a name="example"></a>Ejemplo

```vb
Dim WithEvents app As Application
```

## <a name="see-also"></a>Vea también

- [Handles](../../../visual-basic/language-reference/statements/handles-clause.md)
- [Palabras clave](../../../visual-basic/language-reference/keywords/index.md)
- [Eventos](../../../visual-basic/programming-guide/language-features/events/index.md)
