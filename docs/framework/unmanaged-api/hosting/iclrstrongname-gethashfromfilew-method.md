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
ms.openlocfilehash: 6dbb3360132186c38c007fb5fa12a3724ca145aa
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762102"
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
 de Nombre Unicode del archivo al que se va a aplicar un algoritmo hash.  
  
 `piHashAlg`  
 [in, out] Algoritmo que se va a utilizar al generar el hash. Los algoritmos válidos son los definidos por la CryptoAPI de Win32. Si `piHashAlg` se establece en 0, se usa el algoritmo predeterminado CALG_SHA-1.  
  
 `pbHash`  
 enuncia Matriz de bytes que contiene el hash generado.  
  
 `cchHash`  
 de Tamaño máximo del búfer al que apunta `pbHash` .  
  
 `pchHash`  
 enuncia Tamaño, en bytes, de `pbHash` .  
  
## <a name="return-value"></a>Valor devuelto  
 `S_OK`Si el método se completó correctamente; de lo contrario, un valor HRESULT que indica un error (vea [Valores HRESULT comunes](/windows/win32/seccrypto/common-hresult-values) para una lista).  
  
## <a name="remarks"></a>Comentarios  
 Este método es el mismo que el método [ICLRStrongName:: gethashfromfile (](iclrstrongname-gethashfromfile-method.md) , salvo que la especificación del nombre de archivo es Unicode en lugar de ANSI.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Metahost. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Consulte también:

- [Método GetHashFromFile](iclrstrongname-gethashfromfile-method.md)
- [ICLRStrongName (Interfaz)](iclrstrongname-interface.md)
