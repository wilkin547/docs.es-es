---
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1d0aefea7345bc3bf37bdb8d13cb2cda19cfe527
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61789960"
---
# <a name="enumimporttypes-method"></a>EnumImportTypes (Método)

Enumera cada tipo en cada ámbito.

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
Número máximo de tipos para recuperar.

`aTypeDefs`\
Recibe los tokens de tipo, no debe superar los `dwMax`.

`pdwCount`\
Recibe el número real de tipo en `aTypeDefs`.

## <a name="return-value"></a>Valor devuelto

Devuelve S_OK si el método tiene éxito.

## <a name="requirements"></a>Requisitos

Requiere alink.h

## <a name="see-also"></a>Vea también

- [IALink (interfaz)](ialink-interface.md)
- [IALink2 (interfaz)](ialink2-interface.md)
- [API de ALink](index.md)