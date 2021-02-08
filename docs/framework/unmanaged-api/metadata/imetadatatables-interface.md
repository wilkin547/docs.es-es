---
description: 'Más información acerca de: IMetaDataTables (interfaz)'
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
ms.openlocfilehash: c3edf504586bad1252c36d6e8254193eaf9cc26d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799278"
---
# <a name="imetadatatables-interface"></a>IMetaDataTables (Interfaz)

Proporciona métodos para el almacenamiento y la recuperación de información de metadatos en tablas.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método GetBlob](imetadatatables-getblob-method.md)|Obtiene un puntero al objeto binario grande (BLOB) en el índice de columna especificado.|  
|[Método GetBlobHeapSize](imetadatatables-getblobheapsize-method.md)|Obtiene el tamaño, en bytes, del montón de BLOBs.|  
|[Método GetCodedTokenInfo](imetadatatables-getcodedtokeninfo-method.md)|Obtiene un puntero a una matriz de tokens asociada al índice de fila especificado.|  
|[Método GetColumn](imetadatatables-getcolumn-method.md)|Obtiene un puntero a los valores contenidos en la columna en el índice de columna especificado, en la tabla en el índice de tabla especificado.|  
|[Método GetColumnInfo](imetadatatables-getcolumninfo-method.md)|Obtiene datos sobre la columna especificada de la tabla especificada.|  
|[Método GetGuid](imetadatatables-getguid-method.md)|Obtiene un GUID de la fila en el índice especificado.|  
|[Método GetGuidHeapSize](imetadatatables-getguidheapsize-method.md)|Obtiene el tamaño, en bytes, del montón GUID.|  
|[Método GetNextBlob](imetadatatables-getnextblob-method.md)|Obtiene el índice del siguiente BLOB de la tabla.|  
|[Método GetNextGuid](imetadatatables-getnextguid-method.md)|Obtiene el índice del siguiente valor de GUID en la columna de la tabla actual.|  
|[Método GetNextString](imetadatatables-getnextstring-method.md)|Obtiene el índice de la cadena siguiente en la columna de la tabla actual.|  
|[Método GetNextUserString](imetadatatables-getnextuserstring-method.md)|Obtiene el índice de la fila que contiene la siguiente cadena codificada de forma rígida en la columna de la tabla actual.|  
|[Método GetNumTables](imetadatatables-getnumtables-method.md)|Obtiene el número de tablas en el ámbito de la `IMetaDataTables` instancia actual.|  
|[Método GetRow](imetadatatables-getrow-method.md)|Obtiene la fila en el índice de fila especificado de la tabla en el índice de tabla especificado.|  
|[GetString (Método)](imetadatatables-getstring-method.md)|Obtiene la cadena en el índice especificado de la columna de tabla del ámbito de referencia actual.|  
|[Método GetStringHeapSize](imetadatatables-getstringheapsize-method.md)|Obtiene el tamaño, en bytes, del montón de cadenas.|  
|[Método GetTableIndex](imetadatatables-gettableindex-method.md)|Obtiene el índice de la tabla a la que hace referencia el token especificado.|  
|[Método GetTableInfo](imetadatatables-gettableinfo-method.md)|Obtiene el nombre, el tamaño de la fila, el número de filas, el número de columnas y el índice de columna de clave de la tabla en el índice de tabla especificado.|  
|[Método GetUserString](imetadatatables-getuserstring-method.md)|Obtiene la cadena codificada de forma rígida en el índice especificado de la columna de cadena en el ámbito actual.|  
|[Método GetUserStringHeapSize](imetadatatables-getuserstringheapsize-method.md)|Obtiene el tamaño, en bytes, del montón de cadena de usuario.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se usa como un recurso en MsCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de metadatos](metadata-interfaces.md)
- [IMetaDataTables2 (Interfaz)](imetadatatables2-interface.md)
