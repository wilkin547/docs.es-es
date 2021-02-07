---
description: 'Más información acerca de: IMetaDataTables:: GetUserString ((método)'
title: IMetaDataTables::GetUserString (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetUserString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetUserString
helpviewer_keywords:
- IMetaDataTables::GetUserString method [.NET Framework metadata]
- GetUserString method, IMetaDataTables interface [.NET Framework metadata]
ms.assetid: 35b8f0d6-9aba-4714-adb2-62020a38fb7e
topic_type:
- apiref
ms.openlocfilehash: 0909bfb2dbf4e6a34b746da7397a82845c2129c2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99687693"
---
# <a name="imetadatatablesgetuserstring-method"></a>IMetaDataTables::GetUserString (Método)

Obtiene la cadena codificada de forma rígida en el índice especificado de la columna de cadena en el ámbito actual.

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT GetUserString (
    [in]  ULONG       ixUserString,
    [out] ULONG       *pcbData,
    [out] const void  **ppData
);
```

## <a name="parameters"></a>Parámetros

`ixUserString`\
de Valor de índice del que se recuperará la cadena codificada de forma rígida.

`pcbData`\
enuncia Puntero al tamaño de `ppData` .

`ppData`\
enuncia Un puntero a un puntero a la cadena devuelta.

## <a name="requirements"></a>Requisitos

**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).

**Encabezado:** Cor. h

**Biblioteca:** Se usa como un recurso en MsCorEE.dll

**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]

## <a name="see-also"></a>Vea también

- [IMetaDataTables (Interfaz)](imetadatatables-interface.md)
- [IMetaDataTables2 (Interfaz)](imetadatatables2-interface.md)
