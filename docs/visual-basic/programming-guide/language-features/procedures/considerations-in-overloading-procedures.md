---
title: Consideraciones sobre la sobrecarga de procedimientos (Visual Basic) | Documentos de Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- signatures, ParamArray arguments
- ParamArray keyword, parameter arrays
- ParamArray keyword, arguments and signatures
- function overloading, implicit overloads for ParamArray
- ParamArray keyword, signatures
- Visual Basic code, procedures
- arguments [Visual Basic], parameter arrays
- procedures, overloading
- parameters, lists
- function overloading, typeless programming
- typeless programming
- function overloading, restrictions
- arguments [Visual Basic], optional
- optional arguments, overloading
- signatures, procedure
- parameter lists
- parameter arrays, overloading arguments
- Visual Basic code, parameter lists
- procedure overloading, considerations
- Option Explicit statement
- restrictions, overloading procedures
- procedures, parameter lists
ms.assetid: a2001248-10d0-42c5-b0ce-eeedc987319f
caps.latest.revision: 26
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: aa20cf367fba157f88afd861a4799540dcdecde1
ms.lasthandoff: 03/13/2017

---
# <a name="considerations-in-overloading-procedures-visual-basic"></a>Consideraciones sobre la sobrecarga de procedimientos (Visual Basic)
Cuando se sobrecarga un procedimiento, debe usar otro *firma* en cada versión sobrecargada. Normalmente esto significa que cada versión debe especificar una lista de parámetros distinta. Para obtener más información, vea "Firmas diferentes" en [sobrecarga de procedimientos](./procedure-overloading.md).  
  
 Puede sobrecargar una `Function` procedimiento con un `Sub` procedimiento y viceversa, siempre tienen firmas diferentes. Dos sobrecargas no pueden diferir únicamente en que uno tiene un valor devuelto y el otro no.  
  
 Se puede sobrecargar una propiedad del mismo modo que se sobrecarga un procedimiento y con las mismas restricciones. Sin embargo, no se pueden sobrecargar un procedimiento con una propiedad, o viceversa.  
  
## <a name="alternatives-to-overloaded-versions"></a>Alternativas a las versiones sobrecargadas  
 A veces, dispone de alternativas a las versiones sobrecargadas, especialmente cuando la presencia de argumentos es opcional o su número es variable.  
  
 Tenga en cuenta que los argumentos opcionales no se admiten necesariamente en todos los idiomas y matrices de parámetros están limitadas a [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]. Si está escribiendo un procedimiento que es probable que se llame desde código escrito en cualquiera de varios idiomas, las versiones sobrecargadas ofrecen la máxima flexibilidad.  
  
### <a name="overloads-and-optional-arguments"></a>Sobrecargas y argumentos opcionales  
 Cuando el código de llamada, opcionalmente, puede proporcionar u omitir uno o más argumentos, puede definir varias versiones sobrecargadas o utilizar parámetros opcionales.  
  
#### <a name="when-to-use-overloaded-versions"></a>Cuándo utilizar versiones sobrecargadas  
 Puede definir una serie de versiones sobrecargadas en los casos siguientes:  
  
-   La lógica en el código del procedimiento es significativamente diferente dependiendo de si el código de llamada proporciona un argumento opcional o no.  
  
-   El código del procedimiento no puede probar de forma confiable si el código llamado ha suministrado un argumento opcional. Este es el caso, por ejemplo, si no hay ningún candidato posible a un valor predeterminado que el código de llamada no podía proporcionar.  
  
#### <a name="when-to-use-optional-parameters"></a>Cuándo utilizar parámetros opcionales  
 Es posible que prefiera uno o más parámetros opcionales en los casos siguientes:  
  
-   La única acción necesaria cuando el código de llamada no proporciona un argumento opcional es establecer el parámetro a un valor predeterminado. En tal caso, el código del procedimiento puede resultar menos complicado si se define una única versión con uno o varios `Optional` parámetros.  
  
 Para obtener más información, consulte [parámetros opcionales](./optional-parameters.md).  
  
### <a name="overloads-and-paramarrays"></a>Sobrecargas y matrices de parámetros  
 Cuando el código de llamada puede pasar un número variable de argumentos, puede definir varias versiones sobrecargadas o utilizar una matriz de parámetros.  
  
#### <a name="when-to-use-overloaded-versions"></a>Cuándo utilizar versiones sobrecargadas  
 Puede definir una serie de versiones sobrecargadas en los casos siguientes:  
  
-   Sabrá que el código de llamada nunca pasa más que un pequeño número de valores para la matriz de parámetros.  
  
-   La lógica en el código del procedimiento difiere significativamente dependiendo de cuántos valores que pasa el código de llamada.  
  
-   El código de llamada puede pasar valores de distintos tipos de datos.  
  
#### <a name="when-to-use-a-parameter-array"></a>Cuándo usar una matriz de parámetros  
 Funcionan mejor mediante un `ParamArray` parámetro en los casos siguientes:  
  
