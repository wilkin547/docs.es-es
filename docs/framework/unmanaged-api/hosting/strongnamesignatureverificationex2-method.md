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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: aab3b697a0bb2f58258816ce4f8133009b26f54a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59220596"
---
# <a name="strongnamesignatureverificationex2-method"></a>StrongNameSignatureVerificationEx2 (Método)
Comprueba la firma de un ensamblado con nombre seguro y proporciona una asignación de la clave ECMA a una clave de real.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT StrongNameSignatureVerificationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  BOOLEAN   fForceVerification,    [in]  BYTE      *pbEcmaPublicKey,  
    [in]  DWORD     cbEcmaPublicKey,  
    [out] BOOLEAN   *pfWasVerified  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `wszFilePath`  
 [in] La ruta de acceso al archivo ejecutable portable (.dll o .exe) del ensamblado que debe comprobarse.  
  
 `fForceVerification`  
 [in] `true` para realizar la comprobación, incluso si es necesario reemplazar la configuración del registro; en caso contrario, `false`.  
  
 `pbEcmaPublicKey`  
 [in] Un puntero a la asignación de la clave pública de ECMA a la clave real que se usa para la comprobación.  
  
 `cbEcmaPublicKey`  
 [in] La longitud de la clave pública real de ECMA.  
  
 `pfWasVerified`  
 [out] `true` si la firma de nombre seguro se ha comprobado; en caso contrario, `false`. Este parámetro también se establece en `false` si la comprobación se realizó correctamente debido a la configuración del registro.  
  
## <a name="return-value"></a>Valor devuelto  
 `S_OK` Si la comprobación se realizó correctamente; en caso contrario, un valor HRESULT que indica un error (consulte [valores HRESULT comunes](https://go.microsoft.com/fwlink/?LinkId=213878) para obtener una lista).  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: MetaHost.h  
  
 **Biblioteca:** Incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Método StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)
- [Método StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)
- [ICLRStrongName (Interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
