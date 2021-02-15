---
description: 'Más información sobre: acceso a cadenas basadas en cero en Visual Basic'
title: Acceso a cadenas basado en cero y basado en uno
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], indexing
ms.assetid: 0ed39f35-d68e-421d-ae14-460a5c0373b8
ms.openlocfilehash: adab6954c4329ae0a547d136f26f6c3115dc5890
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100463837"
---
# <a name="zero-based-vs-one-based-string-access-in-visual-basic"></a>Acceso de base cero y de base uno a a cadenas en Visual Basic

En este tema se compara cómo Visual Basic y el .NET Framework proporcionan acceso a los caracteres de una cadena. El .NET Framework siempre proporciona acceso de base cero a los caracteres de una cadena, mientras que Visual Basic proporciona acceso basado en cero y basado en uno, en función de la función.  
  
## <a name="one-based"></a>One-Based  

 Para obtener un ejemplo de una función de Visual Basic basada en uno, considere la `Mid` función. Toma un argumento que indica la posición del carácter en el que comenzará la subcadena, comenzando por la posición 1. El <xref:System.String.Substring%2A?displayProperty=nameWithType> método .NET Framework toma un índice del carácter de la cadena en la que se va a iniciar la subcadena, empezando por la posición 0. Por lo tanto, si tiene una cadena "ABCDe", los caracteres individuales se numeran de 1, 2, 3, 4, 5 para su uso con la `Mid` función, pero 0, 1, 2, 3, 4 para su uso con el <xref:System.String.Substring%2A?displayProperty=nameWithType> método.  
  
## <a name="zero-based"></a>Zero-Based  

 Para obtener un ejemplo de una función de Visual Basic basado en cero, considere la `Split` función. Divide una cadena y devuelve una matriz que contiene las subcadenas. El <xref:System.String.Split%2A?displayProperty=nameWithType> método .NET Framework también divide una cadena y devuelve una matriz que contiene las subcadenas. Dado que la `Split` función y el <xref:System.String.Split%2A> método devuelven .NET Framework matrices, deben ser de base cero.  
  
## <a name="see-also"></a>Consulte también

- <xref:Microsoft.VisualBasic.Strings.Mid%2A>
- <xref:Microsoft.VisualBasic.Strings.Split%2A>
- <xref:System.String.Substring%2A>
- <xref:System.String.Split%2A>
- [Introducción a las cadenas en Visual Basic](introduction-to-strings.md)
