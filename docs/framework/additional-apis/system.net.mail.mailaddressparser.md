---
title: Clase MailAddressParser (System.Net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.MailAddressParser
- System.Net.MailAddressParser.ParseAddress
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: 2c17970614ff9b6f1e6793a064a956da7248d693
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990511"
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
