---
title: "Cómo: Crear una cadena a partir de una matriz de caracteres (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- examples [Visual Basic], arrays
- examples [Visual Basic], Char data type
ms.assetid: 69f94e85-d57c-4ccc-a62a-426e829f5c5e
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 06e5c6923c26f3cb84b38475d6680523853d727d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-string-from-an-array-of-char-values-visual-basic"></a>Cómo: Crear una cadena a partir de una matriz de caracteres (Visual Basic)
Este ejemplo crea la cadena "abcd" de caracteres individuales.  
  
## <a name="example"></a>Ejemplo  
 [!code-vb[VbVbalrStrings#61](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-create-a-string-from-an-array-of-char-values_1.vb)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Este método no tiene ningún requisito especial.  
  
 La sintaxis `"a"c`, donde una sola `c` sigue un carácter individual entre comillas, se utiliza para crear un carácter literal.  
  
## <a name="robust-programming"></a>Programación sólida  
 Caracteres null (equivalente a `Chr(0)`) en la cadena de provocar resultados inesperados cuando se usa la cadena. El carácter null se incluirá con la cadena, pero los caracteres que siguen el carácter null no se mostrará en algunas situaciones.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.String>  
 [Char (tipo de datos)](../../../../visual-basic/language-reference/data-types/char-data-type.md)  
 [Tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
