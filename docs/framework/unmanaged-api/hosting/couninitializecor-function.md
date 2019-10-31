---
title: CoUninitializeCor (Función)
ms.date: 03/30/2017
api_name:
- CoUninitializeCor
api_location:
- mscoree.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CoUninitializeCor
helpviewer_keywords:
- CoUninitializeCor function [.NET Framework hosting]
ms.assetid: 50a95b8b-9766-470e-bb29-2c7ecddfd4a1
topic_type:
- apiref
ms.openlocfilehash: eddc2f29da0efd9e56df710203b1d7621ffc27a0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136864"
---
# <a name="couninitializecor-function"></a>CoUninitializeCor (Función)
`CoUninitializeCor` está obsoleto.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
STDAPI_(void) CoUninitializeCor(void);  
```  
  
## <a name="remarks"></a>Comentarios  
 No se puede descargar el Common Language Runtime de un proceso. Para quitar completamente el Runtime de un proceso en ejecución, debe cerrar ese proceso.  
  
## <a name="see-also"></a>Vea también

- [Funciones estáticas globales para metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
