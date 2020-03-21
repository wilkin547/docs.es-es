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
ms.openlocfilehash: 9db583c7064cb910b29e84437f31143dac0d3ec9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175088"
---
# <a name="gethashfromfilew-function"></a>GetHashFromFileW (Función)
Genera un hash a partir del contenido del archivo especificado por una cadena Unicode.  
  
 Esta función ha quedado en desuso. Utilice el método [ICLRStrongName::GetHashFromFileW](../hosting/iclrstrongname-gethashfromfilew-method.md) en su lugar.  
  
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
  
## <a name="remarks"></a>Observaciones  
 Esta función es la misma que [GetHashFromFile](gethashfromfile-function.md), excepto que la especificación de nombre de archivo es Unicode en lugar de ANSI.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** StrongName.h  
  
 **Biblioteca:** Incluido como recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Método GetHashFromFileW](../hosting/iclrstrongname-gethashfromfilew-method.md)
- [Método GetHashFromFile](../hosting/iclrstrongname-gethashfromfile-method.md)
- [ICLRStrongName (interfaz)](../hosting/iclrstrongname-interface.md)
