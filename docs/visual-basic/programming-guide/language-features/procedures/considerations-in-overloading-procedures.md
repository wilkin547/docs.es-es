---
title: Consideraciones sobre la sobrecarga de procedimientos (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
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
caps.latest.revision: 26
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ac4bc47f9e781f83c7930efffedd40d9c25c2ec2
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="considerations-in-overloading-procedures-visual-basic"></a>Consideraciones sobre la sobrecarga de procedimientos (Visual Basic)
Cuando se sobrecarga un procedimiento, debe usar otro *firma* para cada versión sobrecargada. Esto suele significar que cada versión debe especificar una lista de parámetros distinta. Para obtener más información, vea "Firmas diferentes" en [sobrecarga de procedimientos](./procedure-overloading.md).  
  
 Puede sobrecargar un `Function` procedimiento con un `Sub` procedimiento y viceversa, siempre tienen firmas diferentes. Dos sobrecargas no pueden distinguirse sólo en que una tiene un valor devuelto y el otro no.  
  
 Puede sobrecargar una propiedad del mismo modo que se sobrecarga un procedimiento y con las mismas restricciones. Sin embargo, no se pueden sobrecargar un procedimiento con una propiedad, o viceversa.  
  
## <a name="alternatives-to-overloaded-versions"></a>Alternativas a las versiones sobrecargadas  
 A veces tienen alternativas a las versiones sobrecargadas, especialmente cuando la presencia de argumentos es opcional o su número es variable.  
  
 Tenga en cuenta que todos los lenguajes no admiten necesariamente los argumentos opcionales y matrices de parámetros están limitadas a Visual Basic. Si va a escribir un procedimiento que es probable que se llame desde código escrito en cualquiera de varios idiomas, las versiones sobrecargadas ofrecen la máxima flexibilidad.  
  
### <a name="overloads-and-optional-arguments"></a>Sobrecargas y argumentos opcionales  
 Cuando el código de llamada, opcionalmente, puede proporcionar u omitir uno o más argumentos, puede definir varias versiones sobrecargadas o utilizar parámetros opcionales.  
  
#### <a name="when-to-use-overloaded-versions"></a>Cuándo utilizar versiones sobrecargadas  
 Se puede pensar en definir una serie de versiones sobrecargadas en los casos siguientes:  
  
-   La lógica en el código de procedimiento es significativamente diferente dependiendo de si el código de llamada proporciona un argumento opcional o no.  
  
-   El código del procedimiento no puede probar de forma confiable si el código que realiza la llamada ha suministrado un argumento opcional. Este es el caso, por ejemplo, si no hay ningún candidato posible a un valor predeterminado que el código que realiza la llamada podría no se espera que proporcione.  
  
#### <a name="when-to-use-optional-parameters"></a>Cuándo utilizar parámetros opcionales  
 Es posible que prefiera uno o varios parámetros opcionales en los casos siguientes:  
  
-   La única acción necesaria cuando el código de llamada no proporciona un argumento opcional es establecer el parámetro en un valor predeterminado. En tal caso, el código del procedimiento puede ser menos complicado si define una única versión con uno o varios `Optional` parámetros.  
  
 Para obtener más información, consulte [parámetros opcionales](./optional-parameters.md).  
  
### <a name="overloads-and-paramarrays"></a>Las sobrecargas y matrices de parámetros  
 Cuando el código de llamada puede pasar un número variable de argumentos, puede definir varias versiones sobrecargadas o utilizar una matriz de parámetros.  
  
#### <a name="when-to-use-overloaded-versions"></a>Cuándo utilizar versiones sobrecargadas  
 Se puede pensar en definir una serie de versiones sobrecargadas en los casos siguientes:  
  
-   Sabrá que el código de llamada nunca pasa más de un número pequeño de valores a la matriz de parámetros.  
  
-   La lógica en el código de procedimiento es significativamente diferente dependiendo de cuántos valores que pasa el código de llamada.  
  
-   El código de llamada puede pasar valores de distintos tipos de datos.  
  
#### <a name="when-to-use-a-parameter-array"></a>Cuándo usar una matriz de parámetros  
 Se recomienda por un `ParamArray` parámetro en los casos siguientes:  
  
-   No es posible predecir cuántos valores puede pasar el código que realiza la llamada a la matriz de parámetros, y podría ser un número elevado.  
  
-   La lógica del procedimiento se presta a recorrer en iteración todos los valores que pasa el código de llamada, realizar esencialmente las mismas operaciones en cada valor.  
  
 Para obtener más información, consulte [matrices de parámetros](./parameter-arrays.md).  
  
## <a name="implicit-overloads-for-optional-parameters"></a>Sobrecargas implícitas para parámetros opcionales  
 Un procedimiento con un [opcional](../../../../visual-basic/language-reference/modifiers/optional.md) parámetro es equivalente a dos procedimientos sobrecargados, uno con el parámetro opcional y otro sin él. No se puede sobrecargar un procedimiento con una lista de parámetros que se corresponda con cualquiera de estos. Las declaraciones siguientes ilustran esto.  
  
 [!code-vb[VbVbcnProcedures#58](./codesnippet/VisualBasic/considerations-in-overloading-procedures_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#60](./codesnippet/VisualBasic/considerations-in-overloading-procedures_2.vb)]  
  
 [!code-vb[VbVbcnProcedures#61](./codesnippet/VisualBasic/considerations-in-overloading-procedures_3.vb)]  
  
 Para un procedimiento con más de un parámetro opcional, hay un conjunto de sobrecargas implícitas, llegado por una lógica similar al utilizado en el ejemplo anterior.  
  
## <a name="implicit-overloads-for-a-paramarray-parameter"></a>Sobrecargas implícitas para un parámetro ParamArray.  
 El compilador considera que un procedimiento con un [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) parámetro tenga un número infinito de sobrecargas, que se diferencian entre sí por lo que el código de llamada como se indica a continuación pasa a la matriz de parámetros:  
  
-   Una sobrecarga cuando el código de llamada no proporciona ningún argumento a la `ParamArray`  
  
-   Una sobrecarga cuando el código de llamada proporciona una matriz unidimensional de la `ParamArray` tipo de elemento  
  
-   Para cada entero positivo, una sobrecarga cuando el código de llamada proporciona ese número de argumentos, cada uno de los `ParamArray` tipo de elemento  
  
 Las siguientes declaraciones ilustran estas sobrecargas implícitas.  
  
 [!code-vb[VbVbcnProcedures#68](./codesnippet/VisualBasic/considerations-in-overloading-procedures_4.vb)]  
  
 [!code-vb[VbVbcnProcedures#70](./codesnippet/VisualBasic/considerations-in-overloading-procedures_5.vb)]  
  
 No se pueden sobrecargar un procedimiento así con una lista de parámetros que toma una matriz unidimensional de la matriz de parámetros. Sin embargo, puede utilizar las firmas de las otras sobrecargas implícitas. Las declaraciones siguientes ilustran esto.  
  
 [!code-vb[VbVbcnProcedures#71](./codesnippet/VisualBasic/considerations-in-overloading-procedures_6.vb)]  
  
## <a name="typeless-programming-as-an-alternative-to-overloading"></a>Programación sin tipos como alternativa a la sobrecarga  
 Si desea permitir que el código que realiza la llamada pasar tipos de datos diferentes a un parámetro, un enfoque alternativo es programación sin tipos. Puede establecer el tipo de conmutador para la comprobación `Off` con cualquiera el [Option Strict (instrucción)](../../../../visual-basic/language-reference/statements/option-strict-statement.md) o [/optionstrict](../../../../visual-basic/reference/command-line-compiler/optionstrict.md) opción del compilador. A continuación, no tienes que volver a declarar el tipo de datos del parámetro. Sin embargo, este enfoque tiene las siguientes desventajas en comparación con la sobrecarga:  
  
-   Programación sin tipos genera código de ejecución menos eficiente.  
  
-   Debe probar el procedimiento para cada tipo de datos que se prevé que se pasa.  
  
-   El compilador no puede notificar un error si el código que realiza la llamada pasa un tipo de datos que no es compatible con el procedimiento.  
  
## <a name="see-also"></a>Vea también  
 [Procedimientos](./index.md)  
 [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)  
 [Solución de problemas de procedimientos](./troubleshooting-procedures.md)  
 [Definir varias versiones de un procedimiento](./how-to-define-multiple-versions-of-a-procedure.md)  
 [Llamar a un procedimiento sobrecargado](./how-to-call-an-overloaded-procedure.md)  
 [Sobrecargar un procedimiento que toma parámetros opcionales](./how-to-overload-a-procedure-that-takes-optional-parameters.md)  
 [Sobrecargar un procedimiento que toma un número indefinido de parámetros](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)  
 [Resolución de sobrecargas](./overload-resolution.md)  
 [Sobrecargas](../../../../visual-basic/language-reference/modifiers/overloads.md)
