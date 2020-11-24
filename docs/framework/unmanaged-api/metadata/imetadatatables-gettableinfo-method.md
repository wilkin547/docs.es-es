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
ms.openlocfilehash: 65943ac169106a95feaff7d44017444e65764b60
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95672544"
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

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se usa como un recurso en MsCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [IMetaDataTables (Interfaz)](imetadatatables-interface.md)
- [IMetaDataTables2 (Interfaz)](imetadatatables2-interface.md)
