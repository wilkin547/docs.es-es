---
title: GetHashFromBlob (Función)
ms.date: 03/30/2017
api_name:
- GetHashFromBlob
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromBlob
helpviewer_keywords:
- GetHashFromBlob function [.NET Framework strong naming]
ms.assetid: b712d862-f2d0-4b55-87d4-65bbeadef982
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 59b4df08157ce14a58393e54b671e8f41b8998ed
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799231"
---
# <a name="gethashfromblob-function"></a>GetHashFromBlob (Función)

Obtiene un hash del ensamblado en la dirección de memoria especificada mediante un algoritmo hash concreto.

Esta función está en desuso. Use el método [ICLRStrongName:: GetHashFromBlob (](../hosting/iclrstrongname-gethashfromblob-method.md) en su lugar.

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT GetHashFromBlob (
    [in]  BYTE    *pbBlob,
    [in]  DWORD   cchBlob,
    [in, out] unsigned int   *piHashAlg,
    [out] BYTE    *pbHash,
    [in]  DWORD   cchHash,
    [out] DWORD   *pchHash
);
```

## <a name="parameters"></a>Parámetros

`pbBlob`\
de Puntero a la dirección del bloque de memoria al que se va a aplicar un algoritmo hash.

`cchBlob`\
de La longitud, en bytes, del bloque de memoria.

`piHashAlg`\
[in, out] Constante que especifica el algoritmo hash. Use cero para el algoritmo predeterminado.

`pbHash`\
enuncia Búfer hash devuelto.

`cchHash`\
de Tamaño máximo solicitado de `pbHash`.

`pchHash`\
enuncia Tamaño, en bytes, del devuelto `pbHash`.

## <a name="requirements"></a>Requisitos

**Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).

**Encabezado**: StrongName. h

**Biblioteca** Se incluye como recurso en MsCorEE. dll

**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

## <a name="see-also"></a>Vea también

- [GetHashFromBlob (método)](../hosting/iclrstrongname-gethashfromblob-method.md)
- [ICLRStrongName (interfaz)](../hosting/iclrstrongname-interface.md)
