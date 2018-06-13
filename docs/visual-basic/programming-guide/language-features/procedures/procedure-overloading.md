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
ms.openlocfilehash: 0d1f2c4d8c88922659b3d91ed41d5e760e6e5233
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33653919"
---
# <a name="procedure-overloading-visual-basic"></a>Sobrecarga de procedimiento (Visual Basic)
*Sobrecarga* un procedimiento significa definirlo en varias versiones, utilizando el mismo nombre pero distintas listas de parámetros. El propósito de sobrecarga es definir varias versiones estrechamente relacionadas de un procedimiento sin tener que distinguirlas por su nombre. La forma de hacerlo es mediante la variación de la lista de parámetros.  
  
## <a name="overloading-rules"></a>Reglas de sobrecarga  
 Cuando se sobrecarga un procedimiento, se aplican las siguientes reglas:  
  
-   **Mismo nombre**. Cada versión sobrecargada debe usar el mismo nombre de procedimiento.  
  
-   **Otra firma**. Cada versión sobrecargada debe diferir de todas las demás versiones sobrecargadas en al menos uno de los siguientes aspectos:  
  
    -   Número de parámetros  
  
    -   Orden de los parámetros  
  
    -   Tipos de datos de los parámetros  
  
    -   Número de parámetros de tipo (para un procedimiento genérico)  
  
    -   Tipo de valor devuelto (solo para un operador de conversión)  
  
     Junto con el nombre del procedimiento, los elementos anteriores se denominan colectivamente el *firma* del procedimiento. Cuando se llama a un procedimiento sobrecargado, el compilador utiliza la firma para comprobar que la llamada coincide con la definición.  
  
-   **Elementos no forman parte de la firma**. No se pueden sobrecargar un procedimiento sin modificar la firma. En concreto, no se puede sobrecargar un procedimiento cambiando únicamente uno o varios de los siguientes elementos:  
  
    -   Palabras clave de modificador de procedimiento, como `Public`, `Shared`, y `Static`  
  
    -   Parámetro o escriba los nombres de parámetro  
  
    -   Restricciones de parámetro de tipo (para un procedimiento genérico)  
  
    -   Palabras clave de modificador de parámetro, como `ByRef` y `Optional`  
  
    -   Si devuelve un valor  
  
    -   El tipo de datos del valor devuelto (excepto para un operador de conversión)  
  
     Los elementos de la lista anterior no forman parte de la firma. Aunque no puede usarlos para diferenciar las versiones sobrecargadas, se puede variar entre las versiones sobrecargadas que correctamente se diferencian por sus firmas.  
  
-   **Argumentos de tiempo de ejecución**. Si desea pasar una variable de objeto enlazado a un tiempo de ejecución a una versión sobrecargada, debe declarar el parámetro correspondiente como <xref:System.Object>.  
  
## <a name="multiple-versions-of-a-procedure"></a>Varias versiones de un procedimiento  
 Supongamos que está escribiendo un `Sub` procedimiento para registrar una transacción en el saldo de un cliente y se quiere que puedan hacer referencia al cliente por nombre o por número de cuenta. Para ello, puede definir diferentes `Sub` procedimientos, como en el ejemplo siguiente:  
  
 [!code-vb[VbVbcnProcedures#73](./codesnippet/VisualBasic/procedure-overloading_1.vb)]  
  
### <a name="overloaded-versions"></a>Versiones sobrecargadas  
 Es una alternativa a la sobrecarga de un único nombre de procedimiento. Puede usar el [sobrecargas](../../../../visual-basic/language-reference/modifiers/overloads.md) palabra clave que se va a definir una versión del procedimiento para cada lista de parámetros, como se indica a continuación:  
  
 [!code-vb[VbVbcnProcedures#72](./codesnippet/VisualBasic/procedure-overloading_2.vb)]  
  
#### <a name="additional-overloads"></a>Sobrecargas adicionales  
 Si desea aceptar una cantidad de transacción en la vista `Decimal` o `Single`, podría sobrecargar de nuevo `post` para permitir esta variación. Si lo hizo en cada una de las sobrecargas en el ejemplo anterior, podría tener cuatro `Sub` procedimientos, todos ellos con el mismo nombre pero con cuatro firmas diferentes.  
  
## <a name="advantages-of-overloading"></a>Ventajas de sobrecarga  
 La ventaja de sobrecargar un procedimiento radica en la flexibilidad de la llamada. Para usar el `post` procedimiento declarado en el ejemplo anterior, el código de llamada puede obtener la identificación del cliente como un `String` o un `Integer`y, a continuación, llamar al mismo procedimiento en cualquiera de los casos. Esto se ilustra en el siguiente ejemplo:  
  
 [!code-vb[VbVbcnProcedures#56](./codesnippet/VisualBasic/procedure-overloading_3.vb)]  
  
 [!code-vb[VbVbcnProcedures#57](./codesnippet/VisualBasic/procedure-overloading_4.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Procedimientos](./index.md)  
 [Definir varias versiones de un procedimiento](./how-to-define-multiple-versions-of-a-procedure.md)  
 [Llamar a un procedimiento sobrecargado](./how-to-call-an-overloaded-procedure.md)  
 [Sobrecargar un procedimiento que toma parámetros opcionales](./how-to-overload-a-procedure-that-takes-optional-parameters.md)  
 [Sobrecargar un procedimiento que toma un número indefinido de parámetros](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)  
 [Consideraciones sobre la sobrecarga de procedimientos](./considerations-in-overloading-procedures.md)  
 [Resolución de sobrecargas](./overload-resolution.md)  
 [Sobrecargas](../../../../visual-basic/language-reference/modifiers/overloads.md)  
 [Tipos genéricos en Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
