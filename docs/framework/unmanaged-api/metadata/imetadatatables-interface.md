---
title: IMetaDataTables (Interfaz)
ms.date: 03/30/2017
api_name:
- IMetaDataTables
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables
helpviewer_keywords:
- IMetaDataTables interface [.NET Framework metadata]
ms.assetid: 31272cce-506a-4f18-bcbf-01ee45e36356
topic_type:
- apiref
ms.openlocfilehash: 17305f2c088dd6f479da4c823d3db0fd50c0b3d7
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74443223"
---
# <a name="imetadatatables-interface"></a>IMetaDataTables (Interfaz)
Proporciona métodos para el almacenamiento y la recuperación de información de metadatos en tablas.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[GetBlob (método)](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getblob-method.md)|Obtiene un puntero al objeto binario grande (BLOB) en el índice de columna especificado.|  
|[GetBlobHeapSize (método)](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getblobheapsize-method.md)|Obtiene el tamaño, en bytes, del montón de BLOBs.|  
|[GetCodedTokenInfo (método)](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getcodedtokeninfo-method.md)|Obtiene un puntero a una matriz de tokens asociada al índice de fila especificado.|  
|[GetColumn (método)](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getcolumn-method.md)|Obtiene un puntero a los valores contenidos en la columna en el índice de columna especificado, en la tabla en el índice de tabla especificado.|  
|[GetColumnInfo (método)](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getcolumninfo-method.md)|Obtiene datos sobre la columna especificada de la tabla especificada.|  
|[GetGuid (método)](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getguid-method.md)|Obtiene un GUID de la fila en el índice especificado.|  
|[GetGuidHeapSize (método)](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getguidheapsize-method.md)|Obtiene el tamaño, en bytes, del montón GUID.|  
|[GetNextBlob (método)](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextblob-method.md)|Obtiene el índice del siguiente BLOB de la tabla.|  
|[GetNextGuid (método)](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextguid-method.md)|Obtiene el índice del siguiente valor de GUID en la columna de la tabla actual.|  
|[GetNextString (método)](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextstring-method.md)|Obtiene el índice de la cadena siguiente en la columna de la tabla actual.|  
|[GetNextUserString (método)](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextuserstring-method.md)|Obtiene el índice de la fila que contiene la siguiente cadena codificada de forma rígida en la columna de la tabla actual.|  
|[GetNumTables (método)](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnumtables-method.md)|Obtiene el número de tablas en el ámbito de la instancia de `IMetaDataTables` actual.|  
|[GetRow (método)](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getrow-method.md)|Obtiene la fila en el índice de fila especificado de la tabla en el índice de tabla especificado.|  
|[GetString (método)](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getstring-method.md)|Obtiene la cadena en el índice especificado de la columna de tabla del ámbito de referencia actual.|  
|[GetStringHeapSize (método)](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getstringheapsize-method.md)|Obtiene el tamaño, en bytes, del montón de cadenas.|  
|[GetTableIndex (método)](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-gettableindex-method.md)|Obtiene el índice de la tabla a la que hace referencia el token especificado.|  
|[GetTableInfo (método)](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-gettableinfo-method.md)|Obtiene el nombre, el tamaño de la fila, el número de filas, el número de columnas y el índice de columna de clave de la tabla en el índice de tabla especificado.|  
|[GetUserString (método)](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getuserstring-method.md)|Obtiene la cadena codificada de forma rígida en el índice especificado de la columna de cadena en el ámbito actual.|  
|[GetUserStringHeapSize (método)](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getuserstringheapsize-method.md)|Obtiene el tamaño, en bytes, del montón de cadena de usuario.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se utiliza como recurso en MsCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [IMetaDataTables2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
