---
title: ICLRStrongName::GetHashFromFileW (Método)
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromFileW
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromFileW
helpviewer_keywords:
- GetHashFromFileW method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::GetHashFromFileW method [.NET Framework hosting]
ms.assetid: c6ff45fc-905d-4c6e-b00c-97c6c7c55d99
topic_type:
- apiref
ms.openlocfilehash: 8f2d74531233f2ba423c39126ddc43e499cbb5d8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176375"
---
# <a name="iclrstrongnamegethashfromfilew-method"></a>ICLRStrongName::GetHashFromFileW (Método)
Genera un hash a partir del contenido del archivo especificado por una cadena Unicode.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetHashFromFileW (
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);
```  
  
## <a name="parameters"></a>Parámetros  
 `wszFilePath`  
 [en] El nombre Unicode del archivo que se ha hash.  
  
 `piHashAlg`  
 [adentro, fuera] El algoritmo que se va a utilizar al generar el hash. Los algoritmos válidos son los definidos por Win32 CryptoAPI. Si `piHashAlg` se establece en 0, se utiliza el algoritmo predeterminado CALG_SHA-1.  
  
 `pbHash`  
 [fuera] Matriz de bytes que contiene el hash generado.  
  
 `cchHash`  
 [en] El tamaño máximo del búfer `pbHash`al que apunta .  
  
 `pchHash`  
 [fuera] El tamaño, en `pbHash`bytes, de .  
  
## <a name="return-value"></a>Valor devuelto  
 `S_OK`si el método se completó correctamente; de lo contrario, un valor HRESULT que indica un error (consulte [Valores HRESULT comunes](/windows/win32/seccrypto/common-hresult-values) para obtener una lista).  
  
## <a name="remarks"></a>Observaciones  
 Este método es el mismo que el [método ICLRStrongName::GetHashFromFile,](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md) excepto que la especificación de nombre de archivo es Unicode en lugar de ANSI.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MetaHost.h  
  
 **Biblioteca:** Incluido como recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Método GetHashFromFile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md)
- [ICLRStrongName (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
