---
description: 'Más información acerca de: Gethashfromfile ((función)'
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
ms.openlocfilehash: f91bfe8a3988b6aae563b5a852997d6fd3c309d6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99736601"
---
# <a name="gethashfromfile-function"></a>GetHashFromFile (Función)

Genera un hash a partir del contenido del archivo especificado.  
  
 Esta función está en desuso. Use el método [ICLRStrongName:: gethashfromfile (](../hosting/iclrstrongname-gethashfromfile-method.md) en su lugar.  
  
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
  
## <a name="remarks"></a>Observaciones  

 Esta función es igual que [GetHashFromFileW (](gethashfromfilew-function.md), salvo que la especificación de nombre de archivo es ANSI en lugar de Unicode.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** StrongName. h  
  
 **Biblioteca:** Se incluye como un recurso en MsCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Método GetHashFromFile](../hosting/iclrstrongname-gethashfromfile-method.md)
- [Método GetHashFromFileW](../hosting/iclrstrongname-gethashfromfilew-method.md)
- [ICLRStrongName (Interfaz)](../hosting/iclrstrongname-interface.md)
