---
description: 'Más información acerca de cómo: obtener acceso a caracteres en cadenas en Visual Basic'
title: Procedimiento para obtener acceso a caracteres de cadenas
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], accessing characters
- characters [Visual Basic], accessing in strings
ms.assetid: 02c5206c-ffab-494d-b648-3b2ea358dc34
ms.openlocfilehash: 373005699483dbae92df3a6fe73cc9b6318a9c61
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100476168"
---
# <a name="how-to-access-characters-in-strings-in-visual-basic"></a>Cómo: Obtener acceso a caracteres de cadenas en Visual Basic

En este ejemplo se muestra cómo utilizar la <xref:System.String.Chars%2A> propiedad para tener acceso al carácter que se encuentra en la ubicación especificada de una cadena.  
  
## <a name="example"></a>Ejemplo  

 A veces resulta útil tener datos sobre los caracteres de la cadena y las posiciones de esos caracteres dentro de la cadena. Puede pensar en una cadena como una matriz de caracteres ( `Char` instancias); puede recuperar un carácter determinado haciendo referencia al índice de ese carácter a través de la <xref:System.String.Chars%2A> propiedad.  
  
 [!code-vb[VbVbalrStrings#49](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#49)]  
  
 El `index` parámetro de la <xref:System.String.Chars%2A> propiedad es de base cero.  
  
## <a name="robust-programming"></a>Programación sólida  

 La <xref:System.String.Chars%2A> propiedad devuelve el carácter que se encuentra en la posición especificada. Sin embargo, algunos caracteres Unicode pueden estar representados por más de un carácter. Para obtener más información sobre cómo trabajar con caracteres Unicode, vea [Cómo: convertir una cadena en una matriz de caracteres](how-to-convert-a-string-to-an-array-of-characters.md).  
  
 La <xref:System.String.Chars%2A> propiedad produce una <xref:System.IndexOutOfRangeException> excepción si el `index` parámetro es mayor o igual que la longitud de la cadena, o si es menor que cero.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.String.Chars%2A>
- [Procedimiento para convertir una cadena en una matriz de caracteres](how-to-convert-a-string-to-an-array-of-characters.md)
- [Conversión entre cadenas y otros tipos de datos en Visual Basic](converting-between-strings-and-other-data-types.md)
- [Cadenas](index.md)
