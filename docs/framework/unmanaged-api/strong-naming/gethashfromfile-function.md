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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5774b7cdcfedfc407b626ab5052f5b4a77461e9b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59155914"
---
# <a name="gethashfromfile-function"></a>GetHashFromFile (Función)
Genera un hash a partir del contenido del archivo especificado.  
  
 Esta función está desusada. Use la [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md) método en su lugar.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
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
 [in] El nombre del archivo a hash.  
  
 `piHashAlg`  
 [in, out] El algoritmo que se utilizará al generar el código hash. Los algoritmos válidos son los definidos por CryptoAPI de Win32. Si `piHashAlg` se establece en 0, el algoritmo predeterminado CALG_SHA-1 se utiliza.  
  
 `pbHash`  
 [out] Una matriz de bytes que contiene el código hash generado.  
  
 `cchHash`  
 [in] El tamaño máximo del búfer que `pbHash` apunta a.  
  
 `pchHash`  
 [out] El tamaño, en bytes, del devuelto `pbHash`.  
  
## <a name="remarks"></a>Comentarios  
 Esta función es el mismo que [GetHashFromFileW](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromfilew-function.md), salvo que la especificación del nombre de archivo es ANSI en lugar de Unicode.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: StrongName.h  
  
 **Biblioteca:** Incluye como recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [GetHashFromFile (método)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md)
- [GetHashFromFileW (método)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md)
- [ICLRStrongName (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
