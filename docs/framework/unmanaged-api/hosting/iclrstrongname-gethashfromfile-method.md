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
ms.openlocfilehash: e4a5f6440a016176cf06704b342c173b29748e78
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762115"
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
 de Nombre del archivo al que se va a aplicar un algoritmo hash.  
  
 `piHashAlg`  
 [in, out] Algoritmo que se va a utilizar al generar el hash. Los algoritmos válidos son los definidos por la CryptoAPI de Win32. Si `piHashAlg` se establece en 0, se usa el algoritmo predeterminado CALG_SHA-1.  
  
 `pbHash`  
 enuncia Matriz de bytes que contiene el hash generado.  
  
 `cchHash`  
 de Tamaño máximo del búfer `pbHash` al que apunta.  
  
 `pchHash`  
 enuncia Tamaño, en bytes, del devuelto `pbHash` .  
  
## <a name="return-value"></a>Valor devuelto  
 `S_OK`Si el método se completó correctamente; de lo contrario, un valor HRESULT que indica un error (vea [Valores HRESULT comunes](/windows/win32/seccrypto/common-hresult-values) para una lista).  
  
## <a name="remarks"></a>Comentarios  
 Este método es el mismo que el método [ICLRStrongName:: GetHashFromFileW (](iclrstrongname-gethashfromfilew-method.md) , salvo que la especificación del nombre de archivo es ANSI en lugar de Unicode.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Metahost. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Consulte también:

- [Método GetHashFromFileW](iclrstrongname-gethashfromfilew-method.md)
- [ICLRStrongName (Interfaz)](iclrstrongname-interface.md)
