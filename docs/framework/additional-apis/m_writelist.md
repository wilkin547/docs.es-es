---
title: Campo Connection.m_WriteList
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
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: d138e0490e849ff26f540077ec7d23ae42737606
ms.sourcegitcommit: 621a5f6df00152006160987395b93b5b55f7ffcd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/29/2019
ms.locfileid: "66300905"
---
# <a name="connectionmwritelist-field"></a>Connection.m\_WriteList campo

`Connection.m_WriteList` es un <xref:System.Collections.ArrayList> de <xref:System.Net.HttpWebRequest> objetos que se ponen en cola para ser enviados a través de HTTP.

## <a name="syntax"></a>Sintaxis
  
```csharp  
private ArrayList m_WriteList
```

> [!WARNING]
> El `Connection.m_WriteList` campo es privado y no está pensado para usarse directamente en el código.
> 
> Microsoft no admite el uso de este campo en una aplicación de producción bajo ninguna circunstancia.

## <a name="requirements"></a>Requisitos

**Espacio de nombres:** <xref:System.Net>

**Ensamblado:** Sistema (en System.dll)

**Versiones de .NET framework:** Disponible desde la versión 2.0.
