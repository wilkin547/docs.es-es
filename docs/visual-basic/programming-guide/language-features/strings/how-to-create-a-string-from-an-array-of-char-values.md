---
title: 'Cómo: Crear una cadena a partir de una matriz de caracteres'
ms.date: 07/20/2015
helpviewer_keywords:
- examples [Visual Basic], arrays
- examples [Visual Basic], Char data type
ms.assetid: 69f94e85-d57c-4ccc-a62a-426e829f5c5e
ms.openlocfilehash: bf37ceba901e712df10ad4b39f9ad74194843136
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75346769"
---
# <a name="how-to-create-a-string-from-an-array-of-char-values-visual-basic"></a>Cómo: Crear una cadena a partir de una matriz de caracteres (Visual Basic)
En este ejemplo se crea la cadena "ABCD" a partir de caracteres individuales.  
  
## <a name="example"></a>Ejemplo  
 [!code-vb[VbVbalrStrings#61](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#61)]  
  
## <a name="compile-the-code"></a>Compilar el código  
 Este método no tiene requisitos especiales.  
  
 La sintaxis `"a"c`, donde un solo `c` sigue un carácter único entre comillas, se usa para crear un literal de carácter.  
  
## <a name="robust-programming"></a>Programación sólida  
 Los caracteres nulos (equivalentes a `Chr(0)`) en la cadena conducen a resultados inesperados al usar la cadena. El carácter nulo se incluirá con la cadena, pero los caracteres que siguen al carácter nulo no se mostrarán en algunas situaciones.  
  
## <a name="see-also"></a>Vea también

- <xref:System.String>
- [Char (tipo de datos)](../../../../visual-basic/language-reference/data-types/char-data-type.md)
- [Tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
