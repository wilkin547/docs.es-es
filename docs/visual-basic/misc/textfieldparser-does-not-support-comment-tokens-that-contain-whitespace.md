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
# <a name="textfieldparser-does-not-support-comment-tokens-that-contain-white-space"></a><span data-ttu-id="472e1-102">TextFieldParser no admite tokens de comentarios que contengan espacios en blanco</span><span class="sxs-lookup"><span data-stu-id="472e1-102">TextFieldParser does not support comment tokens that contain white space</span></span>

<span data-ttu-id="472e1-103">Se ha proporcionado un token de comentario que contiene espacios en blanco.</span><span class="sxs-lookup"><span data-stu-id="472e1-103">A comment token that contains white space has been supplied.</span></span> <span data-ttu-id="472e1-104">El `TextFieldParser` no admite tokens de comentarios que contengan espacios en blanco a menos que el espacio en blanco aparezca al principio del token.</span><span class="sxs-lookup"><span data-stu-id="472e1-104">The `TextFieldParser` does not support comment tokens that contain white space unless the white space occurs at the beginning of the token.</span></span> <span data-ttu-id="472e1-105">Se omite el espacio en blanco que aparece al principio de un token.</span><span class="sxs-lookup"><span data-stu-id="472e1-105">White space occurring at the beginning of a token is ignored.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="472e1-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="472e1-106">To correct this error</span></span>  
  
- <span data-ttu-id="472e1-107">Proporcione un token de comentario correcto.</span><span class="sxs-lookup"><span data-stu-id="472e1-107">Supply a correct comment token.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="472e1-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="472e1-108">See also</span></span>

- [<span data-ttu-id="472e1-109">Propiedad TextFieldParser.CommentTokens</span><span class="sxs-lookup"><span data-stu-id="472e1-109">TextFieldParser.CommentTokens Property</span></span>](xref:Microsoft.VisualBasic.FileIO.TextFieldParser.CommentTokens%2A)
- [<span data-ttu-id="472e1-110">Analizar archivos de texto con el objeto TextFieldParser</span><span class="sxs-lookup"><span data-stu-id="472e1-110">Parsing Text Files with the TextFieldParser Object</span></span>](../developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md)
- [<span data-ttu-id="472e1-111">TextFieldParser Object</span><span class="sxs-lookup"><span data-stu-id="472e1-111">TextFieldParser Object</span></span>](../language-reference/objects/textfieldparser-object.md)
