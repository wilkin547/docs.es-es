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
ms.openlocfilehash: 7121ace6777e7cf947fcc6ff30b1ea314851feff
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65636713"
---
# <a name="strongnamekeyinstall-function"></a>StrongNameKeyInstall (Función)

Importa un par de claves pública y privada a un contenedor.

Esta función está desusada. Use la [ICLRStrongName](../hosting/iclrstrongname-strongnamekeyinstall-method.md) método en su lugar.

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
[in] Nombre del contenedor de claves. `wszKeyContainer` debe ser una cadena no vacía.

`pbKeyBlob`\
[in] El par de claves binario.

`cbKeyBlob`\
[in] El tamaño, en bytes, de `pbKeyBlob`.

## <a name="return-value"></a>Valor devuelto

`true` Cuando se finaliza correctamente; en caso contrario, `false`.

## <a name="remarks"></a>Comentarios

Use la [StrongNameKeyDelete](strongnamekeydelete-function.md) función para eliminar el contenedor de claves.

Si el `StrongNameKeyInstall` función no se completa correctamente, llame a la [StrongNameErrorInfo](strongnameerrorinfo-function.md) función para recuperar el último error generado.

## <a name="requirements"></a>Requisitos

**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).

**Encabezado**: StrongName.h

**Biblioteca:** Incluye como recurso en MsCorEE.dll

**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

## <a name="see-also"></a>Vea también

- [StrongNameKeyInstall (método)](../hosting/iclrstrongname-strongnamekeyinstall-method.md)
- [StrongNameKeyDelete (método)](../hosting/iclrstrongname-strongnamekeydelete-method.md)
- [ICLRStrongName (interfaz)](../hosting/iclrstrongname-interface.md)
