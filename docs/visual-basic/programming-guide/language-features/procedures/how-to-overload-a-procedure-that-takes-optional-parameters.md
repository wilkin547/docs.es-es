---
description: 'Más información acerca de cómo: sobrecargar un procedimiento que toma parámetros opcionales (Visual Basic)'
title: Procedimiento para sobrecargar un procedimiento que toma parámetros opcionales
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
ms.openlocfilehash: dccef9d27c08ede2f35edc02c8bd5116aa6969b2
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100472949"
---
# <a name="how-to-overload-a-procedure-that-takes-optional-parameters-visual-basic"></a>Cómo: Sobrecargar un procedimiento que toma parámetros opcionales (Visual Basic)

Si un procedimiento tiene uno o varios parámetros [opcionales](../../../language-reference/modifiers/optional.md) , no se puede definir una versión sobrecargada que coincida con cualquiera de sus sobrecargas implícitas. Para obtener más información, vea "sobrecargas implícitas para los parámetros opcionales" en [consideraciones sobre la sobrecarga de procedimientos](./considerations-in-overloading-procedures.md).  
  
## <a name="one-optional-parameter"></a>Un parámetro opcional  
  
#### <a name="to-overload-a-procedure-that-takes-one-optional-parameter"></a>Para sobrecargar un procedimiento que toma un parámetro opcional  
  
1. Escriba una `Sub` `Function` instrucción de declaración o que incluya el parámetro opcional en la lista de parámetros. No use la `Optional` palabra clave en esta versión sobrecargada.  
  
2. Preceda `Sub` `Function` a la palabra clave o con la palabra clave [Overloads](../../../language-reference/modifiers/overloads.md) .  
  
3. Escriba el código de procedimiento que debe ejecutarse cuando el código que realiza la llamada proporcione el argumento opcional.  
  
4. Finalice el procedimiento con la `End Sub` `End Function` instrucción o según corresponda.  
  
5. Escriba una segunda instrucción de declaración que sea idéntica a la primera declaración, salvo que no incluya el parámetro opcional en la lista de parámetros.  
  
6. Escriba el código de procedimiento que debe ejecutarse cuando el código de llamada no proporcione el argumento opcional. Finalice el procedimiento con la `End Sub` `End Function` instrucción o según corresponda.  
  
     En el ejemplo siguiente se muestra un procedimiento definido con un parámetro opcional, un conjunto equivalente de dos procedimientos sobrecargados y, por último, ejemplos de versiones sobrecargadas y no válidas.  
  
     [!code-vb[VbVbcnProcedures#59](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#59)]  
  
     [!code-vb[VbVbcnProcedures#60](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#60)]  
  
     [!code-vb[VbVbcnProcedures#61](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#61)]  
  
## <a name="multiple-optional-parameters"></a>Varios parámetros opcionales  

 Para un procedimiento con más de un parámetro opcional, normalmente se necesitan más de dos versiones sobrecargadas. Por ejemplo, si hay dos parámetros opcionales y el código de llamada puede proporcionar u omitir cada uno de ellos de forma independiente, se necesitan cuatro versiones sobrecargadas, una para cada combinación posible de argumentos proporcionados.  
  
 A medida que aumenta el número de parámetros opcionales, aumenta la complejidad de la sobrecarga. A menos que algunas combinaciones de los argumentos proporcionados no sean aceptables, para N parámetros opcionales necesita 2 ^ N versiones sobrecargadas. En función de la naturaleza del procedimiento, podría encontrar que la claridad de la lógica justifica el esfuerzo adicional de definir todas las versiones sobrecargadas.  
  
#### <a name="to-overload-a-procedure-that-takes-more-than-one-optional-parameter"></a>Para sobrecargar un procedimiento que toma más de un parámetro opcional  
  
1. Determine qué combinaciones de argumentos opcionales proporcionados son aceptables para la lógica del procedimiento. Podría producirse una combinación inaceptable si un parámetro opcional depende de otro. Por ejemplo, si un parámetro acepta el nombre de una persona y otro acepta la edad de la persona, una combinación de argumentos que proporcione la edad pero que omita el nombre es inaceptable.  
  
2. Para cada combinación aceptable de argumentos opcionales proporcionados, escriba `Sub` una `Function` instrucción de declaración o que defina la lista de parámetros correspondiente. No use la `Optional` palabra clave.  
  
3. En cada declaración, preceda `Sub` `Function` a la palabra clave o con la palabra clave [Overloads](../../../language-reference/modifiers/overloads.md) .  
  
4. Después de cada declaración, escriba el código de procedimiento que debe ejecutarse cuando el código de llamada proporciona una lista de argumentos correspondiente a la lista de parámetros de la declaración.  
  
5. Finalice cada procedimiento con la `End Sub` `End Function` instrucción o según corresponda.  
  
## <a name="see-also"></a>Consulte también

- [Procedimientos](./index.md)
- [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)
- [Parámetros opcionales](./optional-parameters.md)
- [Matrices de parámetros](./parameter-arrays.md)
- [Sobrecarga de procedimientos](./procedure-overloading.md)
- [Solución de problemas de procedimientos](./troubleshooting-procedures.md)
- [Procedimiento para definir varias versiones de un procedimiento](./how-to-define-multiple-versions-of-a-procedure.md)
- [Procedimiento para llamar a un procedimiento sobrecargado](./how-to-call-an-overloaded-procedure.md)
- [Procedimiento para sobrecargar un procedimiento que toma un número indefinido de parámetros](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [Overload Resolution](./overload-resolution.md)
