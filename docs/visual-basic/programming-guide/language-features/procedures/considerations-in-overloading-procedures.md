---
title: Consideraciones sobre la sobrecarga de procedimientos
ms.date: 07/20/2015
helpviewer_keywords:
- signatures [Visual Basic], ParamArray arguments
- ParamArray keyword [Visual Basic], parameter arrays
- ParamArray keyword [Visual Basic], arguments and signatures
- function overloading [Visual Basic], implicit overloads for ParamArray
- ParamArray keyword [Visual Basic], signatures
- Visual Basic code, procedures
- arguments [Visual Basic], parameter arrays
- procedures [Visual Basic], overloading
- parameters [Visual Basic], lists
- function overloading [Visual Basic], typeless programming
- typeless programming
- function overloading [Visual Basic], restrictions
- arguments [Visual Basic], optional
- optional arguments [Visual Basic], overloading
- signatures [Visual Basic], procedure
- parameter lists [Visual Basic]
- parameter arrays [Visual Basic], overloading arguments
- Visual Basic code, parameter lists
- procedure overloading [Visual Basic], considerations
- Option Explicit statement [Visual Basic]
- restrictions [Visual Basic], overloading procedures
- procedures [Visual Basic], parameter lists
ms.assetid: a2001248-10d0-42c5-b0ce-eeedc987319f
ms.openlocfilehash: 6197fa4041a22944542b2657e35bc293a6e5c244
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91075062"
---
# <a name="considerations-in-overloading-procedures-visual-basic"></a>Consideraciones sobre la sobrecarga de procedimientos (Visual Basic)

Al sobrecargar un procedimiento, debe usar una *firma* diferente para cada versión sobrecargada. Normalmente, esto significa que cada versión debe especificar una lista de parámetros diferente. Para obtener más información, vea "firma diferente" en [sobrecarga de procedimientos](./procedure-overloading.md).  
  
 Puede sobrecargar un `Function` procedimiento con un `Sub` procedimiento y viceversa, siempre que tengan firmas diferentes. Dos sobrecargas no pueden diferir solo en que una tenga un valor devuelto y la otra no.  
  
 Puede sobrecargar una propiedad de la misma manera que sobrecarga un procedimiento y con las mismas restricciones. Sin embargo, no se puede sobrecargar un procedimiento con una propiedad, o viceversa.  
  
## <a name="alternatives-to-overloaded-versions"></a>Alternativas a las versiones sobrecargadas  

 A veces tiene alternativas a las versiones sobrecargadas, especialmente cuando la presencia de argumentos es opcional o su número es variable.  
  
 Tenga en cuenta que los argumentos opcionales no se admiten necesariamente en todos los lenguajes, y las matrices de parámetros se limitan a Visual Basic. Si está escribiendo un procedimiento que es probable que se llame desde el código escrito en cualquiera de los distintos lenguajes, las versiones sobrecargadas ofrecen la máxima flexibilidad.  
  
### <a name="overloads-and-optional-arguments"></a>Sobrecargas y argumentos opcionales  

 Cuando el código de llamada puede proporcionar u omitir uno o más argumentos de manera opcional, puede definir varias versiones sobrecargadas o usar parámetros opcionales.  
  
#### <a name="when-to-use-overloaded-versions"></a>Cuándo usar versiones sobrecargadas  

 Puede considerar la posibilidad de definir una serie de versiones sobrecargadas en los casos siguientes:  
  
- La lógica en el código del procedimiento es significativamente diferente en función de si el código de llamada proporciona un argumento opcional o no.  
  
- El código de procedimiento no puede comprobar de forma confiable si el código de llamada ha proporcionado un argumento opcional. Este es el caso, por ejemplo, si no hay ningún candidato posible para un valor predeterminado que el código de llamada no se pudiera esperar proporcionar.  
  
#### <a name="when-to-use-optional-parameters"></a>Cuándo usar parámetros opcionales  

 Podría preferir uno o varios parámetros opcionales en los casos siguientes:  
  
- La única acción necesaria cuando el código de llamada no proporciona un argumento opcional es establecer el parámetro en un valor predeterminado. En tal caso, el código de procedimiento puede ser menos complicado si se define una versión única con uno o más `Optional` parámetros.  
  
 Para obtener más información, vea [parámetros opcionales](./optional-parameters.md).  
  
### <a name="overloads-and-paramarrays"></a>Sobrecargas y ParamArray  

 Cuando el código de llamada puede pasar un número variable de argumentos, puede definir varias versiones sobrecargadas o utilizar una matriz de parámetros.  
  
#### <a name="when-to-use-overloaded-versions"></a>Cuándo usar versiones sobrecargadas  

 Puede considerar la posibilidad de definir una serie de versiones sobrecargadas en los casos siguientes:  
  
