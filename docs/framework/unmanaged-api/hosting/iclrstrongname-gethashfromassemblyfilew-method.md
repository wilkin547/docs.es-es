---
title: ICLRStrongName::GetHashFromAssemblyFileW (Método)
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromAssemblyFileW
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromAssemblyFileW
helpviewer_keywords:
- ICLRStrongName::GetHashFromAssemblyFileW method [.NET Framework hosting]
- GetHashFromAssemblyFileW method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 5d0b44a2-5a14-44a2-9a0e-e8682fd4e106
topic_type:
- apiref
ms.openlocfilehash: 43a5cd57a8eeaba70f1bb1ffb9cab5bb1a067914
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130949"
---
# <a name="iclrstrongnamegethashfromassemblyfilew-method"></a>ICLRStrongName::GetHashFromAssemblyFileW (Método)
Genera un hash a partir del contenido del archivo especificado por una cadena Unicode.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetHashFromAssemblyFileW (  
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `wszFilePath`  
 de Ruta de acceso al archivo al que se va a aplicar un algoritmo hash. Este parámetro debe ser una cadena Unicode.  
  
 `piHashAlg`  
 [in, out] Constante que especifica el algoritmo hash. Use cero para el algoritmo hash predeterminado.  
  
 `pbHash`  
 enuncia Búfer hash devuelto.  
  
 `cchHash`  
 de Tamaño máximo solicitado de `pbHash`.  
  
 `pchHash`  
 enuncia El tamaño devuelto, en bytes, de `pbHash`.  
  
## <a name="return-value"></a>Valor devuelto  
 `S_OK` si el método se completó correctamente; de lo contrario, un valor HRESULT que indica un error (vea [Valores HRESULT comunes](https://go.microsoft.com/fwlink/?LinkId=213878) para una lista).  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Metahost. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [GetHashFromAssemblyFile (método)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfile-method.md)
- [ICLRStrongName (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
