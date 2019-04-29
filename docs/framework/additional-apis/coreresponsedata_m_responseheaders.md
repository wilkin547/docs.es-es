---
title: Campo CoreResponseData.m_ResponseHeaders
ms.date: 01/29/2018
topic_type:
- apiref
api_name:
- System.Net.CoreResponseData.m_ResponseHeaders
api_location:
- System.dll
api_type:
- Assembly
author: stevewhims
ms.openlocfilehash: ea93b70ae8e1a710b4208050d7ec823a28b218b7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61705979"
---
# <a name="coreresponsedatamresponseheaders-field"></a>CoreResponseData.m\_ResponseHeaders campo

`CoreResponseData.m_ResponseHeaders` es un <xref:System.Net.WebHeaderCollection> de encabezados asociados con la respuesta del servidor.

## <a name="syntax"></a>Sintaxis
  
```csharp
public WebHeaderCollection m_ResponseHeaders
```

> [!WARNING]
> Esta API no está pensada para usarse directamente en el código. En su lugar, debe usar un <xref:System.Diagnostics.DiagnosticSource> para enlazar el código de red. Consulte [manual del usuario de DiagnosticSource](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).
> 
> Microsoft no admite el uso de esta clase en una aplicación de producción bajo ninguna circunstancia.

## <a name="requirements"></a>Requisitos

**Espacio de nombres:** <xref:System.Net>

**Ensamblado:** Sistema (en System.dll)

**Versiones de .NET framework:** Disponible desde la versión 2.0.
