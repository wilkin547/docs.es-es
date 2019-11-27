---
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
ms.openlocfilehash: 5936ca837c9ab452e992fcb09aacb476ab37316a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431437"
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
enuncia Puntero al tamaño de `ppData`.

`ppData`\
enuncia Un puntero a un puntero a la cadena devuelta.

## <a name="requirements"></a>Requisitos

**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).

**Encabezado:** Cor. h

**Biblioteca:** Se utiliza como recurso en MsCorEE. dll

**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]

## <a name="see-also"></a>Vea también

- [IMetaDataTables (interfaz)](imetadatatables-interface.md)
- [IMetaDataTables2 (interfaz)](imetadatatables2-interface.md)
