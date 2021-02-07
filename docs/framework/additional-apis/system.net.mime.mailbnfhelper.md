---
description: 'Más información sobre: clase MailBnfHelper'
title: Clase MailBnfHelper (System.Net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.Mime.MailBnfHelper
- System.Net.Mime.MailBnfHelper.Ascii7bitMaxValue
- System.Net.Mime.MailBnfHelper.Atext
- System.Net.Mime.MailBnfHelper.CR
- System.Net.Mime.MailBnfHelper.Ctext
- System.Net.Mime.MailBnfHelper.Dot
- System.Net.Mime.MailBnfHelper.EndComment
- System.Net.Mime.MailBnfHelper.LF
- System.Net.Mime.MailBnfHelper.Space
- System.Net.Mime.MailBnfHelper.StartComment
- System.Net.Mime.MailBnfHelper.Tab
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: 942b5c423d2f63985a8f7840f69d956bbade7582
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99699654"
---
# <a name="mailbnfhelper-class"></a>Clase MailBnfHelper

Contiene métodos de utilidad para analizar las cadenas con formato de mensajes de Internet. Esta clase no puede heredarse.

```csharp
internal static class MailBnfHelper
```

> [!WARNING]
> Esta clase es interna y no está diseñada para usarse directamente en el código.
>
> Microsoft no admite el uso de esta clase en una aplicación de producción en cualquier circunstancia.

## <a name="ascii7bitmaxvalue-field"></a>Campo Ascii7bitMaxValue

Representa el valor ASCII máximo de 7 bits.

```csharp
internal static readonly int Ascii7bitMaxValue
```

## <a name="atext-field"></a>Campo texto

Representa los caracteres permitidos en los átomos.

```csharp
internal static bool[] Atext
```

## <a name="cr-field"></a>Campo CR

Representa el carácter de retorno de carro.

```csharp
internal static readonly char CR
```

## <a name="ctext-field"></a>Campo Ctext

Representa los caracteres permitidos dentro de los comentarios.

```csharp
internal static bool[] Ctext
```

## <a name="dot-field"></a>Campo de punto

Representa el carácter de fin completo ( `.` ).

```csharp
internal static readonly char Dot
```

## <a name="endcomment-field"></a>Campo de endcom

Representa el carácter que especifica el final de un comentario.

```csharp
internal static readonly char EndComment
```

## <a name="lf-field"></a>Campo LF

Representa el carácter de avance de línea.

```csharp
internal static readonly char LF
```

## <a name="space-field"></a>Campo de espacio

Representa el carácter de espacio.

```csharp
internal static readonly char Space
```

## <a name="startcomment-field"></a>Campo StartComment

Representa el carácter que especifica el inicio de un comentario.

```csharp
internal static readonly char StartComment
```

## <a name="tab-field"></a>Campo de pestaña

Representa el carácter de tabulación.

```csharp
internal static readonly char Tab
```

## <a name="requirements"></a>Requisitos

**Espacio de nombres:** <xref:System.Net>

**Ensamblado:** Sistema (en System.dll)
