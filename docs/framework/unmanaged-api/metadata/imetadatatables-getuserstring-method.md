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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0fefbab6b2ea9fbbfd90e03c41578a924f99c7a0
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57364169"
---
# <a name="imetadatatablesgetuserstring-method"></a>IMetaDataTables::GetUserString (Método)

Obtiene la cadena codificada de forma rígida en el índice especificado en la columna de cadena en el ámbito actual.

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
[in] El valor de índice desde el que se recuperará la cadena codificada de forma rígida.

`pcbData`\
[out] Un puntero al tamaño de `ppData`.

`ppData`\
[out] Un puntero a un puntero a la cadena devuelta.

## <a name="requirements"></a>Requisitos

**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).

**Encabezado**: Cor.h

**Biblioteca:** Usar como un recurso en MsCorEE.dll

**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]

## <a name="see-also"></a>Vea también

- [IMetaDataTables (interfaz)](imetadatatables-interface.md)
- [IMetaDataTables2 (interfaz)](imetadatatables2-interface.md)