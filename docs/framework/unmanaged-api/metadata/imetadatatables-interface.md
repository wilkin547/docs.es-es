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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2b2298e2d67e8a50e11d53d864f0e78f3b549e45
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59131422"
---
# <a name="imetadatatables-interface"></a>IMetaDataTables (Interfaz)
Proporciona métodos para el almacenamiento y la recuperación de información de metadatos en tablas.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método GetBlob](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getblob-method.md)|Obtiene un puntero para el objeto binario grande (BLOB) en el índice de la columna especificada.|  
|[Método GetBlobHeapSize](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getblobheapsize-method.md)|Obtiene el tamaño, en bytes, del montón de objetos binarios.|  
|[Método GetCodedTokenInfo](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getcodedtokeninfo-method.md)|Obtiene un puntero a una matriz de tokens asociados con el índice de fila especificado.|  
|[Método GetColumn](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getcolumn-method.md)|Obtiene un puntero a los valores contenidos en la columna en el índice de columna especificado en la tabla en el índice de la tabla especificada.|  
|[Método GetColumnInfo](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getcolumninfo-method.md)|Obtiene datos sobre la columna especificada en la tabla especificada.|  
|[Método GetGuid](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getguid-method.md)|Obtiene un GUID de la fila en el índice especificado.|  
|[Método GetGuidHeapSize](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getguidheapsize-method.md)|Obtiene el tamaño, en bytes, del montón GUID.|  
|[Método GetNextBlob](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextblob-method.md)|Obtiene el índice del siguiente BLOB en la tabla.|  
|[Método GetNextGuid](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextguid-method.md)|Obtiene el índice del siguiente valor de GUID de la columna de tabla actual.|  
|[Método GetNextString](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextstring-method.md)|Obtiene el índice de la cadena siguiente en la columna de tabla actual.|  
|[Método GetNextUserString](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextuserstring-method.md)|Obtiene el índice de la fila que contiene la siguiente cadena codificada de forma rígida en la columna de tabla actual.|  
|[Método GetNumTables](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnumtables-method.md)|Obtiene el número de tablas en el ámbito del elemento actual `IMetaDataTables` instancia.|  
|[Método GetRow](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getrow-method.md)|Obtiene la fila en el índice de fila especificado, en la tabla en el índice de la tabla especificada.|  
|[Método GetString](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getstring-method.md)|Obtiene la cadena en el índice especificado de la columna de tabla en el ámbito de referencia actual.|  
|[Método GetStringHeapSize](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getstringheapsize-method.md)|Obtiene el tamaño, en bytes, del montón de cadenas.|  
|[Método GetTableIndex](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-gettableindex-method.md)|Obtiene el índice de la tabla al que hace referencia el token especificado.|  
|[Método GetTableInfo](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-gettableinfo-method.md)|Obtiene el nombre, el tamaño de fila, el número de filas, número de columnas y el índice de columna de clave de la tabla en el índice de la tabla especificada.|  
|[Método GetUserString](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getuserstring-method.md)|Obtiene la cadena codificada de forma rígida en el índice especificado en la columna de cadena en el ámbito actual.|  
|[Método GetUserStringHeapSize](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getuserstringheapsize-method.md)|Obtiene el tamaño, en bytes, del montón de cadenas de usuario.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Cor.h  
  
 **Biblioteca:** Usar como un recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [IMetaDataTables2 (Interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
