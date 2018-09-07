---
title: TextFieldParser no admite tokens de comentarios que contengan espacios en blanco
ms.date: 07/20/2015
f1_keywords:
- vbrTextFieldParser_WhitespaceInToken
ms.assetid: 55107656-270e-4bbb-841a-478904df8e07
ms.openlocfilehash: 2beda651dba952969593ffc7d64f01fd51ab7919
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "44070893"
---
# <a name="textfieldparser-does-not-support-comment-tokens-that-contain-white-space"></a>TextFieldParser no admite tokens de comentarios que contengan espacios en blanco
Se ha proporcionado un token de comentario que contiene espacios en blanco. El `TextFieldParser` no admite tokens de comentarios que contengan espacios en blanco a menos que el espacio en blanco aparezca al principio del token. Se omite el espacio en blanco que aparece al principio de un token.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Proporcione un token de comentario correcto.  
  
## <a name="see-also"></a>Vea también  
 [Propiedad TextFieldParser.CommentTokens](https://msdn.microsoft.com/library/2e6b6435-4bee-4c14-a353-e8f2c82e2d61)  
 [Análisis de archivos de texto con el objeto TextFieldParser](../../visual-basic/developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md)  
 [TextFieldParser (objeto)](../../visual-basic/language-reference/objects/textfieldparser-object.md)
