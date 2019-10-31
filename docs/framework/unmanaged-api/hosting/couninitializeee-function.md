---
title: CoUninitializeEE (Función)
ms.date: 03/30/2017
api_name:
- CoUninitializeEE
api_location:
- mscoree.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CoUninitializeEE
helpviewer_keywords:
- CoUninitializeEE function [.NET Framework hosting]
ms.assetid: 5f5a311a-839a-465f-89d9-ff1c74da9736
topic_type:
- apiref
ms.openlocfilehash: 3531cfc0815c3f8a9479e35b2df60b2825801b39
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136848"
---
# <a name="couninitializeee-function"></a>CoUninitializeEE (Función)
`CoUninitializeEE` está obsoleto y no proporciona ninguna funcionalidad.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
void CoUninitializeEE (  
    BOOL fFlags  
);  
```  
  
## <a name="remarks"></a>Comentarios  
 El motor de ejecución de Common Language Runtime no se puede descargar de un proceso. Para cerrar el motor de ejecución, llame a [CorExitProcess (](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md).  
  
## <a name="see-also"></a>Vea también

- [CoInitializeEE (función)](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md)
- [Funciones estáticas globales para metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
