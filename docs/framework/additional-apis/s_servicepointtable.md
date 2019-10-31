---
title: Campo ServicePointManager. s_ServicePointTable
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 68445f4a290b9f4fe2696e35cda391b6c0ee8f85
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73119995"
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
