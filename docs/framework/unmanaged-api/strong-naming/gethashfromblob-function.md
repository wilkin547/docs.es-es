---
title: GetHashFromBlob (Función)
ms.date: 03/30/2017
api_name:
- GetHashFromBlob
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromBlob
helpviewer_keywords:
- GetHashFromBlob function [.NET Framework strong naming]
ms.assetid: b712d862-f2d0-4b55-87d4-65bbeadef982
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 427d93a9aff527d36720c4199782fa104a66f8d1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33455038"
---
# <a name="gethashfromblob-function"></a>GetHashFromBlob (Función)
Obtiene un valor hash del ensamblado en la dirección de memoria especificada, utilizando el algoritmo hash especificado.  
  
 Esta función está desusada. Use la [ICLRStronName::GetHashFromBlob](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromblob-method.md) método en su lugar.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetHashFromBlob (  
    [in]  BYTE    *pbBlob,  
    [in]  DWORD   cchBlob,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE    *pbHash,  
    [in]  DWORD   cchHash,  
    [out] DWORD   *pchHash  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `pbBlob`  
 [in] Un puntero a la dirección del bloque de memoria para realizar el hash.  
  
 `cchBlob`  
 [in] La longitud, en bytes, del bloque de memoria.  
  
 `piHashAlg`  
 [entrada, salida] Una constante que especifica el algoritmo hash. Utilice un cero para el algoritmo predeterminado.  
  
 `pbHash`  
 [out] El búfer hash devuelto.  
  
 `cchHash`  
 [in] El tamaño máximo solicitado de `pbHash`.  
  
 `pchHash`  
 [out] El tamaño, en bytes, del devuelto `pbHash`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** StrongName.h  
  
 **Biblioteca:** incluye como recurso en MsCorEE.dll  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [GetHashFromBlob (método)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromblob-method.md)  
 [ICLRStrongName (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
