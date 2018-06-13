---
title: Campo de Connection.m_WriteList
ms.date: 05/01/2017
topic_type:
- apiref
api_name:
- System.Net.Connection.m_WriteList
api_location:
- System.dll
api_type:
- Assembly
ms.assetid: 235503c1-1d01-4f59-895f-ae2cf15b3345
author: guardrex
ms.author: mairaw
ms.openlocfilehash: d145f6fd21989ada49a581ebf2694dcd56d94351
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32743165"
---
# <a name="connectionmwritelist-field"></a>Connection.m\_WriteList campo

`Connection.m_WriteList` es un <xref:System.Collections.ArrayList> de <xref:System.Net.HttpWebRequest> objetos que se ponen en cola para ser enviados a través de HTTP.

## <a name="syntax"></a>Sintaxis
  
```csharp  
private ArrayList m_WriteList
```

> [!WARNING]
> El `Connection.m_WriteList` campo es privado y no están hechos para usarse directamente en el código.
> 
> Microsoft no admite el uso de este campo en una aplicación de producción bajo ninguna circunstancia.

## <a name="requirements"></a>Requisitos

**Namespace:** <xref:System.Net>

**Ensamblado:** sistema (en System.dll)

**Versiones de .NET framework:** disponible desde la versión 2.0.
