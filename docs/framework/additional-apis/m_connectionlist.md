---
title: Campo ConnectionGroup.m_ConnectionList
ms.date: 05/01/2017
topic_type:
- apiref
api_name:
- System.Net.ConnectionGroup.m_ConnectionList
api_location:
- System.dll
api_type:
- Assembly
ms.assetid: 186083cf-8dff-4600-a2ab-6fed4b4de6af
author: guardrex
ms.author: mairaw
ms.openlocfilehash: c9162e123c1167e3aa1be26ddd37279c088acc89
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2019
ms.locfileid: "54149168"
---
# <a name="connectiongroupmconnectionlist-field"></a>ConnectionGroup.m\_ConnectionList campo

`ConnectionGroup.m_ConnectionList` es un <xref:System.Collections.ArrayList> de objetos de conexión que actúa el mismo URI y compartir los mismos valores para algunas otras propiedades como la expiración y la autenticación.

## <a name="syntax"></a>Sintaxis
  
```csharp  
private ArrayList m_ConnectionList
```

> [!WARNING]
> El `ConnectionGroup.m_ConnectionList` campo es privado y no está pensado para usarse directamente en el código.
> 
> Microsoft no admite el uso de este campo en una aplicación de producción bajo ninguna circunstancia.

## <a name="requirements"></a>Requisitos

**Espacio de nombres:** <xref:System.Net>

**Ensamblado:** Sistema (en System.dll)

**Versiones de .NET framework:** Disponible desde la versión 2.0.
