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
ms.openlocfilehash: 3627c9bf0d72ccec3a0d6d9c7c89b62f83dcd4b4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61706070"
---
# <a name="httpwebrequestcoreresponse-field"></a>HttpWebRequest. \_CoreResponse campo

`HttpWebRequest._CoreResponse` es un objeto (ya sea un [CoreResponseData](coreresponsedata.md) o <xref:System.Exception>) que contiene el resultado del análisis de respuesta HTTP.

## <a name="syntax"></a>Sintaxis
  
```csharp
private object _CoreResponse
```

> [!WARNING]
> Esta API no está pensada para usarse directamente en el código. En su lugar, debe usar un <xref:System.Diagnostics.DiagnosticSource> para enlazar el código de red. Consulte [manual del usuario de DiagnosticSource](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).
> 
> Microsoft no admite el uso de esta clase en una aplicación de producción bajo ninguna circunstancia.

## <a name="requirements"></a>Requisitos

**Espacio de nombres:** <xref:System.Net>

**Ensamblado:** Sistema (en System.dll)

**Versiones de .NET framework:** Disponible desde la versión 2.0.
