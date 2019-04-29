---
title: Sobrecarga de procedimiento (Visual Basic)
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
ms.openlocfilehash: 6e8d1fa72c60c4fa3d2237ad24c2d1b4891a7bf2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61791877"
---
# <a name="procedure-overloading-visual-basic"></a>Sobrecarga de procedimiento (Visual Basic)
*Sobrecarga* un procedimiento significa definirlo en varias versiones, con el mismo nombre pero con distintas listas de parámetros. El propósito de sobrecarga es definir varias versiones estrechamente relacionadas de un procedimiento sin tener que distinguirlas por su nombre. Hacer esto mediante la variación de la lista de parámetros.  
  
## <a name="overloading-rules"></a>Reglas de sobrecarga  
 Cuando se sobrecarga un procedimiento, se aplican las reglas siguientes:  
  
- **Mismo nombre**. Cada versión sobrecargada debe usar el mismo nombre de procedimiento.  
  
- **Firma diferente**. Cada versión sobrecargada debe diferir de todas las versiones sobrecargadas en al menos uno de los siguientes aspectos:  
  
    - Número de parámetros  
  
    - Orden de los parámetros  
  
    - Tipos de datos de los parámetros  
  
    - Número de parámetros de tipo (para un procedimiento genérico)  
  
    - Tipo de valor devuelto (solo para un operador de conversión)  
  
     Junto con el nombre del procedimiento, los elementos anteriores se denominan colectivamente la *firma* del procedimiento. Cuando se llama a un procedimiento sobrecargado, el compilador utiliza la firma para comprobar que la llamada coincide con la definición.  
  
- **Los elementos no forma parte de la firma**. No se pueden sobrecargar un procedimiento sin modificar la firma. En concreto, no se puede sobrecargar un procedimiento cambiando únicamente uno o varios de los siguientes elementos:  
  
    - Palabras clave de modificador de procedimiento, como `Public`, `Shared`, y `Static`  
  
    - Nombres de parámetro de tipo o parámetro  
  
    - Restricciones de parámetro de tipo (para un procedimiento genérico)  
  
    - Palabras clave de modificador de parámetro, como `ByRef` y `Optional`  
  
    - Si devuelve un valor  
  
    - El tipo de datos del valor devuelto (excepto para un operador de conversión)  
  
     Los elementos de la lista anterior no forman parte de la firma. Aunque no se pueden utilizar para diferenciar entre versiones sobrecargadas, se puede variar entre las versiones sobrecargadas que correctamente se diferencian por sus firmas.  
  
- **Los argumentos enlazados**. Si piensa pasar una variable de objeto enlazado en tiempo de ejecución a una versión sobrecargada, debe declarar el parámetro apropiado como <xref:System.Object>.  
  
## <a name="multiple-versions-of-a-procedure"></a>Varias versiones de un procedimiento  
 Supongamos que está escribiendo un `Sub` procedimiento para registrar una transacción en el saldo de un cliente y desea poder hacer referencia al cliente por nombre o por número de cuenta. Para dar cabida a esto, puede definir dos diferentes `Sub` procedimientos, como en el ejemplo siguiente:  
  
 [!code-vb[VbVbcnProcedures#73](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#73)]  
  
### <a name="overloaded-versions"></a>Versiones sobrecargadas  
 Es una alternativa a la sobrecarga de un único nombre de procedimiento. Puede usar el [sobrecargas](../../../../visual-basic/language-reference/modifiers/overloads.md) palabra clave para definir una versión del procedimiento para cada lista de parámetros, como se indica a continuación:  
  
 [!code-vb[VbVbcnProcedures#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#72)]  
  
#### <a name="additional-overloads"></a>Sobrecargas adicionales  
 Si desea aceptar un importe de transacción en el `Decimal` o `Single`, se podrían sobrecargar aún más `post` para permitir esta variación. Si lo hizo en cada una de las sobrecargas en el ejemplo anterior, tendría cuatro `Sub` procedimientos, todo ello con el mismo nombre pero con cuatro firmas diferentes.  
  
## <a name="advantages-of-overloading"></a>Ventajas de la sobrecarga  
 La ventaja de sobrecargar un procedimiento es en la flexibilidad de la llamada. Para usar el `post` procedimiento declarado en el ejemplo anterior, el código de llamada puede obtener la identificación del cliente como un `String` o un `Integer`y, a continuación, llamar al mismo procedimiento en ambos casos. Esto se ilustra en el siguiente ejemplo:  
  
 [!code-vb[VbVbcnProcedures#56](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#56)]  
  
 [!code-vb[VbVbcnProcedures#57](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#57)]  
  
## <a name="see-also"></a>Vea también

- [Procedimientos](./index.md)
- [Cómo: Definir varias versiones de un procedimiento](./how-to-define-multiple-versions-of-a-procedure.md)
- [Cómo: Llamar a un procedimiento sobrecargado](./how-to-call-an-overloaded-procedure.md)
- [Cómo: Sobrecargar un procedimiento que toma parámetros opcionales](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [Cómo: Sobrecargar un procedimiento que toma un número indefinido de parámetros](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [Consideraciones sobre la sobrecarga de procedimientos](./considerations-in-overloading-procedures.md)
- [Resolución de sobrecargas](./overload-resolution.md)
- [Sobrecargas](../../../../visual-basic/language-reference/modifiers/overloads.md)
- [Generic Types in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
