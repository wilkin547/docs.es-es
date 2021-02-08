---
description: 'Más información sobre: clase HttpStatusDescription'
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
ms.openlocfilehash: fa135a6421397ce6b7be2af05d66aa8e81beafb7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802507"
---
# <a name="httpstatusdescription-class"></a>Clase HttpStatusDescription

Proporciona descripciones de Estado HTTP estándar. Esta clase no puede heredarse.

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
