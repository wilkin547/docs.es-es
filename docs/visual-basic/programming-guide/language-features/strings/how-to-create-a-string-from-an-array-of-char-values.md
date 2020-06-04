---
title: Procedimiento para crear una cadena a partir de una matriz de valores de caracteres
ms.date: 07/20/2015
helpviewer_keywords:
- examples [Visual Basic], arrays
- examples [Visual Basic], Char data type
ms.assetid: 69f94e85-d57c-4ccc-a62a-426e829f5c5e
ms.openlocfilehash: d9ec897467f0caac0afc089a028516c0316a2bda
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410598"
---
# <a name="how-to-create-a-string-from-an-array-of-char-values-visual-basic"></a>Cómo: Crear una cadena a partir de una matriz de caracteres (Visual Basic)
En este ejemplo se crea la cadena "ABCD" a partir de caracteres individuales.  
  
## <a name="example"></a>Ejemplo  
 [!code-vb[VbVbalrStrings#61](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#61)]  
  
## <a name="compile-the-code"></a>Compilar el código  
 Este método no tiene requisitos especiales.  
  
 La sintaxis `"a"c` , en la que un solo `c` carácter sigue a un solo carácter entre comillas, se usa para crear un literal de carácter.  
  
## <a name="robust-programming"></a>Programación sólida  
 Los caracteres nulos (equivalentes a `Chr(0)` ) de la cadena conducen a resultados inesperados al usar la cadena. El carácter nulo se incluirá con la cadena, pero los caracteres que siguen al carácter nulo no se mostrarán en algunas situaciones.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.String>
- [Tipo de datos Char](../../../language-reference/data-types/char-data-type.md)
- [Tipos de datos](../data-types/index.md)
