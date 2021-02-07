---
description: 'Más información acerca de: GetHashFromBlob ((función)'
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
ms.openlocfilehash: dc5039e44440afa7a000bc61167faec0e5b6cc84
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99736614"
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
de Tamaño máximo solicitado de `pbHash` .

`pchHash`\
enuncia Tamaño, en bytes, del devuelto `pbHash` .

## <a name="requirements"></a>Requisitos

**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).

**Encabezado:** StrongName. h

**Biblioteca:** Se incluye como un recurso en MsCorEE.dll

**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

## <a name="see-also"></a>Vea también

- [Método GetHashFromBlob](../hosting/iclrstrongname-gethashfromblob-method.md)
- [ICLRStrongName (Interfaz)](../hosting/iclrstrongname-interface.md)
