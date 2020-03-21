---
title: ServicePointManager.s_ServicePointTable Field
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
ms.openlocfilehash: 6a56ecd6fc85005f5987c3c2ad0d1680ca63c398
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155824"
---
# <a name="servicepointmanagers_servicepointtable-field"></a>Campo ServicePointManager.s\_ServicePointTable

`ServicePointManager.s_ServicePointTable`es <xref:System.Collections.Hashtable> un que contiene la lista<xref:System.Net.ServicePoint>de conexiones HTTP activas ( s) en el <xref:System.AppDomain>archivo .

## <a name="syntax"></a>Sintaxis
  
```csharp  
private static Hashtable s_ServicePointTable
```

> [!WARNING]
> El `ServicePointManager.s_ServicePointTable` campo es privado y no está diseñado para usarse directamente en el código.
>
> Microsoft no admite el uso de este campo en una aplicación de producción bajo ninguna circunstancia.

## <a name="requirements"></a>Requisitos

**Espacio de nombres:**<xref:System.Net>

**Montaje:** Sistema (en System.dll)

**Versiones de .NET Framework:** Disponible desde 2.0.
