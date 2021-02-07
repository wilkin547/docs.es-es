---
description: 'Más información acerca de: GetHashFromFileW ((función)'
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
ms.openlocfilehash: daebd06de02dfe936f1bdeb8697de4fe6524dce3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99736573"
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
 de Tamaño máximo del búfer al que apunta `pbHash` .  
  
 `pchHash`  
 enuncia Tamaño, en bytes, de `pbHash` .  
  
## <a name="remarks"></a>Observaciones  

 Esta función es igual que [gethashfromfile (](gethashfromfile-function.md), salvo que la especificación de nombre de archivo es Unicode en lugar de ANSI.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** StrongName. h  
  
 **Biblioteca:** Se incluye como un recurso en MsCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Método GetHashFromFileW](../hosting/iclrstrongname-gethashfromfilew-method.md)
- [Método GetHashFromFile](../hosting/iclrstrongname-gethashfromfile-method.md)
- [ICLRStrongName (Interfaz)](../hosting/iclrstrongname-interface.md)
