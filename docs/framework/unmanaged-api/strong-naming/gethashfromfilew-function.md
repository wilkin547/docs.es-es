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
ms.openlocfilehash: fd96b5acb22f63b6e06c981119186680d6593a79
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799189"
---
# <a name="gethashfromfilew-function"></a>GetHashFromFileW (Función)
Genera un hash a partir del contenido del archivo especificado por una cadena Unicode.  
  
 Esta función está en desuso. Use el método [ICLRStrongName:: GetHashFromFileW (](../hosting/iclrstrongname-gethashfromfilew-method.md) en su lugar.  
  
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
 de Tamaño máximo del búfer al que `pbHash`apunta.  
  
 `pchHash`  
 enuncia Tamaño, en bytes, de `pbHash`.  
  
## <a name="remarks"></a>Comentarios  
 Esta función es igual que [gethashfromfile (](gethashfromfile-function.md), salvo que la especificación de nombre de archivo es Unicode en lugar de ANSI.  
  
## <a name="requirements"></a>Requisitos  
 **Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).  
  
 **Encabezado**: StrongName. h  
  
 **Biblioteca** Se incluye como recurso en MsCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [GetHashFromFileW (método)](../hosting/iclrstrongname-gethashfromfilew-method.md)
- [GetHashFromFile (método)](../hosting/iclrstrongname-gethashfromfile-method.md)
- [ICLRStrongName (interfaz)](../hosting/iclrstrongname-interface.md)
