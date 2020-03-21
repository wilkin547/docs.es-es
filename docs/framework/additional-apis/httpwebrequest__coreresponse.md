---
title: Campo HttpWebRequest._CoreResponse
ms.date: 01/29/2018
topic_type:
- apiref
api_name:
- System.Net.HttpWebRequest._CoreResponse
api_location:
- System.dll
api_type:
- Assembly
author: stevewhims
ms.openlocfilehash: b275f3eece96ac8a9ae3fb0ebd030c8d79e21fc1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155926"
---
# <a name="httpwebrequest_coreresponse-field"></a>HttpWebRequest. \_Campo CoreResponse

`HttpWebRequest._CoreResponse`es un objeto (ya sea <xref:System.Exception> [CoreResponseData](coreresponsedata.md) o un ) que contiene el resultado del análisis de respuestas HTTP.

## <a name="syntax"></a>Sintaxis
  
```csharp
private object _CoreResponse
```

> [!WARNING]
> Esta API no está diseñada para usarse directamente en el código. En su lugar, <xref:System.Diagnostics.DiagnosticSource> debe usar a para enlazar código de red. Consulte [Guía del usuario de DiagnosticSource](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).
>
> Microsoft no admite el uso de esta clase en una aplicación de producción bajo ninguna circunstancia.

## <a name="requirements"></a>Requisitos

**Espacio de nombres:**<xref:System.Net>

**Montaje:** Sistema (en System.dll)

**Versiones de .NET Framework:** Disponible desde 2.0.
