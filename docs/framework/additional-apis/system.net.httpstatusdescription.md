---
title: Clase HttpStatusDescription (System.Net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.HttpStatusDescription
- System.Net.HttpStatusDescription.Get
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: 0214d8259c735de11abe204680d619a7298466de
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990515"
---
# <a name="httpstatusdescription-class"></a>Clase HttpStatusDescription

Proporciona descripciones de Estado HTTP estándar. No se puede heredar esta clase.

```csharp
internal static class HttpStatusDescription
```

> [!WARNING]
> Esta clase es interna y no está diseñada para usarse directamente en el código.
>
> Microsoft no admite el uso de esta clase en una aplicación de producción en cualquier circunstancia.

## <a name="get-method"></a>método Get

Devuelve la descripción asociada al código de Estado HTTP especificado.

```csharp
internal static string Get(int code)
```

### <a name="parameters"></a>Parámetros

`code` <xref:System.Int32>

El código de Estado HTTP, por ejemplo, `404` .

### <a name="return-value"></a>Valor devuelto

<xref:System.String?displayProperty=nameWithType>

La descripción del estado de HTTP.

## <a name="requirements"></a>Requisitos

**Espacio de nombres:** <xref:System.Net>

**Ensamblado:** Sistema (en System.dll)
