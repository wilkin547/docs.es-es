---
description: 'Más información sobre: Cómo: definir un parámetro para un procedimiento (Visual Basic)'
title: Procedimiento para definir un parámetro para un procedimiento
ms.date: 07/20/2015
helpviewer_keywords:
- procedure parameters [Visual Basic], defining data types for
- procedures [Visual Basic], parameters
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedure parameters [Visual Basic], defining
ms.assetid: 7962808d-407e-4e84-984e-43e9857c53c9
ms.openlocfilehash: e9405e01c81f50c361c8e7ff9736e2ac0cde144d
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100476233"
---
# <a name="how-to-define-a-parameter-for-a-procedure-visual-basic"></a>Cómo: Definir parámetros para un procedimiento (Visual Basic)

Un *parámetro* permite al código de llamada pasar un valor al procedimiento cuando lo llama. Declare cada parámetro de un procedimiento de la misma manera que declara una variable, especificando su nombre y tipo de datos. También se especifica el mecanismo de paso y si el parámetro es opcional.  
  
 Para obtener más información, vea [argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md).  
  
### <a name="to-define-a-procedure-parameter"></a>Para definir un parámetro de procedimiento  
  
1. En la declaración de procedimiento, agregue el nombre del parámetro a la lista de parámetros del procedimiento, separándolos de otros parámetros mediante comas.  
  
2. Decida el tipo de datos del parámetro.  
  
3. Siga el nombre del parámetro con una `As` cláusula para especificar el tipo de datos.  
  
4. Decida el mecanismo de paso que desea para el parámetro. Normalmente se pasa un parámetro por valor, a menos que se desee que el procedimiento pueda cambiar su valor en el código de llamada.  
  
5. Anteponga a [ByVal](../../../language-reference/modifiers/byval.md) o [ByRef](../../../language-reference/modifiers/byref.md) el nombre del parámetro para especificar el mecanismo de paso. Para obtener más información, vea [diferencias entre pasar un argumento por valor y por referencia](./differences-between-passing-an-argument-by-value-and-by-reference.md).  
  
6. Si el parámetro es opcional, preceda al mecanismo de paso con [opcional](../../../language-reference/modifiers/optional.md) y siga el tipo de datos del parámetro con un signo igual ( `=` ) y un valor predeterminado.  
  
     En el ejemplo siguiente se define el esquema de un `Sub` procedimiento con tres parámetros. Los dos primeros son obligatorios y el tercero es opcional. Las declaraciones de parámetros se separan en la lista de parámetros por comas.  
  
     [!code-vb[VbVbcnProcedures#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#33)]  
  
     El primer parámetro acepta un `customer` objeto y `updateCustomer` puede actualizar directamente la variable pasada a `c` porque el argumento se pasa a [ByRef](../../../language-reference/modifiers/byref.md). El procedimiento no puede cambiar los valores de los dos últimos argumentos porque se pasan [ByVal](../../../language-reference/modifiers/byval.md).  
  
     Si el código de llamada no proporciona un valor para el `level` parámetro, Visual Basic lo establece en el valor predeterminado de 0.  
  
     Si el modificador de comprobación de tipo ([Option Strict Statement](../../../language-reference/statements/option-strict-statement.md)) es `Off` , la `As` cláusula es opcional cuando se define un parámetro. Sin embargo, si cualquiera de los parámetros utiliza una `As` cláusula, todos ellos deben usarlo. Si el modificador de comprobación de tipo es `On` , `As` se requiere la cláusula para cada definición de parámetro.  
  
     La especificación de tipos de datos para todos los elementos de programación se conoce como establecimiento de tipos *seguros*. Al establecer `Option Strict On` , Visual Basic aplica tipos fuertemente tipados. Esto es muy recomendable, por las razones siguientes:  
  
    - Habilita la compatibilidad con IntelliSense para las variables y los parámetros. Esto le permite ver sus propiedades y otros miembros a medida que escribe en el código.  
  
    - Permite que el compilador realice la comprobación de tipos. Esto ayuda a las instrucciones catch que pueden producir errores en tiempo de ejecución debido a errores como el desbordamiento. También detecta llamadas a métodos en objetos que no las admiten.  
  
    - Esto da como resultado una ejecución más rápida del código. Una razón para esto es que, si no se especifica un tipo de datos para un elemento de programación, el compilador Visual Basic le asigna el `Object` tipo. Es posible que el código compilado tenga que realizar la conversión entre `Object` y otros tipos de datos, lo que reduce el rendimiento.  
  
## <a name="see-also"></a>Consulte también

- [Procedimientos](./index.md)
- [Procedimientos Sub](./sub-procedures.md)
- [Procedimientos de función](./function-procedures.md)
- [Procedimiento para pasar argumentos a un procedimiento](./how-to-pass-arguments-to-a-procedure.md)
- [Pasar argumentos por valor y por referencia](./passing-arguments-by-value-and-by-reference.md)
- [Procedimientos recursivos](./recursive-procedures.md)
- [Sobrecarga de procedimientos](./procedure-overloading.md)
- [Objetos y clases](../objects-and-classes/index.md)
- [Programación orientada a objetos (Visual Basic)](../../concepts/object-oriented-programming.md)
