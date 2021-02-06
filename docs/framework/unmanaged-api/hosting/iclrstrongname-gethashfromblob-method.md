---
description: 'Más información sobre: ICLRStrongName:: GetHashFromBlob ((método)'
title: ICLRStrongName::GetHashFromBlob (Método)
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromBlob
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromBlob
helpviewer_keywords:
- ICLRStrongName::GetHashFromBlob method [.NET Framework hosting]
- GetHashFromBlob method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: f91d0f89-f356-49ac-aafb-50fad963c13d
topic_type:
- apiref
ms.openlocfilehash: 20d03184f57e77741e656575038e426ee37968f9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99637071"
---
# <a name="iclrstrongnamegethashfromblob-method"></a>ICLRStrongName::GetHashFromBlob (Método)

Obtiene un hash del ensamblado en la dirección de memoria especificada mediante un algoritmo hash concreto.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetHashFromBlob (  
    [in]  BYTE    *pbBlob,  
    [in]  DWORD   cchBlob,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE    *pbHash,  
    [in]  DWORD   cchHash,  
    [out] DWORD   *pchHash  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `pbBlob`  
 de Puntero a la dirección del bloque de memoria al que se va a aplicar un algoritmo hash.  
  
 `cchBlob`  
 de La longitud, en bytes, del bloque de memoria.  
  
 `piHashAlg`  
 [in, out] Constante que especifica el algoritmo hash. Use cero para el algoritmo predeterminado.  
  
 `pbHash`  
 enuncia Búfer hash devuelto.  
  
 `cchHash`  
 de Tamaño máximo solicitado de `pbHash` .  
  
 `pchHash`  
 enuncia Tamaño, en bytes, del devuelto `pbHash` .  
  
## <a name="return-value"></a>Valor devuelto  

 `S_OK` Si el método se completó correctamente; de lo contrario, un valor HRESULT que indica un error (vea [Valores HRESULT comunes](/windows/win32/seccrypto/common-hresult-values) para una lista).  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Metahost. h  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICLRStrongName (Interfaz)](iclrstrongname-interface.md)
