---
title: Procedimiento Definir un parámetro para un procedimiento (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- procedure parameters [Visual Basic], defining data types for
- procedures [Visual Basic], parameters
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedure parameters [Visual Basic], defining
ms.assetid: 7962808d-407e-4e84-984e-43e9857c53c9
ms.openlocfilehash: 3893b87f50b37116b596b35b32c61ca81e47b3e5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54660806"
---
# <a name="how-to-define-a-parameter-for-a-procedure-visual-basic"></a>Procedimiento Definir un parámetro para un procedimiento (Visual Basic)
Un *parámetro* permite pasar un valor al procedimiento cuando lo llama el código de llamada. Declarar cada parámetro para un procedimiento de la misma manera que se declara una variable, especificando su nombre y tipo de datos. También especifica el mecanismo de paso, y si el parámetro es opcional.  
  
 Para obtener más información, consulte [argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md).  
  
### <a name="to-define-a-procedure-parameter"></a>Para definir un parámetro de procedimiento  
  
1.  En la declaración de procedimiento, agregue el nombre de parámetro a la lista de parámetros del procedimiento, sepárelo de otros parámetros mediante comas.  
  
2.  Decida el tipo de datos del parámetro.  
  
3.  Siga el nombre del parámetro con un `As` cláusula para especificar el tipo de datos.  
  
4.  Decidir el mecanismo de paso que desee para el parámetro. Normalmente se pasa un parámetro por valor, a menos que desee que el procedimiento para que pueda cambiar su valor en el código de llamada.  
  
5.  Delante del nombre de parámetro [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) o [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) para especificar el mecanismo de paso. Para obtener más información, consulte [las diferencias entre pasar un argumento por valor y por referencia](./differences-between-passing-an-argument-by-value-and-by-reference.md).  
  
6.  Si el parámetro es opcional, preceder el mecanismo de paso con [opcional](../../../../visual-basic/language-reference/modifiers/optional.md) y siga el tipo de datos de parámetro con un signo igual (`=`) y un valor predeterminado.  
  
     En el ejemplo siguiente se define el contorno de un `Sub` procedimiento con tres parámetros. Los dos primeros son necesarios y el tercero es opcional. Las declaraciones de parámetro se separan en la lista de parámetros mediante comas.  
  
     [!code-vb[VbVbcnProcedures#33](./codesnippet/VisualBasic/how-to-define-a-parameter-for-a-procedure_1.vb)]  
  
     El primer parámetro acepta un `customer` objeto, y `updateCustomer` puede actualizar directamente la variable pasa a `c` porque el argumento se pasa [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md). El procedimiento no puede cambiar los valores de los dos últimos argumentos porque se pasan [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).  
  
     Si el código de llamada no proporciona un valor para el `level` parámetro, Visual Basic se establece en el valor predeterminado de 0.  
  
     Si el modificador de comprobación de tipo ([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) es `Off`, el `As` cláusula es opcional cuando se define un parámetro. Sin embargo, si utiliza un parámetro una `As` cláusula, todas ellas deben usarla. Si el modificador de comprobación de tipo es `On`, el `As` cláusula es obligatoria para cada definición de parámetro.  
  
     Especificar los tipos de datos para todos los elementos de programación se conoce como *establecimiento inflexible de tipos*. Al establecer `Option Strict On`, Visual Basic exige el establecimiento inflexible de tipos. Esto se recomienda encarecidamente, por las razones siguientes:  
  
    -   Habilita la compatibilidad con IntelliSense para las variables y parámetros. Esto le permite ver sus propiedades y otros miembros a medida que escribe en el código.  
  
    -   Permite al compilador que realice la comprobación de tipos. Esto ayuda a detectar las instrucciones que se pueden producir un error en tiempo de ejecución debido a errores, como el desbordamiento. También detecta llamadas a métodos en objetos que no las admiten.  
  
    -   Se produce una ejecución más rápida del código. Una razón para esto es que si no especifica un tipo de datos para un elemento de programación, el compilador de Visual Basic asigna el `Object` tipo. El código compilado que sea necesario convertir entre `Object` y otros tipos de datos, lo que reduce el rendimiento.  
  
## <a name="see-also"></a>Vea también

- [Procedimientos](./index.md)
- [Subprocedimientos](./sub-procedures.md)
- [Procedimientos de función](./function-procedures.md)
- [Cómo: Pasar argumentos a un procedimiento](./how-to-pass-arguments-to-a-procedure.md)
- [Paso de argumentos por valor y por referencia](./passing-arguments-by-value-and-by-reference.md)
- [Procedimientos recursivos](./recursive-procedures.md)
- [Sobrecarga de procedimientos](./procedure-overloading.md)
- [Objetos y clases](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [Programación orientada a objetos (Visual Basic)](../../concepts/object-oriented-programming.md)
