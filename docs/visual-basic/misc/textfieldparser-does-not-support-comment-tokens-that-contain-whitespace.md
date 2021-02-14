---
description: 'Más información sobre: TextFieldParser no admite tokens de comentarios que contengan espacios en blanco'
title: TextFieldParser no admite tokens de comentarios que contengan espacios en blanco
ms.date: 07/20/2015
f1_keywords:
- vbrTextFieldParser_WhitespaceInToken
ms.assetid: 55107656-270e-4bbb-841a-478904df8e07
ms.openlocfilehash: 27ca19f0a901ca1644d4b121951ed9fdf4d553bd
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100455345"
---
# <a name="textfieldparser-does-not-support-comment-tokens-that-contain-white-space"></a>TextFieldParser no admite tokens de comentarios que contengan espacios en blanco

Se ha proporcionado un token de comentario que contiene espacios en blanco. El `TextFieldParser` no admite tokens de comentarios que contengan espacios en blanco a menos que el espacio en blanco aparezca al principio del token. Se omite el espacio en blanco que aparece al principio de un token.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
- Proporcione un token de comentario correcto.  
  
## <a name="see-also"></a>Consulte también

- [Propiedad TextFieldParser.CommentTokens](xref:Microsoft.VisualBasic.FileIO.TextFieldParser.CommentTokens%2A)
- [Analizar archivos de texto con el objeto TextFieldParser](../developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md)
- [TextFieldParser Object](../language-reference/objects/textfieldparser-object.md)
