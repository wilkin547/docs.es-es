---
title: CoInitializeCor (Función)
ms.date: 03/30/2017
api_name:
- CoInitializeCor
api_location:
- mscoree.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CoInitializeCor
helpviewer_keywords:
- CoInitializeCor function [.NET Framework hosting]
ms.assetid: 9b9079fb-579e-4141-b3f0-791072dd40dc
topic_type:
- apiref
ms.openlocfilehash: 9d077d5c5a414568b5643cad0171e101d7bb06f9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731714"
---
# <a name="coinitializecor-function"></a>CoInitializeCor (Función)

`CoInitializeCor` está obsoleto.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
STDAPI CoInitializeCor (  
    DWORD fFlags  
);  
```  
  
## <a name="remarks"></a>Comentarios  

 Para inicializar el Common Language Runtime, use [CorBindToRuntimeEx](corbindtoruntimeex-function.md) o [CorBindToCurrentRuntime (](corbindtocurrentruntime-function.md).  
  
## <a name="requirements"></a>Requisitos  

 **Encabezado:** Cor. h  
  
## <a name="see-also"></a>Consulte también

- [Funciones estáticas globales para metadatos](../metadata/metadata-global-static-functions.md)