-   No es posible predecir cuántos valores puede pasar el código de llamada a la matriz de parámetros, y podría ser un número elevado.  
  
-   La lógica del procedimiento se presta a recorrer en iteración todos los valores que pasa el código de llamada, realizar esencialmente las mismas operaciones en cada valor.  
  
 Para obtener más información, consulte [matrices de parámetros](./parameter-arrays.md).  
  
## <a name="implicit-overloads-for-optional-parameters"></a>Sobrecargas implícitas para parámetros opcionales  
 Un procedimiento con un [opcional](../../../../visual-basic/language-reference/modifiers/optional.md) parámetro equivale a dos procedimientos sobrecargados, uno con el parámetro opcional y otro sin él. No se puede sobrecargar un procedimiento con una lista de parámetros que se corresponda con cualquiera de estos. Las siguientes declaraciones ilustran esto.  
  
 [!code-vb[VbVbcnProcedures&#58;](./codesnippet/VisualBasic/considerations-in-overloading-procedures_1.vb)]  
  
 [!code-vb[60 VbVbcnProcedures](./codesnippet/VisualBasic/considerations-in-overloading-procedures_2.vb)]  
  
 [!code-vb[VbVbcnProcedures&#61;](./codesnippet/VisualBasic/considerations-in-overloading-procedures_3.vb)]  
  
 Para obtener un procedimiento con más de un parámetro opcional, hay un conjunto de sobrecargas implícitas, llegado por una lógica similar a la del ejemplo anterior.  
  
## <a name="implicit-overloads-for-a-paramarray-parameter"></a>Sobrecargas implícitas para un parámetro ParamArray  
 El compilador considera que un procedimiento con un [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) parámetro tenga un número infinito de sobrecargas, que se diferencian entre sí por lo que el código de llamada siguiente pasa a la matriz de parámetros:  
  
-   Una sobrecarga cuando el código de llamada no proporciona ningún argumento a la`ParamArray`  
  
-   Una sobrecarga cuando el código de llamada proporciona una matriz unidimensional de la `ParamArray` el tipo de elemento  
  
-   Para cada entero positivo, una sobrecarga cuando el código de llamada proporciona ese número de argumentos, cada uno de los `ParamArray` el tipo de elemento  
  
 Las siguientes declaraciones ilustran estas sobrecargas implícitas.  
  
 [!code-vb[VbVbcnProcedures&#68;](./codesnippet/VisualBasic/considerations-in-overloading-procedures_4.vb)]  
  
 [!code-vb[VbVbcnProcedures&#70;](./codesnippet/VisualBasic/considerations-in-overloading-procedures_5.vb)]  
  
 No se puede sobrecargar un procedimiento con una lista de parámetros que toma una matriz unidimensional para la matriz de parámetros. Sin embargo, puede utilizar las firmas de las otras sobrecargas implícitas. Las siguientes declaraciones ilustran esto.  
  
 [!code-vb[VbVbcnProcedures&#71;](./codesnippet/VisualBasic/considerations-in-overloading-procedures_6.vb)]  
  
## <a name="typeless-programming-as-an-alternative-to-overloading"></a>Programación sin tipos como alternativa a la sobrecarga  
 Si desea permitir que el código que realiza la llamada pasar tipos de datos diferentes a un parámetro, un enfoque alternativo es la programación sin tipos. Puede establecer el tipo de conmutador para la comprobación `Off` con cualquiera el [Option Strict (instrucción)](../../../../visual-basic/language-reference/statements/option-strict-statement.md) o [/optionstrict](../../../../visual-basic/reference/command-line-compiler/optionstrict.md) opción del compilador. A continuación, es necesario declarar el tipo de datos del parámetro. Sin embargo, este enfoque tiene las siguientes desventajas en comparación con la sobrecarga:  
  
-   Programación sin tipos genera código de ejecución menos eficiente.  
  
-   Debe probar el procedimiento para cada tipo de datos que anticipe que se pasa.  
  
-   El compilador no puede notificar un error si el código de llamada pasa un tipo de datos que el procedimiento no admite.  
  
## <a name="see-also"></a>Vea también  
 [Procedimientos](./index.md)   
 [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)   
 [Procedimientos de solución de problemas](./troubleshooting-procedures.md)   
 [Cómo: definir varias versiones de un procedimiento](./how-to-define-multiple-versions-of-a-procedure.md)   
 [Cómo: llamar a un procedimiento sobrecargado](./how-to-call-an-overloaded-procedure.md)   
 [Cómo: sobrecargar un procedimiento que toma parámetros opcionales](./how-to-overload-a-procedure-that-takes-optional-parameters.md)   
 [Cómo: sobrecargar un procedimiento que toma un número indefinido de parámetros](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)   
 [Resolución de sobrecarga](./overload-resolution.md)   
 [Sobrecargas](../../../../visual-basic/language-reference/modifiers/overloads.md)
