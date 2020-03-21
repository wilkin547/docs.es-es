---
title: IMetaDataTables::GetColumn (Método)
ms.date: 02/25/2019
api_name:
- IMetaDataTables.GetColumn
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetColumn
helpviewer_keywords:
- IMetaDataTables::GetColumn method [.NET Framework metadata]
- GetColumn method [.NET Framework metadata]
ms.assetid: 1032055b-cabb-45c5-a50e-7e853201b175
topic_type:
- apiref
ms.openlocfilehash: f43d4d1547cbe92f325950e1697dada83b42c4f3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177134"
---
# <a name="imetadatatablesgetcolumn-method"></a>IMetaDataTables::GetColumn (Método)
Obtiene un puntero al valor contenido en la celda de la columna y fila especificadas en la tabla especificada.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetColumn (
    [in]  ULONG   ixTbl,  
    [in]  ULONG   ixCol,  
    [in]  ULONG   rid,  
    [out] ULONG   *pVal  
);  
```  
  
## <a name="parameters"></a>Parámetros

 `ixTbl`  
 [en] El índice de la tabla.  
  
 `ixCol`  
 [en] El índice de la columna de la tabla.  
  
 `rid`  
 [en] El índice de la fila de la tabla.  
  
 `pVal`  
 [fuera] Un puntero al valor de la celda.  

## <a name="remarks"></a>Observaciones

La interpretación del valor `pVal` devuelto depende del tipo de la columna. El tipo de columna se puede determinar llamando a [IMetaDataTables.GetColumnInfo](imetadatatables-getcolumninfo-method.md).

- El **GetColumn** método convierte automáticamente columnas de tipo **Rid** o `mdToken` **CodedToken** en valores completos de 32 bits.
- También convierte automáticamente valores de 8 bits o 16 bits en valores completos de 32 bits.
- Para las columnas de tipo *de montón,* el *pVal* devuelto será un índice en el montón correspondiente.

| Tipo de columna              | pVal contiene | Comentario                          |
|--------------------------|---------------|-----------------------------------|
| `0`..`iRidMax`<br>(0..63)  | mdToken     | *pVal* contendrá un token completo. La función convierte automáticamente el Rid en un token completo. |
| `iCodedToken`..`iCodedTokenMax`<br>(64..95) | mdToken | A la vuelta, *pVal* contendrá un token completo. La función descomprime automáticamente el CodedToken en un token completo. |
| `iSHORT`(96)            | Int16         | Firma-extendida automáticamente a 32 bits.  |
| `iUSHORT`(97)           | UInt16        | Firma-extendida automáticamente a 32 bits.  |
| `iLONG`(98)             | Int32         |                                        |
| `iULONG`(99)            | UInt32        |                                        |
| `iBYTE`(100)            | Byte          | Firma-extendida automáticamente a 32 bits.  |
| `iSTRING`(101)          | Indice de montón de cadenas | *pVal* es un índice en el montón String. Use [IMetadataTables::GetString](imetadatatables-getstring-method.md) para obtener el valor de cadena de columna real. |
| `iGUID`(102)            | Guid índice de montón | *pVal* es un índice en el montón Guid. Utilice [IMetadataTables::GetGuid](imetadatatables-getguid-method.md) para obtener el valor de Guid de la columna real. |
| `iBLOB`(103)            | Indice de montón de blobs | *pVal* es un índice en el montón de Blob. Use [IMetadataTables::GetBlob](imetadatatables-getblob-method.md) para obtener el valor de Blob de la columna real. |
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor.h  
  
 **Biblioteca:** Se utiliza como recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [IMetaDataTables (Interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [IMetaDataTables2 (Interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
