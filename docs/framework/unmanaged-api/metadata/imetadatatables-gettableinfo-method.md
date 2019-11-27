---
title: IMetaDataTables::GetTableInfo (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetTableInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetTableInfo
helpviewer_keywords:
- IMetaDataTables::GetTableInfo method [.NET Framework metadata]
- GetTableInfo method [.NET Framework metadata]
ms.assetid: 50cbe557-2322-41aa-8e0d-f967602eaa0f
topic_type:
- apiref
ms.openlocfilehash: 662b628f3cc6d2d7138f56820beaccee9c5d9e81
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74426658"
---
# <a name="imetadatatablesgettableinfo-method"></a>IMetaDataTables::GetTableInfo (Método)
Obtiene el nombre, el tamaño de la fila, el número de filas, el número de columnas y el índice de la columna de clave de la tabla especificada.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetTableInfo (  
    [in]  ULONG       ixTbl,  
    [out] ULONG       *pcbRow,  
    [out] ULONG       *pcRows,  
    [out] ULONG       *pcCols,  
    [out] ULONG       *piKey,  
    [out] const char  **ppName  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `ixTbl`  
 de Identificador de la tabla cuyas propiedades se van a devolver.  
  
 `pcbRow`  
 enuncia Puntero al tamaño, en bytes, de una fila de la tabla.  
  
 `pcRows`  
 enuncia Puntero al número de filas de la tabla.  
  
 `pcCols`  
 enuncia Puntero al número de columnas de la tabla.  
  
 `piKey`  
 enuncia Puntero al índice de la columna de clave o-1 si la tabla no tiene ninguna columna de clave.  
  
 `ppName`  
 enuncia Un puntero a un puntero al nombre de la tabla.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se utiliza como recurso en MsCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataTables (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [IMetaDataTables2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
