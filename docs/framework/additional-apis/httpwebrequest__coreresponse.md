---
title: HttpWebRequest._CoreResponse Field
ms.date: 01/29/2018
ms.prod: .net-framework
ms.technology: 
ms.topic: reference
topic_type:
- apiref
api_name:
- System.Net.HttpWebRequest._CoreResponse
api_location:
- System.dll
api_type:
- Assembly
author: stevewhims
ms.author: stwhi
manager: markl
ms.workload:
- dotnet
ms.openlocfilehash: e6493747cf6c894357223f011da026770778e26c
ms.sourcegitcommit: cf22b29db780e532e1090c6e755aa52d28273fa6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/01/2018
---
# <a name="httpwebrequestcoreresponse-field"></a>HttpWebRequest. \_CoreResponse campo

`HttpWebRequest._CoreResponse`es un objeto (ya sea un [CoreResponseData](coreresponsedata.md) o <xref:System.Exception>) que contiene el resultado del análisis de respuesta HTTP.

## <a name="syntax"></a>Sintaxis
  
```csharp
private object _CoreResponse
```

> [!WARNING]
> Esta API no está pensada para usarse directamente en el código. En su lugar, debe usar un <xref:System.Diagnostics.DiagnosticSource> para enlazar el código de la red. Vea [manual del usuario de DiagnosticSource](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).
> 
> Microsoft no admite el uso de esta clase en una aplicación de producción bajo ninguna circunstancia.

## <a name="requirements"></a>Requisitos

**Namespace:**<xref:System.Net>

**Ensamblado:** sistema (en System.dll)

**Versiones de .NET framework:** disponible desde la versión 2.0.
