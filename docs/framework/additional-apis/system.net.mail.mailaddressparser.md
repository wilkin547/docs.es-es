---
description: 'Más información sobre: clase MailAddressParser'
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
ms.openlocfilehash: 5ad534e731e283f5449b3b8cc8e87628716da9b0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99699771"
---
# <a name="mailaddressparser-class"></a>Clase MailAddressParser

Analiza las direcciones de correo electrónico como se describe en RFC 2822. Esta clase no puede heredarse.

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
