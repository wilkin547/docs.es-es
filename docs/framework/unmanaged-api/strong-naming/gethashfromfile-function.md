---
title: GetHashFromFile (Función)
ms.date: 03/30/2017
api_name:
- GetHashFromFile
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromFile
helpviewer_keywords:
- GetHashFromFile function [.NET Framework strong naming]
ms.assetid: b3c526a4-8fb4-4ad6-b6af-42ce9c06492e
topic_type:
- apiref
ms.openlocfilehash: ea2b70f37668587fb02513ab54da6c1915e2918d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176986"
---
# <a name="gethashfromfile-function"></a>GetHashFromFile (Función)
Genera un hash a partir del contenido del archivo especificado.  
  
 Esta función ha quedado en desuso. Utilice el [método ICLRStrongName::GetHashFromFile](../hosting/iclrstrongname-gethashfromfile-method.md) en su lugar.  
  
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
  
## <a name="remarks"></a>Observaciones  
 Esta función es la misma que [GetHashFromFileW](gethashfromfilew-function.md), excepto que la especificación de nombre de archivo es ANSI en lugar de Unicode.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** StrongName.h  
  
 **Biblioteca:** Incluido como recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Método GetHashFromFile](../hosting/iclrstrongname-gethashfromfile-method.md)
- [Método GetHashFromFileW](../hosting/iclrstrongname-gethashfromfilew-method.md)
- [ICLRStrongName (interfaz)](../hosting/iclrstrongname-interface.md)
