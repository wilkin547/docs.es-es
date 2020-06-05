---
title: Procedimiento para sobrecargar un procedimiento que toma un número indefinido de parámetros
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], parameters
- procedure overloading [Visual Basic], indefinite number of parameters
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedure parameters
- procedures [Visual Basic], overloading
- procedures [Visual Basic], multiple versions
ms.assetid: c7042de2-2422-4039-94e8-ac298896af69
ms.openlocfilehash: ddff8c8cd82593b7d89fb0847e56123c287e364b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84387886"
---
# <a name="how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters-visual-basic"></a>Cómo: Sobrecargar un procedimiento que toma un número indefinido de parámetros (Visual Basic)
Si un procedimiento tiene un parámetro [ParamArray](../../../language-reference/modifiers/paramarray.md) , no se puede definir una versión sobrecargada que tome una matriz unidimensional para la matriz de parámetros. Para obtener más información, vea "sobrecargas implícitas para un parámetro paramarray" en [consideraciones sobre la sobrecarga de procedimientos](./considerations-in-overloading-procedures.md).  
  
### <a name="to-overload-a-procedure-that-takes-a-variable-number-of-parameters"></a>Para sobrecargar un procedimiento que toma un número variable de parámetros  
  
1. Asegúrese de que el procedimiento y la lógica de llamada del código se benefician de las versiones sobrecargadas más que de un `ParamArray` parámetro. Vea "Overloads and ParamArray" en [consideraciones sobre la sobrecarga de procedimientos](./considerations-in-overloading-procedures.md).  
  
2. Determine qué números de valores proporcionados debe aceptar el procedimiento en la parte variable de la lista de parámetros. Esto podría incluir el caso de ningún valor y podría incluir el caso de una sola matriz unidimensional.  
  
3. Para cada número aceptable de valores proporcionados, escriba `Sub` una `Function` instrucción de declaración o que defina la lista de parámetros correspondiente. No use la `Optional` `ParamArray` palabra clave o en esta versión sobrecargada.  
  
4. En cada declaración, preceda `Sub` `Function` a la palabra clave o con la palabra clave [Overloads](../../../language-reference/modifiers/overloads.md) .  
  
5. Después de cada declaración, escriba el código de procedimiento que debe ejecutarse cuando el código de llamada suministre valores correspondientes a la lista de parámetros de la declaración.  
  
6. Finalice cada procedimiento con la `End Sub` `End Function` instrucción o según corresponda.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra un procedimiento definido con un parámetro [ParamArray](../../../language-reference/modifiers/paramarray.md) y, a continuación, un conjunto equivalente de procedimientos sobrecargados.  
  
 [!code-vb[VbVbcnProcedures#69](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#69)]  
  
 [!code-vb[VbVbcnProcedures#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#70)]  
  
 No se puede sobrecargar este procedimiento con una lista de parámetros que tome una matriz unidimensional para la matriz de parámetros. Sin embargo, puede utilizar las firmas de las otras sobrecargas implícitas. Las declaraciones siguientes muestran esto.  
  
 [!code-vb[VbVbcnProcedures#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#71)]  
  
 El código de las versiones sobrecargadas no tiene que comprobar si el código de llamada proporcionó uno o varios valores para el `ParamArray` parámetro, o si es así, cuántos. Visual Basic pasa el control a la versión que coincide con la lista de argumentos de llamada.  
  
## <a name="compile-the-code"></a>Compilar el código  
 Dado que un procedimiento con un `ParamArray` parámetro es equivalente a un conjunto de versiones sobrecargadas, no se puede sobrecargar este procedimiento con una lista de parámetros que se corresponda con cualquiera de estas sobrecargas implícitas. Para obtener más información, vea [consideraciones sobre la sobrecarga de procedimientos](./considerations-in-overloading-procedures.md).  
  
## <a name="net-framework-security"></a>Seguridad de .NET Framework  
 Siempre que se trata de una matriz que puede ser indefinidamente grande, existe el riesgo de que se produzca una gran cantidad de capacidad interna de la aplicación. Si acepta una matriz de parámetros, debe comprobar la longitud de la matriz que se le ha pasado al código de llamada y tomar los pasos adecuados si es demasiado grande para la aplicación.  
  
## <a name="see-also"></a>Consulte también

- [Procedimientos](./index.md)
- [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)
- [Parámetros opcionales](./optional-parameters.md)
- [Matrices de parámetros](./parameter-arrays.md)
- [Sobrecarga de procedimientos](./procedure-overloading.md)
- [Solución de problemas de procedimientos](./troubleshooting-procedures.md)
- [Procedimiento para definir varias versiones de un procedimiento](./how-to-define-multiple-versions-of-a-procedure.md)
- [Procedimiento para llamar a un procedimiento sobrecargado](./how-to-call-an-overloaded-procedure.md)
- [Procedimiento para sobrecargar un procedimiento que toma parámetros opcionales](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [Resolución de sobrecarga](./overload-resolution.md)
