---
description: 'Más información acerca de: CoInitializeCor ((función)'
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
ms.openlocfilehash: e1db9914cce8a92cecf78123a2e247d75ec74acf
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799855"
---
# <a name="coinitializecor-function"></a>CoInitializeCor (Función)

`CoInitializeCor` está obsoleto.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
STDAPI CoInitializeCor (  
    DWORD fFlags  
);  
```  
  
## <a name="remarks"></a>Observaciones  

 Para inicializar el Common Language Runtime, use [CorBindToRuntimeEx](corbindtoruntimeex-function.md) o [CorBindToCurrentRuntime (](corbindtocurrentruntime-function.md).  
  
## <a name="requirements"></a>Requisitos  

 **Encabezado:** Cor. h  
  
## <a name="see-also"></a>Vea también

- [Funciones estáticas globales para metadatos](../metadata/metadata-global-static-functions.md)
