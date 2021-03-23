---
title: HttpWebRequest._CoreResponse campo
description: Lea sobre el campo HttpWebRequest._CoreResponse en .NET. Este campo es un objeto CoreResponseData o Exception que contiene el resultado del análisis de respuesta HTTP.
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
ms.openlocfilehash: f5fb71c21922285c0e18c2d1f28eeaf2353dcaee
ms.sourcegitcommit: c7f0beaa2bd66ebca86362ca17d673f7e8256ca6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "104873840"
---
# <a name="httpwebrequest_coreresponse-field"></a>HttpWebRequest. \_ Campo CoreResponse

`HttpWebRequest._CoreResponse` es un objeto ( [CoreResponseData](coreresponsedata.md) o un <xref:System.Exception> ) que contiene el resultado del análisis de respuesta http.

## <a name="syntax"></a>Sintaxis
  
```csharp
private object _CoreResponse
```

> [!WARNING]
> Esta API no está pensada para usarse directamente en el código. En su lugar, debe utilizar un <xref:System.Diagnostics.DiagnosticSource> para enlazar el código de red. Consulte [la guía del usuario de DiagnosticSource](https://github.com/dotnet/runtime/blob/main/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).
>
> Microsoft no admite el uso de esta clase en una aplicación de producción en cualquier circunstancia.

## <a name="requirements"></a>Requisitos

**Espacio de nombres:** <xref:System.Net>

**Ensamblado:** Sistema (en System.dll)

**.NET Framework versiones:** Disponible desde 2,0.
