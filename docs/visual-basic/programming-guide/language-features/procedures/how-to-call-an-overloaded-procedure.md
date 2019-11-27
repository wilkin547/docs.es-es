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
La ventaja de sobrecargar un procedimiento es la flexibilidad de la llamada. El código de llamada puede obtener la información que necesita para pasar al procedimiento y, a continuación, llamar a un nombre de procedimiento único, independientemente de los argumentos que pase.  
  
### <a name="to-call-a-procedure-that-has-more-than-one-version-defined"></a>Para llamar a un procedimiento que tiene más de una versión definida  
  
1. En el código de llamada, determine qué datos se van a pasar al procedimiento.  
  
2. Escriba la llamada a procedimiento de la manera normal y presente los datos en la lista de argumentos. Asegúrese de que los argumentos coincidan con la lista de parámetros en una de las versiones definidas para el procedimiento.  
  
3. No es necesario determinar la versión del procedimiento que se va a llamar. Visual Basic pasa el control a la versión que coincida con la lista de argumentos.  
  
     En el ejemplo siguiente se llama al procedimiento `post` declarado en [Cómo: definir varias versiones de un procedimiento](./how-to-define-multiple-versions-of-a-procedure.md). Obtiene la identificación del cliente, determina si se trata de una `String` o un `Integer`y, en cualquier caso, llama al mismo procedimiento.  
  
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
