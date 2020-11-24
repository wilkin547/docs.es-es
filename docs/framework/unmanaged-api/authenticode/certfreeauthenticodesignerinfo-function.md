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
ms.openlocfilehash: dc6bb5a137a50ec07f89f292e5d9beac4349c3c7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95674182"
---
# <a name="certfreeauthenticodesignerinfo-function"></a>CertFreeAuthenticodeSignerInfo (Función)

Libera los recursos asignados para la estructura de [AXL_AUTHENTICODE_SIGNER_INFO](axl-authenticode-signer-info-structure.md) .  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT CertFreeAuthenticodeSignerInfo (  
    [in, out]  PAXL_AUTHENTICODE_SIGNER_INFO   pSignerInfo);  
```  
  
## <a name="parameters"></a>Parámetros  

 `pSignerInfo`  
 [in, out] Información sobre el firmante que se va a liberar. Vea la estructura [AXL_AUTHENTICODE_SIGNER_INFO](axl-authenticode-signer-info-structure.md) .  
  
## <a name="return-value"></a>Valor devuelto  

 `S_OK` si la función se realiza correctamente. De lo contrario, devuelve un código de error.  
  
## <a name="see-also"></a>Consulte también

- [Authenticode](index.md)
