---
title: ICLRStrongName::GetHashFromFile (Método)
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromFile
helpviewer_keywords:
- ICLRStrongName::GetHashFromFile method [.NET Framework hosting]
- GetHashFromFile method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 9e50480a-8ada-4044-b2a5-97bb14ed3525
topic_type:
- apiref
ms.openlocfilehash: ed735c3d7830551581df35793f3f6fdc4953dc8c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178071"
---
# <a name="iclrstrongnamegethashfromfile-method"></a>ICLRStrongName::GetHashFromFile (Método)
Genera un hash a partir del contenido del archivo especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetHashFromFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,
    [out] BYTE     *pbHash,
    [in]  DWORD    cchHash,
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `szFilePath`  
 [en] El nombre del archivo que se ha hash.  
  
 `piHashAlg`  
 [adentro, fuera] El algoritmo que se va a utilizar al generar el hash. Los algoritmos válidos son los definidos por Win32 CryptoAPI. Si `piHashAlg` se establece en 0, se utiliza el algoritmo predeterminado CALG_SHA-1.  
  
 `pbHash`  
 [fuera] Matriz de bytes que contiene el hash generado.  
  
 `cchHash`  
 [en] El tamaño máximo del `pbHash` búfer al que apunta.  
  
 `pchHash`  
 [fuera] El tamaño, en bytes, `pbHash`del valor devuelto .  
  
## <a name="return-value"></a>Valor devuelto  
 `S_OK`si el método se completó correctamente; de lo contrario, un valor HRESULT que indica un error (consulte [Valores HRESULT comunes](/windows/win32/seccrypto/common-hresult-values) para obtener una lista).  
  
## <a name="remarks"></a>Observaciones  
 Este método es el mismo que el [método ICLRStrongName::GetHashFromFileW,](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md) excepto que la especificación de nombre de archivo es ANSI en lugar de Unicode.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MetaHost.h  
  
 **Biblioteca:** Incluido como recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Método GetHashFromFileW](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md)
- [ICLRStrongName (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
