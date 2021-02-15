---
description: 'Más información sobre: Cómo: crear una cadena a partir de una matriz de valores char (Visual Basic)'
title: Procedimiento para crear una cadena a partir de una matriz de valores de caracteres
ms.date: 07/20/2015
helpviewer_keywords:
- examples [Visual Basic], arrays
- examples [Visual Basic], Char data type
ms.assetid: 69f94e85-d57c-4ccc-a62a-426e829f5c5e
ms.openlocfilehash: 67b675f5f02c92b785e374b99f49248d43d12fb4
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100429837"
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
- [Tipo de datos](../data-types/index.md)
