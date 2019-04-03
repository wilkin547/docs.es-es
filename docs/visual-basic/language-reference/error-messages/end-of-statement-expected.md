---
title: Se esperaba el fin de instrucción
ms.date: 07/20/2015
f1_keywords:
- bc30205
- vbc30205
helpviewer_keywords:
- BC30205
ms.assetid: 53c7f825-a737-4b76-a1fa-f67745b8bd40
ms.openlocfilehash: ab6a4a0e6736e2af9c1fa0dd170b6aa4c42d9e4a
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58817159"
---
# <a name="end-of-statement-expected"></a>Se esperaba el fin de instrucción
La instrucción es sintácticamente completa, pero un elemento de programación adicional sigue al elemento que se complete la instrucción. Falta un terminador de línea al final de cada instrucción.
  
 Un terminador de línea divide los caracteres de un archivo de código fuente de Visual Basic en líneas. Ejemplos de terminadores de línea son el Unicode carro devuelto carácter (& HD), el Unicode avance de línea carácter (& alta disponibilidad), y seguido del carácter de avance de línea Unicode del carácter de retorno de carro Unicode. Para obtener más información acerca de los terminadores de línea, consulte el [especificación del lenguaje Visual Basic](~/_vblang/spec/lexical-grammar.md#line-terminators).
  
 **Identificador de error:** BC30205
  
## <a name="to-correct-this-error"></a>Para corregir este error
  
1.  Comprueba si dos instrucciones diferentes se colocaron en la misma línea.
  
2.  Insertar un terminador de línea después del elemento que se complete la instrucción.
  
## <a name="see-also"></a>Vea también

- [Cómo: Interrumpir y combinar instrucciones en código](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
- [Instrucciones](../../../visual-basic/programming-guide/language-features/statements.md)
