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
ms.openlocfilehash: 76d23fe9221ae5a07d79b8c5c1a7ad297922b003
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501253"
---
# <a name="imetadatatablesgetcolumn-method"></a>IMetaDataTables::GetColumn (Método)
Obtiene un puntero al valor contenido en la celda de la columna y la fila especificadas en la tabla especificada.  
  
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
 de Índice de la tabla.  
  
 `ixCol`  
 de Índice de la columna de la tabla.  
  
 `rid`  
 de Índice de la fila de la tabla.  
  
 `pVal`  
 enuncia Puntero al valor de la celda.  

## <a name="remarks"></a>Comentarios

La interpretación del valor devuelto a través `pVal` de depende del tipo de la columna. El tipo de columna se puede determinar mediante una llamada a [IMetaDataTables. GetColumnInfo](imetadatatables-getcolumninfo-method.md).

- El método **getcolumn (** convierte automáticamente las columnas de tipo **RID** o **CodedToken** a valores completos de 32 bits `mdToken` .
- También convierte automáticamente los valores de 8 o 16 bits en valores completos de 32 bits.
- En el caso de las columnas de tipo de *montón* , el *pval* devuelto será un índice en el montón correspondiente.

| Tipo de columna              | pVal contiene | Comentario                          |
|--------------------------|---------------|-----------------------------------|
| `0`..`iRidMax`<br>(0.. 63)  | mdToken     | *pval* contendrá un token completo. La función convierte automáticamente el RID en un token completo. |
| `iCodedToken`..`iCodedTokenMax`<br>(64.. 95) | mdToken | Después de la devolución, *pval* contendrá un token completo. La función descomprime automáticamente CodedToken en un token completo. |
| `iSHORT`(96)            | Int16         | El signo se extiende automáticamente a 32 bits.  |
| `iUSHORT`(97)           | UInt16        | El signo se extiende automáticamente a 32 bits.  |
| `iLONG`(98)             | Int32         |                                        |
| `iULONG`(99)            | UInt32        |                                        |
| `iBYTE`(100)            | Byte          | El signo se extiende automáticamente a 32 bits.  |
| `iSTRING`(101)          | Índice de montón de cadena | *pval* es un índice del montón de cadenas. Use [IMetadataTables:: GetString](imetadatatables-getstring-method.md) para obtener el valor de cadena de columna real. |
| `iGUID`(102)            | Índice de montón GUID | *pval* es un índice en el montón de GUID. Use [IMetadataTables:: GetGuid](imetadatatables-getguid-method.md) para obtener el valor de GUID de columna real. |
| `iBLOB`(103)            | Índice de montón de BLOB | *pval* es un índice del montón de blobs. Use [IMetadataTables:: GetBlob](imetadatatables-getblob-method.md) para obtener el valor de BLOB de columna real. |
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se utiliza como recurso en MsCorEE. dll  
  
 **.NET Framework versiones**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también:

- [IMetaDataTables (Interfaz)](imetadatatables-interface.md)
- [IMetaDataTables2 (Interfaz)](imetadatatables2-interface.md)
