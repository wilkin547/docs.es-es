---
title: Procedimiento para crear una cadena a partir de una matriz de valores de caracteres
ms.date: 07/20/2015
helpviewer_keywords:
- examples [Visual Basic], arrays
- examples [Visual Basic], Char data type
ms.assetid: 69f94e85-d57c-4ccc-a62a-426e829f5c5e
ms.openlocfilehash: 08ad2f1c9455853e92533a7f00726c73b6adb87e
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91071162"
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
  
## <a name="see-also"></a>Vea también

- <xref:System.String>
- [Tipo de datos Char](../../../language-reference/data-types/char-data-type.md)
- [Tipo de datos](../data-types/index.md)
