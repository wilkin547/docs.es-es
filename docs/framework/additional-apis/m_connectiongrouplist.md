---
title: ServicePoint.m_ConnectionGroupList Field
ms.date: 05/01/2017
topic_type:
- apiref
api_name:
- System.Net.ServicePoint.m_ConnectionGroupList
api_location:
- System.dll
api_type:
- Assembly
ms.assetid: df8afb59-f0f6-4ddc-b3c1-839b9fc601d8
ms.openlocfilehash: 2b1b46085ed035b67fd01447727b406fe3895980
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155900"
---
# <a name="servicepointm_connectiongrouplist-field"></a>Campo ConnectionGroupList de ServicePoint.m\_

`ServicePoint.m_ConnectionGroupList`es <xref:System.Collections.Hashtable> un de grupos de conexión, <xref:System.Net.ServicePoint>cada uno de los dos mantiene una conexión para el URI 's.

## <a name="syntax"></a>Sintaxis
  
```csharp  
private Hashtable m_ConnectionGroupList
```

> [!WARNING]
> El `ServicePoint.m_ConnectionGroupList` campo es privado y no está diseñado para usarse directamente en el código.
>
> Microsoft no admite el uso de este campo en una aplicación de producción bajo ninguna circunstancia.

## <a name="requirements"></a>Requisitos

**Espacio de nombres:**<xref:System.Net>

**Montaje:** Sistema (en System.dll)

**Versiones de .NET Framework:** Disponible desde 2.0.
