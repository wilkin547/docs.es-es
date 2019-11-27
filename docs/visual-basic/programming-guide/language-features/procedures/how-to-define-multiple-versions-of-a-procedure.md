---
title: 'Cómo: Definir varias versiones de un procedimiento'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedures [Visual Basic], overloading
- procedures [Visual Basic], multiple versions
- procedure overloading [Visual Basic], multiple versions
ms.assetid: 71ccdd66-1b00-4b66-bee4-6926c0d696f4
ms.openlocfilehash: 83e96e271f6613aa325d59a0ca2fce9fc69fe059
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350485"
---
# <a name="how-to-define-multiple-versions-of-a-procedure-visual-basic"></a>Cómo: Definir varias versiones de un procedimiento (Visual Basic)
Puede definir un procedimiento en varias versiones si lo *sobrecarga* , con el mismo nombre, pero con una lista de parámetros diferente para cada versión. El propósito de la sobrecarga es definir varias versiones estrechamente relacionadas de un procedimiento sin tener que diferenciarlas por nombre.  
  
 Para obtener más información, consulta [Procedure Overloading](./procedure-overloading.md).  
  
### <a name="to-define-multiple-versions-of-a-procedure"></a>Para definir varias versiones de un procedimiento  
  
1. Escriba una instrucción de declaración `Sub` o `Function` para cada versión del procedimiento que desee definir. Use el mismo nombre de procedimiento en cada declaración.  
  
2. Preceda a la palabra clave `Sub` o `Function` en cada declaración con la palabra clave [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) . Opcionalmente, puede omitir `Overloads` en las declaraciones, pero si lo incluye en cualquiera de las declaraciones, debe incluirlo en cada declaración.  
  
3. Después de cada instrucción de declaración, escriba el código de procedimiento para controlar el caso concreto en el que el código de llamada proporciona argumentos que coinciden con la lista de parámetros de la versión. No es necesario comprobar los parámetros que ha proporcionado el código de llamada. Visual Basic pasa el control a la versión correspondiente del procedimiento.  
  
4. Finalice cada versión del procedimiento con la instrucción `End Sub` o `End Function` según corresponda.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se define una `Sub` procedimiento para publicar una transacción en el saldo de un cliente. Usa la palabra clave `Overloads` para definir dos versiones del procedimiento, una que acepta el cliente por nombre y la otra por número de cuenta.  
  
 [!code-vb[VbVbcnProcedures#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#72)]  
  
 El código de llamada puede obtener la identificación del cliente como un `String` o un `Integer`y, a continuación, utilizar la misma instrucción de llamada en cualquier caso.  
  
 Para obtener información sobre cómo llamar a estas versiones del procedimiento `post`, consulte [Cómo: llamar a un procedimiento sobrecargado](./how-to-call-an-overloaded-procedure.md).  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Asegúrese de que cada una de las versiones sobrecargadas tiene el mismo nombre de procedimiento pero una lista de parámetros diferente.  
  
## <a name="see-also"></a>Vea también

- [Procedimientos](./index.md)
- [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)
- [Solución de problemas de procedimientos](./troubleshooting-procedures.md)
- [Sobrecargar un procedimiento que toma parámetros opcionales](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [Sobrecargar un procedimiento que toma un número indefinido de parámetros](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [Consideraciones sobre la sobrecarga de procedimientos](./considerations-in-overloading-procedures.md)
- [Resolución de sobrecargas](./overload-resolution.md)
