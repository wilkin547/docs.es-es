---
title: "Se esperaba el fin de instrucción"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30205
- vbc30205
helpviewer_keywords: BC30205
ms.assetid: 53c7f825-a737-4b76-a1fa-f67745b8bd40
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4934952015cb4871bcd90cef982eab5425b1617f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
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
