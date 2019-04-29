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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645187"
---
# <a name="imetadatatables-interface"></a>IMetaDataTables (Interfaz)
Proporciona métodos para el almacenamiento y la recuperación de información de metadatos en tablas.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[GetBlob (método)](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getblob-method.md)|Obtiene un puntero para el objeto binario grande (BLOB) en el índice de la columna especificada.|  
|[GetBlobHeapSize (método)](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getblobheapsize-method.md)|Obtiene el tamaño, en bytes, del montón de objetos binarios.|  
|[GetCodedTokenInfo (método)](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getcodedtokeninfo-method.md)|Obtiene un puntero a una matriz de tokens asociados con el índice de fila especificado.|  
|[GetColumn (método)](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getcolumn-method.md)|Obtiene un puntero a los valores contenidos en la columna en el índice de columna especificado en la tabla en el índice de la tabla especificada.|  
|[GetColumnInfo (método)](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getcolumninfo-method.md)|Obtiene datos sobre la columna especificada en la tabla especificada.|  
|[GetGuid (método)](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getguid-method.md)|Obtiene un GUID de la fila en el índice especificado.|  
|[GetGuidHeapSize (método)](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getguidheapsize-method.md)|Obtiene el tamaño, en bytes, del montón GUID.|  
|[GetNextBlob (método)](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextblob-method.md)|Obtiene el índice del siguiente BLOB en la tabla.|  
|[GetNextGuid (método)](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextguid-method.md)|Obtiene el índice del siguiente valor de GUID de la columna de tabla actual.|  
|[GetNextString (método)](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextstring-method.md)|Obtiene el índice de la cadena siguiente en la columna de tabla actual.|  
|[GetNextUserString (método)](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextuserstring-method.md)|Obtiene el índice de la fila que contiene la siguiente cadena codificada de forma rígida en la columna de tabla actual.|  
|[GetNumTables (método)](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnumtables-method.md)|Obtiene el número de tablas en el ámbito del elemento actual `IMetaDataTables` instancia.|  
|[GetRow (método)](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getrow-method.md)|Obtiene la fila en el índice de fila especificado, en la tabla en el índice de la tabla especificada.|  
|[GetString (método)](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getstring-method.md)|Obtiene la cadena en el índice especificado de la columna de tabla en el ámbito de referencia actual.|  
|[GetStringHeapSize (método)](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getstringheapsize-method.md)|Obtiene el tamaño, en bytes, del montón de cadenas.|  
|[GetTableIndex (método)](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-gettableindex-method.md)|Obtiene el índice de la tabla al que hace referencia el token especificado.|  
|[GetTableInfo (método)](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-gettableinfo-method.md)|Obtiene el nombre, el tamaño de fila, el número de filas, número de columnas y el índice de columna de clave de la tabla en el índice de la tabla especificada.|  
|[GetUserString (método)](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getuserstring-method.md)|Obtiene la cadena codificada de forma rígida en el índice especificado en la columna de cadena en el ámbito actual.|  
|[GetUserStringHeapSize (método)](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getuserstringheapsize-method.md)|Obtiene el tamaño, en bytes, del montón de cadenas de usuario.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Cor.h  
  
 **Biblioteca:** Usar como un recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [IMetaDataTables2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
