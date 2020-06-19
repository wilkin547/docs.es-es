---
title: Campo ConnectionGroup. m_ConnectionList
description: Obtenga información sobre el campo ConnectionGroup. m_ConnectionList en .NET, que contiene los objetos de conexión que atienden el mismo URI y los valores de recurso compartido para otras propiedades.
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
ms.openlocfilehash: 478b2441c062e8df6f4e718bd66d7af329f20f12
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/18/2020
ms.locfileid: "84989729"
---
# <a name="connectiongroupm_connectionlist-field"></a>ConnectionGroup. m \_ ConnectionList campo

`ConnectionGroup.m_ConnectionList`es un <xref:System.Collections.ArrayList> objeto de conexión que sirve al mismo URI y comparte los mismos valores para algunas otras propiedades, como la expiración y la autenticación.

## <a name="syntax"></a>Sintaxis
  
```csharp  
private ArrayList m_ConnectionList
```

> [!WARNING]
> El `ConnectionGroup.m_ConnectionList` campo es privado y no está diseñado para usarse directamente en el código.
>
> Microsoft no admite el uso de este campo en una aplicación de producción en cualquier circunstancia.

## <a name="requirements"></a>Requisitos

**Espacio de nombres:** <xref:System.Net>

**Ensamblado:** Sistema (en System.dll)

**.NET Framework versiones:** Disponible desde 2,0.
