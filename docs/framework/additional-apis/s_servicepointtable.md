---
title: Campo de ServicePointManager.s_ServicePointTable
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
author: guardrex
ms.author: mairaw
ms.openlocfilehash: 5450a0cb3e5bd39a86365b16d372c7e573a43496
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33351763"
---
# <a name="servicepointmanagersservicepointtable-field"></a>ServicePointManager.s\_ServicePointTable campo

`ServicePointManager.s_ServicePointTable` es un <xref:System.Collections.Hashtable> que contiene la lista de conexiones HTTP activas (<xref:System.Net.ServicePoint>s) en el <xref:System.AppDomain>.

## <a name="syntax"></a>Sintaxis
  
```csharp  
private static Hashtable s_ServicePointTable
```

> [!WARNING]
> El `ServicePointManager.s_ServicePointTable` campo es privado y no están hechos para usarse directamente en el código.
> 
> Microsoft no admite el uso de este campo en una aplicación de producción bajo ninguna circunstancia.

## <a name="requirements"></a>Requisitos

**Namespace:** <xref:System.Net>

**Ensamblado:** sistema (en System.dll)

**Versiones de .NET framework:** disponible desde la versión 2.0.
