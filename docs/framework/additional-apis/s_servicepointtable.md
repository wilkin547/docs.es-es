---
title: ServicePointManager. s_ServicePointTable campo
description: Lea sobre el campo ServicePointManager. s_ServicePointTable en .NET. Este campo de tabla hash contiene conexiones HTTP activas (ServicePoints) en el AppDomain.
ms.date: 05/01/2017
topic_type:
- apiref
api_name:
- System.Net.ServicePointManager.s_ServicePointTable
api_location:
- System.dll
api_type:
- Assembly
ms.assetid: 24459679-291c-401a-9def-e42b29466fcf
ms.openlocfilehash: 9462ae10125dd37706f786a1f2cef78e62fbabcc
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/18/2020
ms.locfileid: "84989539"
---
# <a name="servicepointmanagers_servicepointtable-field"></a>Campo ServicePointManager. s \_ ServicePointTable

`ServicePointManager.s_ServicePointTable`es un <xref:System.Collections.Hashtable> que contiene la lista de conexiones http activas <xref:System.Net.ServicePoint> en <xref:System.AppDomain> .

## <a name="syntax"></a>Sintaxis
  
```csharp  
private static Hashtable s_ServicePointTable
```

> [!WARNING]
> El `ServicePointManager.s_ServicePointTable` campo es privado y no está diseñado para usarse directamente en el código.
>
> Microsoft no admite el uso de este campo en una aplicación de producción en cualquier circunstancia.

## <a name="requirements"></a>Requisitos

**Espacio de nombres:** <xref:System.Net>

**Ensamblado:** Sistema (en System.dll)

**.NET Framework versiones:** Disponible desde 2,0.
