---
description: 'Más información acerca de: StrongNameKeyInstall ((función)'
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
ms.openlocfilehash: 0a5d3971ac0927dda7066405adc01a5c80b7faca
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99670559"
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
de Tamaño, en bytes, de `pbKeyBlob` .

## <a name="return-value"></a>Valor devuelto

`true` Cuando se complete correctamente; en caso contrario, `false` .

## <a name="remarks"></a>Observaciones

Use la función [StrongNameKeyDelete (](strongnamekeydelete-function.md) para eliminar el contenedor de claves.

Si la `StrongNameKeyInstall` función no se completa correctamente, llame a la función [StrongNameErrorInfo (](strongnameerrorinfo-function.md) para recuperar el último error generado.

## <a name="requirements"></a>Requisitos

**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).

**Encabezado:** StrongName. h

**Biblioteca:** Se incluye como un recurso en MsCorEE.dll

**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

## <a name="see-also"></a>Vea también

- [Método StrongNameKeyInstall](../hosting/iclrstrongname-strongnamekeyinstall-method.md)
- [Método StrongNameKeyDelete](../hosting/iclrstrongname-strongnamekeydelete-method.md)
- [ICLRStrongName (Interfaz)](../hosting/iclrstrongname-interface.md)
