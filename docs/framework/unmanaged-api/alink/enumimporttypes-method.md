---
description: 'Más información sobre: método Enumimporttypes ('
title: EnumImportTypes (Método)
ms.date: 03/30/2017
api_name:
- EnumImportTypes
- IALink.EnumImportTypes
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EnumImportTypes
helpviewer_keywords:
- EnumImportTypes method
ms.assetid: 83a0e4e7-ec06-40cb-9b63-700b9695bb04
topic_type:
- apiref
ms.openlocfilehash: 39570740f3560f5bfef8ba80b95c0eb2aca41f59
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99638124"
---
# <a name="enumimporttypes-method"></a>EnumImportTypes (Método)

Enumera cada tipo de cada ámbito.

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT EnumImportTypes(
    HALINKENUM   hEnum,
    DWORD        dwMax,
    mdTypeDef    aTypeDefs[],
    DWORD*       pdwCount
) PURE;
```

## <a name="parameters"></a>Parámetros

`hEnum`\
Identificador del enumerador.

`dwMax`\
Número máximo de tipos que se van a recuperar.

`aTypeDefs`\
Recibe tokens de tipo, no superar `dwMax` .

`pdwCount`\
Recibe el número real de tipo en `aTypeDefs` .

## <a name="return-value"></a>Valor devuelto

Devuelve S_OK si el método se ejecuta correctamente.

## <a name="requirements"></a>Requisitos

Requiere ALink. h

## <a name="see-also"></a>Vea también

- [IALink (Interfaz)](ialink-interface.md)
- [IALink2 (Interfaz)](ialink2-interface.md)
- [API de ALink](index.md)
