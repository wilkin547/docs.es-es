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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d05bc472711838236ed18b00ce808d022d9581dc
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67758206"
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
 El motor de ejecución de common language runtime no se puede descargar desde un proceso. Para apagar la llamada del motor de ejecución [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md).  
  
## <a name="see-also"></a>Vea también

- [CoInitializeEE (función)](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md)
- [Funciones estáticas globales para metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
