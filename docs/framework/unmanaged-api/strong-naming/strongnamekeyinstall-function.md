---
title: StrongNameKeyInstall (Función)
ms.date: 03/30/2017
api_name:
- StrongNameKeyInstall
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameKeyInstall
helpviewer_keywords:
- StrongNameKeyInstall function [.NET Framework strong naming]
ms.assetid: e32fd546-7757-4681-be3d-658e93281e50
topic_type:
- apiref
ms.openlocfilehash: 9e441d4da64e9704fbda2368d2b07289aaea610a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125197"
---
# <a name="strongnamekeyinstall-function"></a>StrongNameKeyInstall (Función)

Importa un par de claves pública y privada a un contenedor.

Esta función está en desuso. Use el método [ICLRStrongName:: StrongNameKeyInstall (](../hosting/iclrstrongname-strongnamekeyinstall-method.md) en su lugar.

## <a name="syntax"></a>Sintaxis

```cpp
BOOLEAN StrongNameKeyInstall (
    [in]  LPCWSTR   wszKeyContainer,
    [in]  BYTE      *pbKeyBlob,
    [in]  ULONG     cbKeyBlob
);
```

## <a name="parameters"></a>Parámetros

`wszKeyContainer`\
de Nombre del contenedor de claves. `wszKeyContainer` debe ser una cadena no vacía.

`pbKeyBlob`\
de Par de claves binarias.

`cbKeyBlob`\
de Tamaño, en bytes, de `pbKeyBlob`.

## <a name="return-value"></a>Valor devuelto

`true` cuando se complete correctamente; de lo contrario, `false`.

## <a name="remarks"></a>Comentarios

Use la función [StrongNameKeyDelete (](strongnamekeydelete-function.md) para eliminar el contenedor de claves.

Si la función `StrongNameKeyInstall` no se completa correctamente, llame a la función [StrongNameErrorInfo (](strongnameerrorinfo-function.md) para recuperar el último error generado.

## <a name="requirements"></a>Requisitos

**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).

**Encabezado:** StrongName. h

**Biblioteca:** Se incluye como recurso en MsCorEE. dll

**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

## <a name="see-also"></a>Vea también

- [StrongNameKeyInstall (método)](../hosting/iclrstrongname-strongnamekeyinstall-method.md)
- [StrongNameKeyDelete (método)](../hosting/iclrstrongname-strongnamekeydelete-method.md)
- [ICLRStrongName (interfaz)](../hosting/iclrstrongname-interface.md)