- Sabe que el código de llamada nunca pasa más de un número pequeño de valores a la matriz de parámetros.  
  
- La lógica en el código del procedimiento es significativamente diferente en función del número de valores que pase el código de llamada.  
  
- El código de llamada puede pasar valores de tipos de datos diferentes.  
  
#### <a name="when-to-use-a-parameter-array"></a>Cuándo usar una matriz de parámetros  

 Un parámetro se sirve mejor `ParamArray` en los casos siguientes:  
  
- No es posible predecir cuántos valores puede pasar el código de llamada a la matriz de parámetros y podría ser un número grande.  
  
- La lógica del procedimiento se presta a recorrer en iteración todos los valores que pasa el código que realiza la llamada, con lo que se realizan esencialmente las mismas operaciones en cada valor.  
  
 Para obtener más información, consulte [matrices de parámetros](./parameter-arrays.md).  
  
## <a name="implicit-overloads-for-optional-parameters"></a>Sobrecargas implícitas para los parámetros opcionales  

 Un procedimiento con un parámetro [opcional](../../../language-reference/modifiers/optional.md) equivale a dos procedimientos sobrecargados, uno con el parámetro opcional y otro sin él. No se puede sobrecargar este procedimiento con una lista de parámetros correspondiente a cualquiera de ellos. Las declaraciones siguientes muestran esto.  
  
 [!code-vb[VbVbcnProcedures#58](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#58)]  
  
 [!code-vb[VbVbcnProcedures#60](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#60)]  
  
 [!code-vb[VbVbcnProcedures#61](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#61)]  
  
 En el caso de un procedimiento con más de un parámetro opcional, existe un conjunto de sobrecargas IMPLÍCITAS, que llegó a través de una lógica similar a la del ejemplo anterior.  
  
## <a name="implicit-overloads-for-a-paramarray-parameter"></a>Sobrecargas implícitas para un parámetro paramarray  

 El compilador considera que un procedimiento con un parámetro [ParamArray](../../../language-reference/modifiers/paramarray.md) tiene un número infinito de sobrecargas, que difieren entre sí en lo que el código de llamada pasa a la matriz de parámetros, como se indica a continuación:  
  
- Una sobrecarga para cuando el código de llamada no proporciona un argumento al parámetro `ParamArray`  
  
- Una sobrecarga para cuando el código de llamada proporciona una matriz unidimensional del `ParamArray` tipo de elemento.  
  
- Para cada entero positivo, una sobrecarga para cuando el código de llamada proporciona ese número de argumentos, cada uno de los `ParamArray` tipos de elemento.  
  
 Las declaraciones siguientes muestran estas sobrecargas implícitas.  
  
 [!code-vb[VbVbcnProcedures#68](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#68)]  
  
 [!code-vb[VbVbcnProcedures#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#70)]  
  
 No se puede sobrecargar este procedimiento con una lista de parámetros que tome una matriz unidimensional para la matriz de parámetros. Sin embargo, puede utilizar las firmas de las otras sobrecargas implícitas. Las declaraciones siguientes muestran esto.  
  
 [!code-vb[VbVbcnProcedures#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#71)]  
  
## <a name="typeless-programming-as-an-alternative-to-overloading"></a>Programación sin tipos como alternativa a la sobrecarga  

 Si desea permitir que el código de llamada pase tipos de datos diferentes a un parámetro, un enfoque alternativo es la programación sin tipos. Puede establecer el modificador de comprobación de tipos en `Off` con la [instrucción Option Strict](../../../language-reference/statements/option-strict-statement.md) o la opción del compilador [-OptionStrict](../../../reference/command-line-compiler/optionstrict.md) . No es necesario declarar el tipo de datos del parámetro. Sin embargo, este enfoque tiene las siguientes desventajas en comparación con la sobrecarga:  
  
- La programación sin tipos genera código de ejecución menos eficaz.  
  
- El procedimiento debe comprobar todos los tipos de datos que prevé que se pasan.  
  
- El compilador no puede indicar un error si el código de llamada pasa un tipo de datos no admitido por el procedimiento.  
  
## <a name="see-also"></a>Vea también

- [Procedimientos](./index.md)
- [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)
- [Solución de problemas de procedimientos](./troubleshooting-procedures.md)
- [Procedimiento para definir varias versiones de un procedimiento](./how-to-define-multiple-versions-of-a-procedure.md)
- [Procedimiento para llamar a un procedimiento sobrecargado](./how-to-call-an-overloaded-procedure.md)
- [Procedimiento para sobrecargar un procedimiento que toma parámetros opcionales](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [Procedimiento para sobrecargar un procedimiento que toma un número indefinido de parámetros](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [Overload Resolution](./overload-resolution.md)
- [Sobrecargas](../../../language-reference/modifiers/overloads.md)
