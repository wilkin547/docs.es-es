---
title: AXL_AUTHENTICODE_SIGNER_INFO (Estructura)
ms.date: 03/30/2017
ms.assetid: 81c0f8b4-ce35-4716-8651-b642d40648a2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 024837870aade6b0beb76fe758a571b15fd14d59
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59107671"
---
# <a name="axlauthenticodesignerinfo-structure"></a>AXL_AUTHENTICODE_SIGNER_INFO (Estructura)
Define la información del firmante de Authenticode.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
typedef struct _AXL_AUTHENTICODE_SIGNER_INFO {  
    DWORD cbSize;  
    HRESULT dwError;  
    ALG_ID algHash;  
    LPCWSTR pwszHash  
    LPCWSTR pwszDescription;  
    LPCWSTR pwszDescriptionUrl;  
    PCCERT_CHAIN_CONTEXT pChainContext  
} AXL_AUTHENTICODE_SIGNER_INFO, * PAXL_AUTHENTICODE_SIGNER_INFO;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`cbSize`|Tamaño de esta estructura.|  
|`dwError`|Código de error.|  
|`algHash`|Algoritmo hash.|  
|`pwszHash`|Hash.|  
|`pwszDescription`|Description.|  
|`pwszDescriptionUrl`|Dirección URL de la descripción.|  
|`pChainContext`|Contexto de cadena del firmante. Consulte la [CERT_CONTEXT](/windows/desktop/api/wincrypt/ns-wincrypt-_cert_context) estructura.|  
  
## <a name="see-also"></a>Vea también

- [Authenticode](../../../../docs/framework/unmanaged-api/authenticode/index.md)
