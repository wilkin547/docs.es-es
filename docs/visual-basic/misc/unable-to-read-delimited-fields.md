---
title: No se pueden leer los campos delimitados porque una comilla doble no es un delimitador válido cuando EscapeQuotes se establece en True.
ms.date: 07/20/2015
f1_keywords:
- vbrTextFieldParser_IllegalDelimiter
ms.assetid: ab8a0c3a-b89c-4617-9e31-7e81f5dca433
ms.openlocfilehash: faa42c2fec5851857496b321dbdb53c16c43e8c1
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43525942"
---
# <a name="unable-to-read-delimited-fields-because-a-double-quote-is-not-a-legal-delimiter-when-escapequotes-is-set-to-true"></a>No se pueden leer los campos delimitados porque una comilla doble no es un delimitador válido cuando EscapeQuotes se establece en True.
El `TextFieldParser` no se puede leer desde el archivo porque se han proporcionado comillas (") como delimitador y `EscapeQuotes` está establecido en `True`.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Establezca `EscapeQuotes` en `False`.  
  
## <a name="see-also"></a>Vea también  
 [Método TextFieldParser.SetDelimiters](https://msdn.microsoft.com/library/21fa40ec-5866-4d0e-9fd9-c708a190dcc9)  
 [Propiedad TextFieldParser.Delimiters](https://msdn.microsoft.com/library/4eb18f4d-3011-40a9-b668-be93eed0444f)  
 [Leer archivos de texto delimitado por comas](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-comma-delimited-text-files.md)  
 [TextFieldParser (objeto)](../../visual-basic/language-reference/objects/textfieldparser-object.md)
