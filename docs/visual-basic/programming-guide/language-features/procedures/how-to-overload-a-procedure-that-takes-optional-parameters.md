---
title: Procedimiento Sobrecargar un procedimiento que toma parámetros opcionales (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], parameters
- procedure overloading [Visual Basic], optional parameters
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedure parameters
- procedures [Visual Basic], overloading
- procedures [Visual Basic], multiple versions
ms.assetid: 825f9d56-4cde-43fd-993a-b9171717e2eb
ms.openlocfilehash: 4374a229392d51b67c99210da91ae05dd3342e96
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/31/2019
ms.locfileid: "66424057"
---
# <a name="how-to-overload-a-procedure-that-takes-optional-parameters-visual-basic"></a>Procedimiento Sobrecargar un procedimiento que toma parámetros opcionales (Visual Basic)
Si un procedimiento tiene uno o varios [opcional](../../../../visual-basic/language-reference/modifiers/optional.md) parámetros, no se puede definir una versión sobrecargada que coincida con alguno de sus sobrecargas implícitas. Para obtener más información, vea "Implícita sobrecargas para parámetros opcionales" en [consideraciones en sobrecarga de procedimientos](./considerations-in-overloading-procedures.md).  
  
## <a name="one-optional-parameter"></a>Un parámetro opcional  
  
#### <a name="to-overload-a-procedure-that-takes-one-optional-parameter"></a>Sobrecargar un procedimiento que toma un parámetro opcional  
  
1. Escribir un `Sub` o `Function` instrucción de declaración que incluye el parámetro opcional en la lista de parámetros. No utilice el `Optional` palabra clave en esta versión sobrecargada.  
  
2. Preceder el `Sub` o `Function` palabra clave con el [sobrecargas](../../../../visual-basic/language-reference/modifiers/overloads.md) palabra clave.  
  
3. Escribir el código del procedimiento que se debe ejecutar cuando el código de llamada proporciona el argumento opcional.  
  
4. Finalice el procedimiento con el `End Sub` o `End Function` instrucción según corresponda.  
  
5. Escribir una segunda instrucción de declaración que es idéntica a la primera declaración, salvo que no incluye el parámetro opcional en la lista de parámetros.  
  
6. Escribir el código del procedimiento que se debe ejecutar cuando el código de llamada no proporciona el argumento opcional. Finalice el procedimiento con el `End Sub` o `End Function` instrucción según corresponda.  
  
     El ejemplo siguiente muestra un procedimiento definido con un parámetro opcional, un conjunto equivalente de dos procedimientos sobrecargados y, finalmente, ejemplos de versiones sobrecargadas válidas y no válidos.  
  
     [!code-vb[VbVbcnProcedures#59](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#59)]  
  
     [!code-vb[VbVbcnProcedures#60](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#60)]  
  
     [!code-vb[VbVbcnProcedures#61](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#61)]  
  
## <a name="multiple-optional-parameters"></a>Varios parámetros opcionales  
 Para obtener un procedimiento con más de un parámetro opcional, normalmente necesita más de dos versiones sobrecargadas. Por ejemplo, si hay dos parámetros opcionales, y el código de llamada puede proporcionar u omitir cada uno de ellos independientemente de la otra, necesitará cuatro versiones sobrecargadas, uno para cada combinación posible de los argumentos proporcionados.  
  
 A medida que aumenta el número de parámetros opcionales, aumenta la complejidad de la sobrecarga. A menos que algunas combinaciones de argumentos proporcionados no son aceptables, para los parámetros opcionales de N necesita 2 ^ N versiones sobrecargadas. Según la naturaleza del procedimiento, es posible que la claridad de la lógica de justifica el esfuerzo adicional de definir todas las versiones sobrecargadas.  
  
#### <a name="to-overload-a-procedure-that-takes-more-than-one-optional-parameter"></a>Sobrecargar un procedimiento que toma más de un parámetro opcional  
  
1. Determine qué combinaciones de argumentos opcionales proporcionados son aceptables para la lógica del procedimiento. Si un parámetro opcional que depende de otro, podría surgir una combinación inaceptable. Por ejemplo, si un parámetro acepta el nombre de una persona y otro acepta la edad de la persona, una combinación de argumentos que proporcione la edad pero omita el nombre no es aceptable.  
  
2. Para cada combinación aceptable de argumentos opcionales proporcionados, escribir un `Sub` o `Function` instrucción de declaración que define la lista de parámetros correspondientes. No utilice el `Optional` palabra clave.  
  
3. En cada declaración, anteponga la `Sub` o `Function` palabra clave con el [sobrecargas](../../../../visual-basic/language-reference/modifiers/overloads.md) palabra clave.  
  
4. Después de cada declaración, escriba el código de procedimiento que se debe ejecutar cuando el código de llamada proporciona una lista de argumentos correspondientes a la lista de parámetros de declaración.  
  
5. Finalizar cada procedimiento con el `End Sub` o `End Function` instrucción según corresponda.  
  
## <a name="see-also"></a>Vea también

- [Procedimientos](./index.md)
- [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)
- [Parámetros opcionales](./optional-parameters.md)
- [Matrices de parámetros](./parameter-arrays.md)
- [Sobrecarga de procedimientos](./procedure-overloading.md)
- [Solución de problemas de procedimientos](./troubleshooting-procedures.md)
- [Cómo: Definir varias versiones de un procedimiento](./how-to-define-multiple-versions-of-a-procedure.md)
- [Cómo: Llamar a un procedimiento sobrecargado](./how-to-call-an-overloaded-procedure.md)
- [Cómo: Sobrecargar un procedimiento que toma un número indefinido de parámetros](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [Resolución de sobrecargas](./overload-resolution.md)
