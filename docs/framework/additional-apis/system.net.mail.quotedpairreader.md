---
title: Clase QuotedPairReader (System.Net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.Mail.QuotedPairReader
- System.Net.Mail.QuotedPairReader.CountQuotedChars
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: 898c6e9d2d5dd02f3d5f9c096ad470b5dd445d1d
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.contentlocale: es-ES
ms.lasthandoff: 07/07/2020
ms.locfileid: "86051316"
---
# <a name="quotedpairreader-class"></a>Clase QuotedPairReader

Determina qué caracteres están entre comillas (con escape) en una cadena entrecomillada. No se puede heredar esta clase.

```csharp
internal static class QuotedPairReader
```

> [!WARNING]
> Esta clase es interna y no está diseñada para usarse directamente en el código.
>
> Microsoft no admite el uso de esta clase en una aplicación de producción en cualquier circunstancia.

## <a name="countquotedchars-method"></a>Método CountQuotedChars

Cuenta el número de caracteres entre comillas consecutivos, incluidas varias barras diagonales inversas anteriores, en la cadena especificada. Por ejemplo, dada la cadena `a\\\b` y un índice de `4` , el método devuelve `4` , porque `b` está entre comillas y, por tanto, son las tres barras diagonales inversas anteriores.

```csharp
internal static int CountQuotedChars(string data, int index, bool permitUnicodeEscaping)
```

### <a name="parameters"></a>Parámetros

- `data` <xref:System.String>

  Cadena de datos en la que se van a contar los caracteres comillas consecutivos.

- `index` <xref:System.Int32>

  Posición en la cadena especificada hasta e incluidos los caracteres consecutivos que se deben contar.

- `permitUnicodeEscaping` <xref:System.Boolean>

  `true`para permitir el escape de caracteres Unicode; en caso contrario, `false` .

### <a name="return-value"></a>Valor devuelto

<xref:System.Int32?displayProperty=nameWithType>

`0`Si el carácter que se encuentra en el índice especificado no tiene escape; de lo contrario, el número de caracteres consecutivos consecutivos hasta el carácter situado en `index` .

### <a name="exceptions"></a>Excepciones

<xref:System.FormatException?displayProperty=nameWithType>

Se encontró un carácter Unicode con escape, pero no está permitido.

## <a name="requirements"></a>Requisitos

**Espacio de nombres:** <xref:System.Net>

**Ensamblado:** Sistema (en System.dll)
