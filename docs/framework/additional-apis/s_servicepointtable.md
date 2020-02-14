---
title: ServicePointManager. s_ServicePointTable campo
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
ms.openlocfilehash: 272a0c113fd70d804c763ba0e7e6e9a4a4ee04ce
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "77214919"
---
# <a name="servicepointmanagers_servicepointtable-field"></a>ServicePointManager. s\_campo ServicePointTable

`ServicePointManager.s_ServicePointTable` es una <xref:System.Collections.Hashtable> que contiene la lista de conexiones HTTP activas (<xref:System.Net.ServicePoint>s) en el <xref:System.AppDomain>.

## <a name="syntax"></a>Sintaxis
  
```csharp  
private static Hashtable s_ServicePointTable
```

> [!WARNING]
> El campo `ServicePointManager.s_ServicePointTable` es privado y no está diseñado para usarse directamente en el código.
> 
> Microsoft no admite el uso de este campo en una aplicación de producción en cualquier circunstancia.

## <a name="requirements"></a>Requisitos

**Espacio de nombres:** <xref:System.Net>

**Ensamblado:** Sistema (en System. dll)

**.NET Framework versiones:** Disponible desde 2,0.
