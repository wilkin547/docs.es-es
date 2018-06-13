---
title: Se esperaba el fin de instrucción
ms.date: 07/20/2015
f1_keywords:
- bc30205
- vbc30205
helpviewer_keywords:
- BC30205
ms.assetid: 53c7f825-a737-4b76-a1fa-f67745b8bd40
ms.openlocfilehash: 7b91d13cbcb9d211d4ca18c8e48c7494bf6eccc6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33588085"
---
# <a name="end-of-statement-expected"></a>Se esperaba el fin de instrucción
La instrucción es sintácticamente completa, pero un elemento de programación adicional sigue al elemento que se completa la instrucción. Tiene un terminador de línea al final de cada instrucción.
  
 Un terminador de línea divide los caracteres de un archivo de código fuente de Visual Basic en líneas. Algunos ejemplos de terminadores de línea son el Unicode carro devuelto carácter (& HD), el Unicode avance de línea carácter (& HA), y seguido del carácter de avance de línea de Unicode del carácter de retorno de carro de Unicode. Para obtener más información acerca de los terminadores de línea, consulte el [especificación del lenguaje Visual Basic](../../../visual-basic/reference/language-specification/index.md).
  
 **Id. de error:** BC30205
  
## <a name="to-correct-this-error"></a>Para corregir este error
  
1.  Comprueba si dos instrucciones diferentes inadvertidamente se han colocado en la misma línea.
  
2.  Inserte un terminador de línea después del elemento que se completa la instrucción.
  
## <a name="see-also"></a>Vea también  
 [Interrumpir y combinar instrucciones en código](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)  
 [Instrucciones](../../../visual-basic/programming-guide/language-features/statements.md)
