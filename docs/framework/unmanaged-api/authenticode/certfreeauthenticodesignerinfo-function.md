---
title: CertFreeAuthenticodeSignerInfo (Función)
ms.date: 03/30/2017
api_name:
- CertFreeAuthenticodeSignerInfo
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: 8029633c-b6e4-4665-a7c2-89607c3247ef
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cbed2ece8b10c6385341c0af44a81dfa16b6f60c
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57497488"
---
# <a name="certfreeauthenticodesignerinfo-function"></a>CertFreeAuthenticodeSignerInfo (Función)
Libera recursos asignados para el [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md) estructura.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT CertFreeAuthenticodeSignerInfo (  
    [in, out]  PAXL_AUTHENTICODE_SIGNER_INFO   pSignerInfo);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pSignerInfo`  
 [in, out] Información sobre el firmante que se va a liberar. Consulte la [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md) estructura.  
  
## <a name="return-value"></a>Valor devuelto  
 `S_OK` si la función se realiza correctamente. De lo contrario, devuelve un código de error.  
  
## <a name="see-also"></a>Vea también
- [Authenticode](../../../../docs/framework/unmanaged-api/authenticode/index.md)
