---
description: 'Más información sobre: no se pueden leer los campos delimitados porque una comilla doble no es un delimitador válido cuando EscapeQuotes está establecido en true'
title: No se pueden leer los campos delimitados porque una comilla doble no es un delimitador válido cuando EscapeQuotes se establece en True.
ms.date: 07/20/2015
f1_keywords:
- vbrTextFieldParser_IllegalDelimiter
ms.assetid: ab8a0c3a-b89c-4617-9e31-7e81f5dca433
ms.openlocfilehash: 066b5110eaddad74b64f1d86683d7ca2a0a619f7
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100474400"
---
# <a name="unable-to-read-delimited-fields-because-a-double-quote-is-not-a-legal-delimiter-when-escapequotes-is-set-to-true"></a>No se pueden leer los campos delimitados porque una comilla doble no es un delimitador válido cuando EscapeQuotes se establece en True.

El `TextFieldParser` no se puede leer desde el archivo porque se han proporcionado comillas (") como delimitador y `EscapeQuotes` está establecido en `True`.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
- Establezca `EscapeQuotes` en `False`.  
  
## <a name="see-also"></a>Consulte también

- [Método TextFieldParser.SetDelimiters](xref:Microsoft.VisualBasic.FileIO.TextFieldParser.SetDelimiters%2A)
- [Propiedad TextFieldParser.Delimiters](xref:Microsoft.VisualBasic.FileIO.TextFieldParser.Delimiters%2A)
- [Procedimiento para leer archivos de texto delimitado por comas](../developing-apps/programming/drives-directories-files/how-to-read-from-comma-delimited-text-files.md)
- [TextFieldParser Object](../language-reference/objects/textfieldparser-object.md)
