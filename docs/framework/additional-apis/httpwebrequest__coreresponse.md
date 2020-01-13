---
title: Campo HttpWebRequest. _CoreResponse
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
ms.openlocfilehash: d16936f6984e73a886f5f48e05b53501ced63c1b
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740452"
---
# <a name="httpwebrequest_coreresponse-field"></a>HttpWebRequest.\_campo CoreResponse

`HttpWebRequest._CoreResponse` es un objeto ( [CoreResponseData](coreresponsedata.md) o un <xref:System.Exception>) que contiene el resultado del análisis de respuesta http.

## <a name="syntax"></a>Sintaxis
  
```csharp
private object _CoreResponse
```

> [!WARNING]
> Esta API no está pensada para usarse directamente en el código. En su lugar, debe usar un <xref:System.Diagnostics.DiagnosticSource> para enlazar el código de red. Consulte [la guía del usuario de DiagnosticSource](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).
> 
> Microsoft no admite el uso de esta clase en una aplicación de producción en cualquier circunstancia.

## <a name="requirements"></a>Requisitos de

**Espacio de nombres:** <xref:System.Net>

**Ensamblado:** Sistema (en System. dll)

**.NET Framework versiones:** Disponible desde 2,0.
