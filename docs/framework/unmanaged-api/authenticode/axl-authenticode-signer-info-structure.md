---
title: AXL_AUTHENTICODE_SIGNER_INFO (Estructura)
ms.date: 03/30/2017
ms.assetid: 81c0f8b4-ce35-4716-8651-b642d40648a2
ms.openlocfilehash: 00132bb378d69c0db9fe9d762407707346238917
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132512"
---
# <a name="axl_authenticode_signer_info-structure"></a>AXL_AUTHENTICODE_SIGNER_INFO (Estructura)
Define la información del firmante de Authenticode.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
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
|`pChainContext`|Contexto de cadena del firmante. Vea la estructura [CERT_CONTEXT](/windows/win32/api/wincrypt/ns-wincrypt-cert_context) .|  
  
## <a name="see-also"></a>Vea también

- [Authenticode](index.md)
