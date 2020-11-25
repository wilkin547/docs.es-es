---
title: GetHashFromAssemblyFileW (Función)
ms.date: 03/30/2017
api_name:
- GetHashFromAssemblyFileW
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromAssemblyFileW
helpviewer_keywords:
- GetHashFromAssemblyFileW function [.NET Framework strong naming]
ms.assetid: d1b2b172-5353-42af-a877-cf653c68ece0
topic_type:
- apiref
ms.openlocfilehash: b895c77850c0457fd2a152c1128c016093599f76
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730986"
---
# <a name="gethashfromassemblyfilew-function"></a>GetHashFromAssemblyFileW (Función)

Obtiene un hash del archivo de ensamblado especificado mediante un algoritmo hash concreto. La ruta de acceso al archivo de ensamblado debe especificarse como una cadena Unicode.  
  
 Esta función está en desuso. Use el método [ICLRStrongName:: gethashfromassemblyfilew (](../hosting/iclrstrongname-gethashfromassemblyfilew-method.md) en su lugar.  
  
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
 de Tamaño máximo solicitado de `pbHash` .  
  
 `pchHash`  
 enuncia El tamaño devuelto, en bytes, de `pbHash` .  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** StrongName. h  
  
 **Biblioteca:** Se incluye como un recurso en MsCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Método GetHashFromAssemblyFileW](../hosting/iclrstrongname-gethashfromassemblyfilew-method.md)
- [Método GetHashFromAssemblyFile](../hosting/iclrstrongname-gethashfromassemblyfile-method.md)
- [ICLRStrongName (Interfaz)](../hosting/iclrstrongname-interface.md)
