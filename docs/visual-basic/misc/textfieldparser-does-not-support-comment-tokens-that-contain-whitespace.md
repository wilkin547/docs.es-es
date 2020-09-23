---
title: TextFieldParser no admite tokens de comentarios que contengan espacios en blanco
ms.date: 07/20/2015
f1_keywords:
- vbrTextFieldParser_WhitespaceInToken
ms.assetid: 55107656-270e-4bbb-841a-478904df8e07
ms.openlocfilehash: 825f999f8eab3563dd77039ef19ae5e329bb4240
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91078507"
---
# <a name="textfieldparser-does-not-support-comment-tokens-that-contain-white-space"></a>TextFieldParser no admite tokens de comentarios que contengan espacios en blanco

Se ha proporcionado un token de comentario que contiene espacios en blanco. El `TextFieldParser` no admite tokens de comentarios que contengan espacios en blanco a menos que el espacio en blanco aparezca al principio del token. Se omite el espacio en blanco que aparece al principio de un token.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
- Proporcione un token de comentario correcto.  
  
## <a name="see-also"></a>Vea también

- [Propiedad TextFieldParser.CommentTokens](xref:Microsoft.VisualBasic.FileIO.TextFieldParser.CommentTokens%2A)
- [Analizar archivos de texto con el objeto TextFieldParser](../developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md)
- [TextFieldParser Object](../language-reference/objects/textfieldparser-object.md)
