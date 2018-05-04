---
title: Campo de ConnectionGroup.m_ConnectionList
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
ms.openlocfilehash: 5844f8d63aa5646bfd7860dc0407528fb2eaf329
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="connectiongroupmconnectionlist-field"></a>ConnectionGroup.m\_ConnectionList campo

`ConnectionGroup.m_ConnectionList` es un <xref:System.Collections.ArrayList> de objetos de conexión que actúa el mismo URI y compartir los mismos valores para otras propiedades como la expiración y la autenticación.

## <a name="syntax"></a>Sintaxis
  
```csharp  
private ArrayList m_ConnectionList
```

> [!WARNING]
> El `ConnectionGroup.m_ConnectionList` campo es privado y no están hechos para usarse directamente en el código.
> 
> Microsoft no admite el uso de este campo en una aplicación de producción bajo ninguna circunstancia.

## <a name="requirements"></a>Requisitos

**Namespace:** <xref:System.Net>

**Ensamblado:** sistema (en System.dll)

**Versiones de .NET framework:** disponible desde la versión 2.0.
