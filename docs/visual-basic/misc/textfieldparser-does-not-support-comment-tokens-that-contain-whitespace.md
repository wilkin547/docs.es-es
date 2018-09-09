---
title: TextFieldParser no admite tokens de comentarios que contengan espacios en blanco
ms.date: 07/20/2015
f1_keywords:
- vbrTextFieldParser_WhitespaceInToken
ms.assetid: 55107656-270e-4bbb-841a-478904df8e07
ms.openlocfilehash: a8931d67cd728cf98bc4d83044c65fad6642b021
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/09/2018
ms.locfileid: "44252810"
---
# <a name="textfieldparser-does-not-support-comment-tokens-that-contain-white-space"></a>TextFieldParser no admite tokens de comentarios que contengan espacios en blanco
Se ha proporcionado un token de comentario que contiene espacios en blanco. El `TextFieldParser` no admite tokens de comentarios que contengan espacios en blanco a menos que el espacio en blanco aparezca al principio del token. Se omite el espacio en blanco que aparece al principio de un token.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Proporcione un token de comentario correcto.  
  
## <a name="see-also"></a>Vea también

- [Propiedad TextFieldParser.CommentTokens](xref:Microsoft.VisualBasic.FileIO.TextFieldParser.CommentTokens%2A)  
- [Análisis de archivos de texto con el objeto TextFieldParser](../../visual-basic/developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md)  
- [TextFieldParser (objeto)](../../visual-basic/language-reference/objects/textfieldparser-object.md)
