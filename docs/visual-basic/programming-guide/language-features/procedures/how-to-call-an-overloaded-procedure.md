---
title: "Cómo: llamar a un procedimiento sobrecargado (Visual Basic) | Documentos de Microsoft"
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
- Visual Basic code, procedures
- procedures, overloading
- procedures, calling
- procedures, multiple versions
- procedure calls, overloaded
ms.assetid: 3bb331fb-f6bc-406f-9ca0-9609b497014c
caps.latest.revision: 12
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
ms.openlocfilehash: 0da83aa63bf013d841f2a01a535726f3b03497a1
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-call-an-overloaded-procedure-visual-basic"></a>Cómo: Llamar a un procedimiento sobrecargado (Visual Basic)
La ventaja de sobrecargar un procedimiento radica en la flexibilidad de la llamada. El código de llamada puede obtener la información que necesita para pasar al procedimiento y, a continuación, llamar a un único nombre de procedimiento, independientemente de los argumentos está pasando.  
  
### <a name="to-call-a-procedure-that-has-more-than-one-version-defined"></a>Llamar a un procedimiento que tiene más de una versión definida  
  
1.  En el código de llamada, determine qué datos se deben pasar al procedimiento.  
  
2.  Escribir la llamada al procedimiento de la manera normal, presentación de datos en la lista de argumentos. Asegúrese de que los argumentos coincidan con la lista de parámetros de una de las versiones definidas para el procedimiento.  
  
3.  No es necesario que determinar qué versión del procedimiento al que llamar. [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]pasa el control a la versión correspondiente de la lista de argumentos.  
  
     El ejemplo siguiente se llama el `post` procedimiento declarado en [Cómo: definir varias versiones de un procedimiento](./how-to-define-multiple-versions-of-a-procedure.md). Obtiene la identificación del cliente, se determina si se trata de un `String` o `Integer`y, a continuación, en cualquier caso, llama el mismo procedimiento.  
  
     [!code-vb[VbVbcnProcedures nº&56;](./codesnippet/VisualBasic/how-to-call-an-overloaded-procedure_1.vb)]  
  
     [!code-vb[VbVbcnProcedures&#57;](./codesnippet/VisualBasic/how-to-call-an-overloaded-procedure_2.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Procedimientos](./index.md)   
 [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)   
 [Sobrecarga de procedimientos](./procedure-overloading.md)   
 [Procedimientos de solución de problemas](./troubleshooting-procedures.md)   
 [Cómo: definir varias versiones de un procedimiento](./how-to-define-multiple-versions-of-a-procedure.md)   
 [Cómo: sobrecargar un procedimiento que toma parámetros opcionales](./how-to-overload-a-procedure-that-takes-optional-parameters.md)   
 [Cómo: sobrecargar un procedimiento que toma un número indefinido de parámetros](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)   
 [Consideraciones sobre la sobrecarga de procedimientos](./considerations-in-overloading-procedures.md)   
 [Resolución de sobrecarga](./overload-resolution.md)   
 [Sobrecargas](../../../../visual-basic/language-reference/modifiers/overloads.md)
