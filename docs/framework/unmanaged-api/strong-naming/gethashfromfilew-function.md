---
title: GetHashFromFileW (Función)
ms.date: 03/30/2017
api_name:
- GetHashFromFileW
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromFileW
helpviewer_keywords:
- GetHashFromFileW function [.NET Framework strong naming]
ms.assetid: 97c2d7a6-5376-45a1-ba65-146a249147cc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 00ee1139b4b8340a73740117b74208a6a1f6b639
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33461596"
---
# <a name="gethashfromfilew-function"></a>GetHashFromFileW (Función)
Genera un hash sobre el contenido del archivo especificado por una cadena Unicode.  
  
 Esta función está desusada. Use la [ICLRStrongName:: GetHashFromFileW](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md) método en su lugar.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetHashFromFileW (   
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);   
```  
  
#### <a name="parameters"></a>Parámetros  
 `wszFilePath`  
 [in] El nombre de Unicode del archivo hash.  
  
 `piHashAlg`  
 [entrada, salida] El algoritmo que se utilizará al generar el código hash. Los algoritmos válidos son los definidos por CryptoAPI de Win32. Si `piHashAlg` se establece en 0, el algoritmo predeterminado CALG_SHA-1 se utiliza.  
  
 `pbHash`  
 [out] Una matriz de bytes que contiene el código hash generado.  
  
 `cchHash`  
 [in] El tamaño máximo del búfer que señala `pbHash`.  
  
 `pchHash`  
 [out] El tamaño, en bytes, de `pbHash`.  
  
## <a name="remarks"></a>Comentarios  
 Esta función es el mismo que [GetHashFromFile](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromfile-function.md), salvo que la especificación del nombre de archivo es Unicode en lugar de ANSI.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** StrongName.h  
  
 **Biblioteca:** incluye como recurso en MsCorEE.dll  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [GetHashFromFileW (método)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md)  
 [GetHashFromFile (método)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md)  
 [ICLRStrongName (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
