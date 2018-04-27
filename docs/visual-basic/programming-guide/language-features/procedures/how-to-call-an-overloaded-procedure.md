---
title: 'Cómo: Llamar a un procedimiento sobrecargado (Visual Basic)'
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], overloading
- procedures [Visual Basic], calling
- procedures [Visual Basic], multiple versions
- procedure calls [Visual Basic], overloaded
ms.assetid: 3bb331fb-f6bc-406f-9ca0-9609b497014c
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5eca03de6b6dd2ca2b992196b1ae224f8fbf5068
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-call-an-overloaded-procedure-visual-basic"></a>Cómo: Llamar a un procedimiento sobrecargado (Visual Basic)
La ventaja de sobrecargar un procedimiento radica en la flexibilidad de la llamada. El código de llamada puede obtener la información que necesita para pasar al procedimiento y, a continuación, llamar a un único nombre de procedimiento, independientemente de los argumentos está pasando.  
  
### <a name="to-call-a-procedure-that-has-more-than-one-version-defined"></a>Llamar a un procedimiento que tiene más de una versión definida  
  
1.  En el código que realiza la llamada, determine qué datos se deben pasar al procedimiento.  
  
2.  Escribir la llamada al procedimiento de la manera normal, presentación de datos en la lista de argumentos. Asegúrese de que los argumentos coincidan con la lista de parámetros en una de las versiones definidas para el procedimiento.  
  
3.  No es necesario que determinar qué versión del procedimiento para llamar a. Visual Basic pasa el control a la versión que coincida con la lista de argumentos.  
  
     El ejemplo siguiente se llama el `post` procedimiento declarado en [Cómo: definir varias versiones de un procedimiento](./how-to-define-multiple-versions-of-a-procedure.md). Obtiene la identificación del cliente, se determina si se trata de un `String` o `Integer`y, a continuación, en cualquier caso llama el mismo procedimiento.  
  
     [!code-vb[VbVbcnProcedures#56](./codesnippet/VisualBasic/how-to-call-an-overloaded-procedure_1.vb)]  
  
     [!code-vb[VbVbcnProcedures#57](./codesnippet/VisualBasic/how-to-call-an-overloaded-procedure_2.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Procedimientos](./index.md)  
 [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)  
 [Sobrecarga de procedimientos](./procedure-overloading.md)  
 [Solución de problemas de procedimientos](./troubleshooting-procedures.md)  
 [Definir varias versiones de un procedimiento](./how-to-define-multiple-versions-of-a-procedure.md)  
 [Sobrecargar un procedimiento que toma parámetros opcionales](./how-to-overload-a-procedure-that-takes-optional-parameters.md)  
 [Sobrecargar un procedimiento que toma un número indefinido de parámetros](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)  
 [Consideraciones sobre la sobrecarga de procedimientos](./considerations-in-overloading-procedures.md)  
 [Resolución de sobrecargas](./overload-resolution.md)  
 [Sobrecargas](../../../../visual-basic/language-reference/modifiers/overloads.md)
