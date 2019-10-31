---
title: GetHashFromHandle (Función)
ms.date: 03/30/2017
api_name:
- GetHashFromHandle
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromHandle
helpviewer_keywords:
- GetHashFromHandle function [.NET Framework strong naming]
ms.assetid: 9e00337f-b307-4602-9bc3-965a8dbf02cd
topic_type:
- apiref
ms.openlocfilehash: dc241324f5844610d7b86b7cb9668f84d4525395
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140664"
---
# <a name="gethashfromhandle-function"></a>GetHashFromHandle (Función)
Genera un hash a partir del contenido del archivo con el identificador de archivos especificado mediante un algoritmo hash concreto.  
  
 Esta función está en desuso. Use el método [ICLRStrongName:: gethashfromhandle (](../hosting/iclrstrongname-gethashfromhandle-method.md) en su lugar.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetHashFromHandle (  
    [in]  HANDLE   hFile,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `hFile`  
 de Identificador del archivo al que se va a aplicar un algoritmo hash.  
  
 `piHashAlg`  
 [in, out] Constante que especifica el algoritmo hash. Use cero para el algoritmo predeterminado.  
  
 `pbHash`  
 enuncia Búfer hash devuelto.  
  
 `cchHash`  
 de Tamaño máximo solicitado de `pbHash`.  
  
 `pchHash`  
 enuncia Tamaño, en bytes, del `pbHash`devuelto.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** StrongName. h  
  
 **Biblioteca:** Se incluye como recurso en MsCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [GetHashFromHandle (método)](../hosting/iclrstrongname-gethashfromhandle-method.md)
- [ICLRStrongName (interfaz)](../hosting/iclrstrongname-interface.md)
