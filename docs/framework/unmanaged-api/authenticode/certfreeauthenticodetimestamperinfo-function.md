---
description: 'Más información acerca de: Certfreeauthenticodetimestamperinfo ((función)'
title: CertFreeAuthenticodeTimestamperInfo (Función)
ms.date: 03/30/2017
api_name:
- CertFreeAuthenticodeTimestamperInfo
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: 3eb14c49-68c2-4516-ac89-e5bd7473831c
topic_type:
- apiref
ms.openlocfilehash: 5234a90ea1d0272a7409b1b0b4def2160b77a513
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99772944"
---
# <a name="certfreeauthenticodetimestamperinfo-function"></a>CertFreeAuthenticodeTimestamperInfo (Función)

Libera los recursos asignados para la estructura de [AXL_AUTHENTICODE_TIMESTAMPER_INFO](axl-authenticode-timestamper-info-structure.md) .

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT CertFreeAuthenticodeTimestamperInfo (
    [in, out]  PAXL_AUTHENTICODE_TIMESTAMPER_INFO   pTimestamperInfo
);
```

## <a name="parameters"></a>Parámetros

 `pTimestamperInfo`\
 [in, out] Información sobre la marca de tiempo que se va a publicar. Vea la estructura [AXL_AUTHENTICODE_TIMESTAMPER_INFO](axl-authenticode-timestamper-info-structure.md) .

## <a name="return-value"></a>Valor devuelto

 `S_OK` si la función se realiza correctamente. De lo contrario, devuelve un código de error.

## <a name="requirements"></a>Requisitos

**Ensamblado**: clr.dll

## <a name="see-also"></a>Vea también

- [Authenticode](index.md)
