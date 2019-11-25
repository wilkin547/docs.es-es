---
title: 'Cómo: Llamar a un procedimiento sobrecargado'
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], overloading
- procedures [Visual Basic], calling
- procedures [Visual Basic], multiple versions
- procedure calls [Visual Basic], overloaded
ms.assetid: 3bb331fb-f6bc-406f-9ca0-9609b497014c
ms.openlocfilehash: d983f5f6183c33141079ed35171f7a73f254450f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74340206"
---
# <a name="how-to-call-an-overloaded-procedure-visual-basic"></a>Cómo: Llamar a un procedimiento sobrecargado (Visual Basic)
The advantage of overloading a procedure is in the flexibility of the call. The calling code can obtain the information it needs to pass to the procedure and then call a single procedure name, no matter what arguments it is passing.  
  
### <a name="to-call-a-procedure-that-has-more-than-one-version-defined"></a>To call a procedure that has more than one version defined  
  
1. In the calling code, determine which data to pass to the procedure.  
  
2. Write the procedure call in the normal way, presenting the data in the argument list. Be sure the arguments match the parameter list in one of the versions defined for the procedure.  
  
3. You do not have to determine which version of the procedure to call. Visual Basic passes control to the version matching your argument list.  
  
     The following example calls the `post` procedure declared in [How to: Define Multiple Versions of a Procedure](./how-to-define-multiple-versions-of-a-procedure.md). It obtains the customer identification, determines whether it is a `String` or an `Integer`, and then in either case calls the same procedure.  
  
     [!code-vb[VbVbcnProcedures#56](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#56)]  
  
     [!code-vb[VbVbcnProcedures#57](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#57)]  
  
## <a name="see-also"></a>Vea también

- [Procedimientos](./index.md)
- [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)
- [Sobrecarga de procedimientos](./procedure-overloading.md)
- [Solución de problemas de procedimientos](./troubleshooting-procedures.md)
- [Definir varias versiones de un procedimiento](./how-to-define-multiple-versions-of-a-procedure.md)
- [Sobrecargar un procedimiento que toma parámetros opcionales](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [Sobrecargar un procedimiento que toma un número indefinido de parámetros](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [Consideraciones sobre la sobrecarga de procedimientos](./considerations-in-overloading-procedures.md)
- [Resolución de sobrecargas](./overload-resolution.md)
- [Sobrecargas](../../../../visual-basic/language-reference/modifiers/overloads.md)
