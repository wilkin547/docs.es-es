---
title: ICLRStrongName::StrongNameSignatureVerificationEx (Método)
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameSignatureVerificationEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameSignatureVerificationEx
helpviewer_keywords:
- StrongNameSignatureVerificationEx method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameSignatureVerificationEx method [.NET Framework hosting]
ms.assetid: dbd2f662-208b-4174-b301-5c99af91040f
topic_type:
- apiref
ms.openlocfilehash: e2003ce78f04b101fe093867e0820f9c3840151a
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762713"
---
# <a name="iclrstrongnamestrongnamesignatureverificationex-method"></a>ICLRStrongName::StrongNameSignatureVerificationEx (Método)
Obtiene un valor que indica si el manifiesto del ensamblado en la ruta de acceso proporcionada contiene una firma de nombre seguro.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT StrongNameSignatureVerificationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  BOOLEAN   fForceVerification,  
    [out] BOOLEAN   *pfWasVerified  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `wszFilePath`  
 de Ruta de acceso al archivo portable ejecutable (. exe o. dll) del ensamblado que se va a comprobar.  
  
 `fForceVerification`  
 [in] `true` para realizar la comprobación, incluso si es necesario invalidar la configuración del registro; en caso contrario, `false` .  
  
 `pfWasVerified`  
 [out] `true` Si se ha comprobado la firma de nombre seguro; en caso contrario, `false` . `pfWasVerified`también se establece en `false` si la comprobación se realizó correctamente debido a la configuración del registro.  
  
## <a name="return-value"></a>Valor devuelto  
 `S_OK`Si la comprobación se realizó correctamente; de lo contrario, un valor HRESULT que indica un error (vea [Valores HRESULT comunes](/windows/win32/seccrypto/common-hresult-values) para una lista).  
  
## <a name="remarks"></a>Comentarios  
 El método [ICLRStrongName:: strongnamesignatureverificationex (](iclrstrongname-strongnamesignatureverificationex-method.md) proporciona una funcionalidad similar a la del método [ICLRStrongName:: strongnamesignatureverification (](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md) . Sin embargo, el segundo parámetro de entrada y el parámetro de salida de [ICLRStrongName:: strongnamesignatureverificationex (](iclrstrongname-strongnamesignatureverificationex-method.md) son de tipo `BOOLEAN` en lugar de `DWORD` .  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Metahost. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Consulte también:

- [Método StrongNameSignatureVerification](iclrstrongname-strongnamesignatureverification-method.md)
- [ICLRStrongName (Interfaz)](iclrstrongname-interface.md)
