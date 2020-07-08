---
title: Clase MailAddressParser (System.Net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.Mail.MailAddressParser
- System.Net.Mail.MailAddressParser.ParseAddress
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: ff83f6946539fa262ccde980052627f98c75601d
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.contentlocale: es-ES
ms.lasthandoff: 07/07/2020
ms.locfileid: "86051355"
---
# <a name="mailaddressparser-class"></a>Clase MailAddressParser

Analiza las direcciones de correo electrónico como se describe en RFC 2822. No se puede heredar esta clase.

```csharp
internal static class MailAddressParser
```

> [!WARNING]
> Esta clase es interna y no está diseñada para usarse directamente en el código.
>
> Microsoft no admite el uso de esta clase en una aplicación de producción en cualquier circunstancia.

## <a name="parseaddress-method"></a>Método ParseAddress

Analiza una única dirección de correo electrónico de la cadena especificada.

```csharp
internal static MailAddress ParseAddress(string data)
```

### <a name="parameters"></a>Parámetros

`data` <xref:System.String>

Cadena que contiene una dirección de correo electrónico que se va a analizar.

### <a name="return-value"></a>Valor devuelto

<xref:System.Net.Mail.MailAddress>

Una dirección de correo electrónico válida.

### <a name="exceptions"></a>Excepciones

<xref:System.FormatException?displayProperty=nameWithType>

La dirección de correo electrónico no es válida.

## <a name="requirements"></a>Requisitos

**Espacio de nombres:** <xref:System.Net>

**Ensamblado:** Sistema (en System.dll)
