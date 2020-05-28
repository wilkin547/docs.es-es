---
title: StrongNameSignatureVerificationEx2 (Método)
ms.date: 03/30/2017
api_name:
- ICLRStrongName2.StrongNameSignatureVerificationEx2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- StrongNameSignatureVerificationEx2
helpviewer_keywords:
- StrongNameSignatureVerificationEx2 method, ICLRStrongName2 interface [.NET Framework hosting]
- ICLRStrongName2::StrongNameSignatureVerificationEx2 method [.NET Framework hosting]
ms.assetid: dfd4133f-a074-4db3-a7ee-4f250fe9ad3a
topic_type:
- apiref
ms.openlocfilehash: 5e6f77b9b5da061a75d23d7f3f7b673754b62afd
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84006373"
---
# <a name="strongnamesignatureverificationex2-method"></a>StrongNameSignatureVerificationEx2 (Método)
Comprueba la firma de un ensamblado con nombre seguro y proporciona una asignación de la clave ECMA a una clave real.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT StrongNameSignatureVerificationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  BOOLEAN   fForceVerification,    [in]  BYTE      *pbEcmaPublicKey,  
    [in]  DWORD     cbEcmaPublicKey,  
    [out] BOOLEAN   *pfWasVerified  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `wszFilePath`  
 de Ruta de acceso al archivo portable ejecutable (. exe o. dll) del ensamblado que se va a comprobar.  
  
 `fForceVerification`  
 [in] `true` para realizar la comprobación, incluso si es necesario invalidar la configuración del registro; en caso contrario, `false` .  
  
 `pbEcmaPublicKey`  
 de Un puntero a la asignación de la clave pública ECMA a la clave real que se usa para la comprobación.  
  
 `cbEcmaPublicKey`  
 de La longitud de la clave pública ECMA real.  
  
 `pfWasVerified`  
 [out] `true` Si se ha comprobado la firma de nombre seguro; en caso contrario, `false` . Este parámetro también se establece en `false` si la comprobación se realizó correctamente debido a la configuración del registro.  
  
## <a name="return-value"></a>Valor devuelto  
 `S_OK`Si la comprobación se realizó correctamente; de lo contrario, un valor HRESULT que indica un error (vea [Valores HRESULT comunes](/windows/win32/seccrypto/common-hresult-values) para una lista).  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Metahost. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Método StrongNameSignatureVerification](iclrstrongname-strongnamesignatureverification-method.md)
- [Método StrongNameSignatureVerificationEx](iclrstrongname-strongnamesignatureverificationex-method.md)
- [ICLRStrongName (Interfaz)](iclrstrongname-interface.md)
