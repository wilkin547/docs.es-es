---
title: Campo de Connection.m_WriteList
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology: 
ms.topic: reference
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
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e3849fdd327923e480cd88c932cfdce6580d3f09
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="connectionmwritelist-field"></a>Connection.m\_WriteList campo

`Connection.m_WriteList`es un <xref:System.Collections.ArrayList> de <xref:System.Net.HttpWebRequest> objetos que se ponen en cola para ser enviados a través de HTTP.

## <a name="syntax"></a>Sintaxis
  
```csharp  
private ArrayList m_WriteList
```

> [!WARNING]
> El `Connection.m_WriteList` campo es privado y no están hechos para usarse directamente en el código.
> 
> Microsoft no admite el uso de este campo en una aplicación de producción bajo ninguna circunstancia.

## <a name="requirements"></a>Requisitos

**Namespace:**<xref:System.Net>

**Ensamblado:** sistema (en System.dll)

**Versiones de .NET framework:** disponible desde la versión 2.0.
