---
description: 'Más información acerca de: una comilla doble no es un símbolo (token) de comentario válido para campos delimitados donde EscapeQuote está establecido en true'
title: Un carácter de comilla doble no es un símbolo (token) de comentario válido para campos delimitados donde EscapeQuote está establecido en True
ms.date: 07/20/2015
f1_keywords:
- vbrTextFieldParser_InvalidComment
ms.assetid: 636d4b81-00ba-4cfd-98f7-4d57036f494d
ms.openlocfilehash: d0668c6ffb479e649d4d3900070dc125db6dec05
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797216"
---
# <a name="a-double-quote-is-not-a-valid-comment-token-for-delimited-fields-where-escapequote-is-set-to-true"></a>Un carácter de comilla doble no es un símbolo (token) de comentario válido para campos delimitados donde EscapeQuote está establecido en True

Se proporcionó una comilla como delimitador para `TextFieldParser`, pero `EscapeQuotes` está establecido en `True`.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
- Establezca `EscapeQuotes` en `False`.  
  
## <a name="see-also"></a>Consulte también

- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.SetDelimiters%2A>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.Delimiters%2A>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser>
- [Procedimiento para leer archivos de texto delimitado por comas](../../developing-apps/programming/drives-directories-files/how-to-read-from-comma-delimited-text-files.md)
