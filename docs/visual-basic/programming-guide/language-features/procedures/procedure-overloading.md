---
title: Sobrecarga de procedimientos
ms.date: 07/20/2015
helpviewer_keywords:
- signatures
- Overloads keyword [Visual Basic]
- hiding by signature
- Visual Basic code, procedures
- procedures [Visual Basic], signatures for
- procedures [Visual Basic], overloading
- procedures [Visual Basic], multiple versions
- parameters [Visual Basic], lists
- signatures [Visual Basic], procedure
- parameter lists [Visual Basic]
- Visual Basic code, parameter lists
- Shadows keyword [Visual Basic]
- procedure overloading
- procedures [Visual Basic], parameter lists
ms.assetid: fbc7fb18-e3b2-48b6-b554-64c00ed09d2a
ms.openlocfilehash: 41a971896fe726cbe9849fd46334910e7288afe0
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352596"
---
# <a name="procedure-overloading-visual-basic"></a>Sobrecarga de procedimiento (Visual Basic)

*Sobrecargar* un procedimiento significa definirlo en varias versiones, con el mismo nombre pero con diferentes listas de parámetros. El propósito de la sobrecarga es definir varias versiones estrechamente relacionadas de un procedimiento sin tener que diferenciarlas por nombre. Para ello, variará la lista de parámetros.

## <a name="overloading-rules"></a>Sobrecargar reglas

Al sobrecargar un procedimiento, se aplican las siguientes reglas:

- **Mismo nombre**. Cada versión sobrecargada debe usar el mismo nombre de procedimiento.

- **Firma diferente**. Cada versión sobrecargada debe ser diferente de todas las demás versiones sobrecargadas en al menos uno de los siguientes aspectos:

  - Número de parámetros

  - Orden de los parámetros

  - Tipos de datos de los parámetros

  - Número de parámetros de tipo (para un procedimiento genérico)

  - Tipo de valor devuelto (solo para un operador de conversión)

  Junto con el nombre del procedimiento, los elementos anteriores se denominan colectivamente la *firma* del procedimiento. Cuando se llama a un procedimiento sobrecargado, el compilador usa la firma para comprobar que la llamada coincide correctamente con la definición.

- **Elementos que no forman parte de la firma**. No se puede sobrecargar un procedimiento sin variar la firma. En concreto, no se puede sobrecargar un procedimiento cambiando solo uno o varios de los siguientes elementos:

  - Palabras clave de modificador de procedimientos, como `Public`, `Shared`y `Static`

  - Nombres de parámetros de tipo o parámetro

  - Restricciones de parámetros de tipo (para un procedimiento genérico)

  - Palabras clave de modificador de parámetro, como `ByRef` y `Optional`

  - Si devuelve un valor

  - El tipo de datos del valor devuelto (excepto para un operador de conversión)

  Los elementos de la lista anterior no forman parte de la firma. Aunque no puede usarlos para diferenciar entre las versiones sobrecargadas, puede modificarlas entre las versiones sobrecargadas que se diferencian correctamente por sus firmas.

- **Argumentos enlazados en tiempo de ejecución**. Si piensa pasar una variable de objeto enlazado en tiempo de ejecución a una versión sobrecargada, debe declarar el parámetro adecuado como <xref:System.Object>.

## <a name="multiple-versions-of-a-procedure"></a>Varias versiones de un procedimiento

Supongamos que está escribiendo una `Sub` procedimiento para publicar una transacción en el saldo de un cliente y desea poder hacer referencia al cliente por el nombre o por el número de cuenta. Para ello, puede definir dos procedimientos de `Sub` diferentes, como en el ejemplo siguiente:

[!code-vb[VbVbcnProcedures#73](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#73)]

### <a name="overloaded-versions"></a>Versiones sobrecargadas

Una alternativa es sobrecargar un único nombre de procedimiento. Puede usar la palabra clave [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) para definir una versión del procedimiento para cada lista de parámetros, como se indica a continuación:

[!code-vb[VbVbcnProcedures#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#72)]

#### <a name="additional-overloads"></a>Sobrecargas adicionales

Si también desease aceptar una cantidad de transacción en `Decimal` o `Single`, podría sobrecargar `post` para permitir esta variación. Si lo hizo en cada una de las sobrecargas del ejemplo anterior, tendría cuatro procedimientos `Sub`, todos con el mismo nombre pero con cuatro firmas diferentes.

## <a name="advantages-of-overloading"></a>Ventajas de la sobrecarga

La ventaja de sobrecargar un procedimiento es la flexibilidad de la llamada. Para usar el procedimiento `post` declarado en el ejemplo anterior, el código de llamada puede obtener la identificación del cliente como un `String` o un `Integer`y, a continuación, llamar al mismo procedimiento en cualquier caso. Esto se ilustra en el siguiente ejemplo:

[!code-vb[VbVbcnProcedures#56](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#56)]

[!code-vb[VbVbcnProcedures#57](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#57)]

## <a name="see-also"></a>Vea también

- [Procedimientos](./index.md)
- [Definir varias versiones de un procedimiento](./how-to-define-multiple-versions-of-a-procedure.md)
- [Llamar a un procedimiento sobrecargado](./how-to-call-an-overloaded-procedure.md)
- [Sobrecargar un procedimiento que toma parámetros opcionales](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [Sobrecargar un procedimiento que toma un número indefinido de parámetros](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [Consideraciones sobre la sobrecarga de procedimientos](./considerations-in-overloading-procedures.md)
- [Resolución de sobrecargas](./overload-resolution.md)
- [Sobrecargas](../../../../visual-basic/language-reference/modifiers/overloads.md)
- [Generic Types in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
