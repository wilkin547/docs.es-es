---
title: Pasar argumentos por valor y por referencia (Visual Basic) | Documentos de Microsoft
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
- ByRef keyword, passing arguments by reference
- Visual Basic code, procedures
- passing arguments, by value or by reference
- ByVal keyword, passing arguments by value
- arguments [Visual Basic], passing by value or by reference
- argument passing, by value or by reference
ms.assetid: fd8a9de6-7178-44d5-a9bf-458d4ad907c2
caps.latest.revision: 23
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
ms.openlocfilehash: 56d1ceba14020ca7f3dc750c2318efd3e9586af0
ms.lasthandoff: 03/13/2017

---
# <a name="passing-arguments-by-value-and-by-reference-visual-basic"></a>Pasar argumentos por valor y por referencia (Visual Basic)
En [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], puede pasar un argumento a un procedimiento *por valor* o *por referencia*. Esto se conoce como el *mecanismo para pasar argumentos*, y determina si el procedimiento puede modificar el elemento de programación subyacente al argumento en el código de llamada. La declaración del procedimiento determina el mecanismo para pasar argumentos de cada parámetro especificando la [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) o [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) (palabra clave).  
  
## <a name="distinctions"></a>Diferencias  
 Al pasar un argumento a un procedimiento, tenga distintas condiciones que interactúan entre sí:  
  
-   Si el elemento de programación subyacente es modificable o no modificable  
  
-   Si el propio argumento es modificable o no modificable  
  
-   Si el argumento se pasa por valor o por referencia  
  
-   Si el tipo de datos de argumento es un tipo de valor o un tipo de referencia  
  
 Para obtener más información, consulte [diferencias entre modificables y no modificables argumentos](./differences-between-modifiable-and-nonmodifiable-arguments.md) y [las diferencias entre pasar un argumento por valor y por referencia](./differences-between-passing-an-argument-by-value-and-by-reference.md).  
  
## <a name="choice-of-passing-mechanism"></a>Elección del mecanismo para pasar argumentos  
 Debe elegir el mecanismo para pasar argumentos cuidadosamente para cada argumento.  
  
-   **Protección**. Para elegir entre los mecanismos de dos paso, el criterio más importante es la exposición de las variables para cambiar de llamada. La ventaja de pasar un argumento `ByRef` es que el procedimiento puede devolver un valor al código de llamada por medio del argumento. La ventaja de pasar un argumento `ByVal` es que protege a la variable se puede modificar el procedimiento.  
  
-   **Rendimiento**. Aunque el mecanismo de paso puede afectar al rendimiento del código, la diferencia es suele ser insignificante. Una excepción a esto es un tipo de valor que se pasa `ByVal`. En este caso, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] copia el contenido completo de datos del argumento. Por lo tanto, para un tipo de valor grande, como una estructura, puede ser más eficaz que lo pase `ByRef`.  
  
     Tipos de referencia, sólo el puntero a los datos es (cuatro bytes copiados en plataformas de 32 bits, ocho bytes en plataformas de 64 bits). Por lo tanto, puede pasar argumentos de tipo `String` o `Object` por valor sin perjudicar al rendimiento.  
  
## <a name="determination-of-the-passing-mechanism"></a>Determinación del mecanismo para pasar argumentos  
 La declaración del procedimiento especifica el mecanismo para pasar argumentos de cada parámetro. El código de llamada no puede reemplazar un `ByVal` mecanismo.  
  
 Si se declara un parámetro con `ByRef`, el código de llamada puede forzar al mecanismo para `ByVal` incluyendo el nombre del argumento entre paréntesis en la llamada. Para obtener más información, consulte [Cómo: forzar un argumento para pasar por valor](./how-to-force-an-argument-to-be-passed-by-value.md).  
  
 El valor predeterminado de [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] es pasar argumentos por valor.  
  
## <a name="when-to-pass-an-argument-by-value"></a>Cuándo se debe pasar un argumento por valor  
  
-   Si el elemento de código de llamada subyacente al argumento es un elemento no modificable, declare el parámetro correspondiente [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md). Ningún código puede cambiar el valor de un elemento no modificable.  
  
-   Si el elemento subyacente es modificable, pero no desea que el procedimiento pueda cambiar su valor, declare el parámetro `ByVal`. Solo el código de llamada puede cambiar el valor de un elemento modificable transferido por valor.  
  
## <a name="when-to-pass-an-argument-by-reference"></a>Cuándo se debe pasar un argumento por referencia  
  
-   Si el procedimiento necesita realmente cambiar el elemento subyacente en el código de llamada, declare el parámetro correspondiente [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md).  
  
-   Si la ejecución correcta del código depende del procedimiento que cambia el elemento subyacente en el código de llamada, declare el parámetro `ByRef`. Si se pasa por valor o si el código de llamada reemplaza el `ByRef` mecanismo para pasar argumentos encerrando el argumento entre paréntesis, la llamada al procedimiento podría producir resultados inesperados.  
  
## <a name="example"></a>Ejemplo  
  
### <a name="description"></a>Descripción  
 En el ejemplo siguiente se muestra cuándo pasar argumentos por valor y pasar por referencia. Procedimiento `Calculate` tiene un `ByVal` y un `ByRef` parámetro. Dada una tasa de interés, `rate`y la suma de dinero, `debt`, la tarea del procedimiento es calcular un nuevo valor para `debt` que es el resultado de aplicar la tasa de interés al valor original de `debt`. Porque `debt` es una `ByRef` parámetro, el nuevo total se refleja en el valor del argumento en el código de llamada que corresponde a `debt`. Parámetro `rate` es una `ByVal` parámetro porque `Calculate` no debe cambiar su valor.  
  
### <a name="code"></a>Código  
 [!code-vb[VbVbcnProcedures&#74;](./codesnippet/VisualBasic/passing-arguments-by-value-and-by-reference_1.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Procedimientos](./index.md)   
 [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)   
 [Cómo: pasar argumentos a un procedimiento](./how-to-pass-arguments-to-a-procedure.md)   
 [Cómo: cambiar el valor de un argumento de procedimiento](./how-to-change-the-value-of-a-procedure-argument.md)   
 [Cómo: proteger un argumento de procedimiento realicen cambios de valor](./how-to-protect-a-procedure-argument-against-value-changes.md)   
 [Cómo: forzar un argumento para pasar por valor](./how-to-force-an-argument-to-be-passed-by-value.md)   
 [Pasar argumentos por posición o por nombre](./passing-arguments-by-position-and-by-name.md)   
 [Tipos de valores y tipos de referencias](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
