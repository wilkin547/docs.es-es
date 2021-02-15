---
description: 'Más información acerca de cómo: llamar a un procedimiento sobrecargado (Visual Basic)'
title: Procedimiento para llamar a un procedimiento sobrecargado
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], overloading
- procedures [Visual Basic], calling
- procedures [Visual Basic], multiple versions
- procedure calls [Visual Basic], overloaded
ms.assetid: 3bb331fb-f6bc-406f-9ca0-9609b497014c
ms.openlocfilehash: 6a67a598bd4a42964fd8fc01bc22b1b919f5e2a9
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100472597"
---
# <a name="how-to-call-an-overloaded-procedure-visual-basic"></a>Cómo: Llamar a un procedimiento sobrecargado (Visual Basic)

La ventaja de sobrecargar un procedimiento es la flexibilidad de la llamada. El código de llamada puede obtener la información que necesita para pasar al procedimiento y, a continuación, llamar a un nombre de procedimiento único, independientemente de los argumentos que pase.  
  
### <a name="to-call-a-procedure-that-has-more-than-one-version-defined"></a>Para llamar a un procedimiento que tiene más de una versión definida  
  
1. En el código de llamada, determine qué datos se van a pasar al procedimiento.  
  
2. Escriba la llamada a procedimiento de la manera normal y presente los datos en la lista de argumentos. Asegúrese de que los argumentos coincidan con la lista de parámetros en una de las versiones definidas para el procedimiento.  
  
3. No es necesario determinar la versión del procedimiento que se va a llamar. Visual Basic pasa el control a la versión que coincida con la lista de argumentos.  
  
     En el ejemplo siguiente se llama al `post` procedimiento declarado en [Cómo: definir varias versiones de un procedimiento](./how-to-define-multiple-versions-of-a-procedure.md). Obtiene la identificación del cliente, determina si es `String` o `Integer` , y, en cualquier caso, llama al mismo procedimiento.  
  
     [!code-vb[VbVbcnProcedures#56](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#56)]  
  
     [!code-vb[VbVbcnProcedures#57](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#57)]  
  
## <a name="see-also"></a>Consulte también

- [Procedimientos](./index.md)
- [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)
- [Sobrecarga de procedimientos](./procedure-overloading.md)
- [Solución de problemas de procedimientos](./troubleshooting-procedures.md)
- [Procedimiento para definir varias versiones de un procedimiento](./how-to-define-multiple-versions-of-a-procedure.md)
- [Procedimiento para sobrecargar un procedimiento que toma parámetros opcionales](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [Procedimiento para sobrecargar un procedimiento que toma un número indefinido de parámetros](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [Consideraciones sobre la sobrecarga de procedimientos](./considerations-in-overloading-procedures.md)
- [Overload Resolution](./overload-resolution.md)
- [Sobrecargas](../../../language-reference/modifiers/overloads.md)
