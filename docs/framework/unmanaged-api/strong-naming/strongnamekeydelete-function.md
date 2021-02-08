---
description: 'Más información acerca de: StrongNameKeyDelete ((función)'
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
ms.openlocfilehash: 9314d961f79e673925125c2362308f9ab4533e75
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99781212"
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

`true` Cuando se complete correctamente; en caso contrario, `false` .

## <a name="remarks"></a>Observaciones

Utilice la función [StrongNameKeyInstall (](strongnamekeyinstall-function.md) para importar un par de claves pública y privada en un contenedor.

Si la `StrongNameKeyDelete` función no se completa correctamente, llame a la función [StrongNameErrorInfo (](strongnameerrorinfo-function.md) para recuperar el último error generado.

## <a name="requirements"></a>Requisitos

**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).

**Encabezado:** StrongName. h

**Biblioteca:** Se incluye como un recurso en MsCorEE.dll

**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

## <a name="see-also"></a>Vea también

- [Método StrongNameKeyDelete](../hosting/iclrstrongname-strongnamekeydelete-method.md)
- [Método StrongNameKeyInstall](../hosting/iclrstrongname-strongnamekeyinstall-method.md)
- [ICLRStrongName (Interfaz)](../hosting/iclrstrongname-interface.md)
