---
title: Campo Connection. m_WriteList
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9760e301e25bc6e69ab22b563894cb079a8d58bb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120028"
---
# <a name="connectionm_writelist-field"></a>Connection. m\_campo WriteList

`Connection.m_WriteList` es una <xref:System.Collections.ArrayList> de objetos <xref:System.Net.HttpWebRequest> que se ponen en cola para enviarse a través de HTTP.

## <a name="syntax"></a>Sintaxis
  
```csharp  
private ArrayList m_WriteList
```

> [!WARNING]
> El campo `Connection.m_WriteList` es privado y no está diseñado para usarse directamente en el código.
> 
> Microsoft no admite el uso de este campo en una aplicación de producción en cualquier circunstancia.

## <a name="requirements"></a>Requisitos

**Espacio de nombres:** <xref:System.Net>

**Ensamblado:** Sistema (en System. dll)

**.NET Framework versiones:** Disponible desde 2,0.
