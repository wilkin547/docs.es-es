---
title: Acceso a cadenas basado en cero Acceso basado en una cadena en Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], indexing
ms.assetid: 0ed39f35-d68e-421d-ae14-460a5c0373b8
ms.openlocfilehash: cc8f286de41d7e44225e889e73ff3c7b1fdbd881
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2019
ms.locfileid: "65591748"
---
# <a name="zero-based-vs-one-based-string-access-in-visual-basic"></a>Acceso a cadenas basado en cero Acceso basado en una cadena en Visual Basic
Este tema compara cómo Visual Basic y .NET Framework proporcionan acceso a los caracteres de una cadena. .NET Framework siempre proporciona acceso basado en cero para los caracteres en una cadena, mientras que Visual Basic proporciona acceso basado en cero y basado en uno, dependiendo de la función.  
  
## <a name="one-based"></a>Basado en uno  
 Para obtener un ejemplo de una función de Visual Basic basado en uno, tenga en cuenta el `Mid` función. Toma un argumento que indica la posición del carácter en el que comenzará la subcadena, empezando por la posición 1. .NET Framework <xref:System.String.Substring%2A?displayProperty=nameWithType> método toma un índice del carácter en la cadena en la que la subcadena se va a comenzar, empezando por la posición 0. Por lo tanto, si tiene una cadena "ABCDE", los caracteres individuales se numeran 1,2,3,4,5 para su uso con el `Mid` función, pero 0,1,2,3,4 para su uso con el <xref:System.String.Substring%2A?displayProperty=nameWithType> método.  
  
## <a name="zero-based"></a>Basado en cero  
 Para obtener un ejemplo de una función de Visual Basic basado en cero, considere la `Split` función. Divide una cadena y devuelve una matriz que contiene las subcadenas. .NET Framework <xref:System.String.Split%2A?displayProperty=nameWithType> método también divide una cadena y devuelve una matriz que contiene las subcadenas. Dado que el `Split` función y <xref:System.String.Split%2A> método devolver matrices de .NET Framework, deben ser basado en cero.  
  
## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.Strings.Mid%2A>
- <xref:Microsoft.VisualBasic.Strings.Split%2A>
- <xref:System.String.Substring%2A>
- <xref:System.String.Split%2A>
- [Introducción a las cadenas en Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
