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
ms.openlocfilehash: 3d9e7b52c9061a1a7b470f9d4abf735e605087dc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62000537"
---
# <a name="gethashfromblob-function"></a>GetHashFromBlob (Función)

Obtiene un hash del ensamblado en la dirección de memoria especificada mediante un algoritmo hash concreto.

Esta función está desusada. Use la [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromblob-method.md) método en su lugar.

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
[in] Un puntero a la dirección del bloque de memoria para un algoritmo hash.

`cchBlob`\
[in] La longitud, en bytes, del bloque de memoria.

`piHashAlg`\
[in, out] Una constante que especifica el algoritmo hash. Usar cero para el algoritmo predeterminado.

`pbHash`\
[out] El búfer hash devuelto.

`cchHash`\
[in] El tamaño máximo solicitado de `pbHash`.

`pchHash`\
[out] El tamaño, en bytes, del devuelto `pbHash`.

## <a name="requirements"></a>Requisitos

**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).

**Encabezado**: StrongName.h

**Biblioteca:** Incluye como recurso en MsCorEE.dll

**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

## <a name="see-also"></a>Vea también

- [GetHashFromBlob (método)](../hosting/iclrstrongname-gethashfromblob-method.md)
- [ICLRStrongName (interfaz)](../hosting/iclrstrongname-interface.md)