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
ms.openlocfilehash: d37f990241ae704abef55d863da0f40a31284837
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141586"
---
# <a name="strongnamekeydelete-function"></a>StrongNameKeyDelete (Función)

Elimina el contenedor de claves especificado.

Esta función está en desuso. Use el método [ICLRStrongName:: StrongNameKeyDelete (](../hosting/iclrstrongname-strongnamekeydelete-method.md) en su lugar.

## <a name="syntax"></a>Sintaxis

```cpp
BOOLEAN StrongNameKeyDelete (
    [in]  LPCWSTR   wszKeyContainer
);
```

## <a name="parameters"></a>Parámetros

`wszKeyContainer`\
de Nombre del contenedor de claves que se va a eliminar.

## <a name="return-value"></a>Valor devuelto

`true` cuando se complete correctamente; de lo contrario, `false`.

## <a name="remarks"></a>Comentarios

Utilice la función [StrongNameKeyInstall (](strongnamekeyinstall-function.md) para importar un par de claves pública y privada en un contenedor.

Si la función `StrongNameKeyDelete` no se completa correctamente, llame a la función [StrongNameErrorInfo (](strongnameerrorinfo-function.md) para recuperar el último error generado.

## <a name="requirements"></a>Requisitos

**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).

**Encabezado:** StrongName. h

**Biblioteca:** Se incluye como recurso en MsCorEE. dll

**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

## <a name="see-also"></a>Vea también

- [StrongNameKeyDelete (método)](../hosting/iclrstrongname-strongnamekeydelete-method.md)
- [StrongNameKeyInstall (método)](../hosting/iclrstrongname-strongnamekeyinstall-method.md)
- [ICLRStrongName (interfaz)](../hosting/iclrstrongname-interface.md)
