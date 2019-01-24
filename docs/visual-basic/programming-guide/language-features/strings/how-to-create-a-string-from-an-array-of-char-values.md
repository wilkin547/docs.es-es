---
title: Procedimiento Crear una cadena de una matriz de valores Char (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- examples [Visual Basic], arrays
- examples [Visual Basic], Char data type
ms.assetid: 69f94e85-d57c-4ccc-a62a-426e829f5c5e
ms.openlocfilehash: a067474d6b32589a34b031d5c3ea4e5a4be55834
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54611467"
---
# <a name="how-to-create-a-string-from-an-array-of-char-values-visual-basic"></a>Procedimiento Crear una cadena de una matriz de valores Char (Visual Basic)
Este ejemplo crea la cadena "abcd" de caracteres individuales.  
  
## <a name="example"></a>Ejemplo  
 [!code-vb[VbVbalrStrings#61](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-create-a-string-from-an-array-of-char-values_1.vb)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Este método no tiene ningún requisito especial.  
  
 La sintaxis `"a"c`, donde una sola `c` sigue un solo carácter entre comillas, se usa para crear un carácter literal.  
  
## <a name="robust-programming"></a>Programación sólida  
 Caracteres nulos (equivalente a `Chr(0)`) en la cadena de provocar resultados inesperados cuando se usa la cadena. El carácter nulo se incluirá con la cadena, pero no se mostrará después del carácter nulo de caracteres en algunas situaciones.  
  
## <a name="see-also"></a>Vea también
- <xref:System.String>
- [Char (tipo de datos)](../../../../visual-basic/language-reference/data-types/char-data-type.md)
- [Tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
