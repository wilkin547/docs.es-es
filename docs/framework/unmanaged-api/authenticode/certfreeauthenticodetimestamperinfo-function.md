---
title: CertFreeAuthenticodeTimestamperInfo (Función)
ms.date: 03/30/2017
api_name:
- CertFreeAuthenticodeTimestamperInfo
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: 3eb14c49-68c2-4516-ac89-e5bd7473831c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 355e6c7b1cd77936d5ccfa5ccff7312c8e35ac63
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59220409"
---
# <a name="certfreeauthenticodetimestamperinfo-function"></a>CertFreeAuthenticodeTimestamperInfo (Función)
Libera recursos asignados para el [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) estructura.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT CertFreeAuthenticodeTimestamperInfo (  
    [in, out]  PAXL_AUTHENTICODE_TIMESTAMPER_INFO   pTimestamperInfo  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pTimestamperInfo`  
 [in, out] Información sobre la marca de tiempo que se va a publicar. Consulte la [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) estructura.  
  
## <a name="return-value"></a>Valor devuelto  
 `S_OK` Si la función se realiza correctamente. De lo contrario, devuelve un código de error.  
  
## <a name="see-also"></a>Vea también

- [Authenticode](../../../../docs/framework/unmanaged-api/authenticode/index.md)
