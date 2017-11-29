---
title: "IMetaDataTables::GetTableInfo (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataTables.GetTableInfo
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataTables::GetTableInfo
helpviewer_keywords:
- IMetaDataTables::GetTableInfo method [.NET Framework metadata]
- GetTableInfo method [.NET Framework metadata]
ms.assetid: 50cbe557-2322-41aa-8e0d-f967602eaa0f
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 0f4ccd9bbd1c7caa9bbeb548176d834dc8844213
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="imetadatatablesgettableinfo-method"></a>IMetaDataTables::GetTableInfo (Método)
Obtiene el nombre, el tamaño de fila, el número de filas, número de columnas y el índice de columna de clave de la tabla especificada.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetTableInfo (  
    [in]  ULONG       ixTbl,  
    [out] ULONG       *pcbRow,  
    [out] ULONG       *pcRows,  
    [out] ULONG       *pcCols,  
    [out] ULONG       *piKey,  
    [out] const char  **ppName  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `ixTbl`  
 [in] El identificador de la tabla cuyas propiedades se deben devolver.  
  
 `pcbRow`  
 [out] Un puntero al tamaño, en bytes, de una fila de tabla.  
  
 `pcRows`  
 [out] Un puntero al número de filas de la tabla.  
  
 `pcCols`  
 [out] Un puntero al número de columnas de la tabla.  
  
 `piKey`  
 [out] Un puntero al índice de la columna de clave, o -1 si la tabla no tiene ninguna columna de clave.  
  
 `ppName`  
 [out] Un puntero a un puntero al nombre de tabla.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor.h  
  
 **Biblioteca:** usada como recurso en MsCorEE.dll  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [IMetaDataTables (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [IMetaDataTables2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
