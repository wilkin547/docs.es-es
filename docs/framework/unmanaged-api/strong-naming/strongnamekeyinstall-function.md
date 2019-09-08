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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 353898b72f41acd0c49a43ff05e54f61b99444c4
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798997"
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
de Nombre del contenedor de claves. `wszKeyContainer`debe ser una cadena no vacía.

`pbKeyBlob`\
de Par de claves binarias.

`cbKeyBlob`\
de Tamaño, en bytes, de `pbKeyBlob`.

## <a name="return-value"></a>Valor devuelto

`true`Cuando se complete correctamente; en caso `false`contrario,.

## <a name="remarks"></a>Comentarios

Use la función [StrongNameKeyDelete (](strongnamekeydelete-function.md) para eliminar el contenedor de claves.

Si la `StrongNameKeyInstall` función no se completa correctamente, llame a la función [StrongNameErrorInfo (](strongnameerrorinfo-function.md) para recuperar el último error generado.

## <a name="requirements"></a>Requisitos

**Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).

**Encabezado**: StrongName. h

**Biblioteca** Se incluye como recurso en MsCorEE. dll

**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

## <a name="see-also"></a>Vea también

- [StrongNameKeyInstall (método)](../hosting/iclrstrongname-strongnamekeyinstall-method.md)
- [StrongNameKeyDelete (método)](../hosting/iclrstrongname-strongnamekeydelete-method.md)
- [ICLRStrongName (interfaz)](../hosting/iclrstrongname-interface.md)
