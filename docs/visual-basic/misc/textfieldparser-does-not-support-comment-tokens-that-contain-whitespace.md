---
title: TextFieldParser no admite tokens de comentarios que contengan espacios en blanco.
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrTextFieldParser_WhitespaceInToken
ms.assetid: 55107656-270e-4bbb-841a-478904df8e07
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0e5f41b1f1019459d55d5806f45301f4248e65fc
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="textfieldparser-does-not-support-comment-tokens-that-contain-whitespace"></a>TextFieldParser no admite tokens de comentarios que contengan espacios en blanco.
Se ha proporcionado un token de comentario que contiene espacios en blanco. El `TextFieldParser` no admite tokens de comentarios que contengan espacios en blanco a menos que el espacio en blanco aparezca al principio del token. Se omite el espacio en blanco que aparece al principio de un token.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Proporcione un token de comentario correcto.  
  
## <a name="see-also"></a>Vea también  
 [Propiedad TextFieldParser.CommentTokens](http://msdn.microsoft.com/library/2e6b6435-4bee-4c14-a353-e8f2c82e2d61)  
 [Análisis de archivos de texto con el objeto TextFieldParser](../../visual-basic/developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md)  
 [TextFieldParser (objeto)](../../visual-basic/language-reference/objects/textfieldparser-object.md)
