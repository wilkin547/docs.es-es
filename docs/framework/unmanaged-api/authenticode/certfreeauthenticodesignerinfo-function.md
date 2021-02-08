---
description: 'Más información acerca de: Certfreeauthenticodesignerinfo ((función)'
title: CertFreeAuthenticodeSignerInfo (Función)
ms.date: 03/30/2017
api_name:
- CertFreeAuthenticodeSignerInfo
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: 8029633c-b6e4-4665-a7c2-89607c3247ef
topic_type:
- apiref
ms.openlocfilehash: 6e8a97e8fee37d885c7d32102ed8cc7654992223
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99772983"
---
# <a name="certfreeauthenticodesignerinfo-function"></a>CertFreeAuthenticodeSignerInfo (Función)

Libera los recursos asignados para la estructura de [AXL_AUTHENTICODE_SIGNER_INFO](axl-authenticode-signer-info-structure.md) .

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT CertFreeAuthenticodeSignerInfo (
    [in, out]  PAXL_AUTHENTICODE_SIGNER_INFO   pSignerInfo);
```

## <a name="parameters"></a>Parámetros

 `pSignerInfo`\
 [in, out] Información sobre el firmante que se va a liberar. Vea la estructura [AXL_AUTHENTICODE_SIGNER_INFO](axl-authenticode-signer-info-structure.md) .

## <a name="return-value"></a>Valor devuelto

 `S_OK` si la función se realiza correctamente. De lo contrario, devuelve un código de error.

## <a name="requirements"></a>Requisitos

**Ensamblado**: clr.dll

## <a name="see-also"></a>Vea también

- [Authenticode](index.md)
