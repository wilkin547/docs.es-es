---
title: StrongNameKeyDelete (Función)
ms.date: 03/30/2017
api_name:
- StrongNameKeyDelete
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameKeyDelete
helpviewer_keywords:
- StrongNameKeyDelete function [.NET Framework strong naming]
ms.assetid: 313e71e4-1790-4d2f-b68b-5040ebd1c149
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dfc785a48d0cdf1cf2fdc0245a27b8ef35fd2d81
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62040773"
---
# <a name="strongnamekeydelete-function"></a>StrongNameKeyDelete (Función)

Elimina el contenedor de claves especificado.

Esta función está desusada. Use la [ICLRStrongName](../hosting/iclrstrongname-strongnamekeydelete-method.md) método en su lugar.

## <a name="syntax"></a>Sintaxis

```cpp
BOOLEAN StrongNameKeyDelete (
    [in]  LPCWSTR   wszKeyContainer
);
```

## <a name="parameters"></a>Parámetros

`wszKeyContainer`\
[in] Nombre del contenedor de claves para eliminar.

## <a name="return-value"></a>Valor devuelto

`true` Cuando se finaliza correctamente; en caso contrario, `false`.

## <a name="remarks"></a>Comentarios

Use la [StrongNameKeyInstall](strongnamekeyinstall-function.md) función para importar un par de claves pública y privada en un contenedor.

Si el `StrongNameKeyDelete` función no se completa correctamente, llame a la [StrongNameErrorInfo](strongnameerrorinfo-function.md) función para recuperar el último error generado.

## <a name="requirements"></a>Requisitos

**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).

**Encabezado**: StrongName.h

**Biblioteca:** Incluye como recurso en MsCorEE.dll

**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

## <a name="see-also"></a>Vea también

- [StrongNameKeyDelete (método)](../hosting/iclrstrongname-strongnamekeydelete-method.md)
- [StrongNameKeyInstall (método)](../hosting/iclrstrongname-strongnamekeyinstall-method.md)
- [ICLRStrongName (interfaz)](../hosting/iclrstrongname-interface.md)