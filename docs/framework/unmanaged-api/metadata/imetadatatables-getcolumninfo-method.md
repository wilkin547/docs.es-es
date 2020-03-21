---
title: IMetaDataTables::GetColumnInfo (Método)
ms.date: 10/10/2019
api_name:
- IMetaDataTables.GetColumnInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetColumnInfo
helpviewer_keywords:
- IMetaDataTables::GetColumnInfo method [.NET Framework metadata]
- GetColumnInfo method [.NET Framework metadata]
ms.assetid: 68c160ea-ae7d-4750-985d-a038b2c8e7d9
topic_type:
- apiref
ms.openlocfilehash: cc8aac32149fed952737d928e16a8f6efc448c79
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177120"
---
# <a name="imetadatatablesgetcolumninfo-method"></a>IMetaDataTables::GetColumnInfo (Método)
Obtiene datos sobre la columna especificada en la tabla especificada.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetColumnInfo (
    [in]  ULONG        ixTbl,  
    [in]  ULONG        ixCol,  
    [out] ULONG        *poCol,  
    [out] ULONG        *pcbCol,  
    [out] ULONG        *pType,  
    [out] const char   **ppName  
);  
```  
  
## <a name="parameters"></a>Parámetros
=======

 `ixTbl`  
 [en] El índice de la tabla deseada.  
  
 `ixCol`  
 [en] El índice de la columna deseada.  
  
 `poCol`  
 [fuera] Un puntero al desplazamiento de la columna de la fila.  
  
 `pcbCol`  
 [fuera] Un puntero al tamaño, en bytes, de la columna.  
  
 `pType`  
 [fuera] Un puntero al tipo de los valores de la columna.  
  
 `ppName`  
 [fuera] Puntero a un puntero al nombre de la columna.  

## <a name="remarks"></a>Observaciones

El tipo de columna devuelto se encuentra dentro de un intervalo de valores:

| pType                    | Descripción   | Función auxiliar                   |
|--------------------------|---------------|-----------------------------------|
| `0`..`iRidMax`<br>(0..63)   | Librar           | **IsRidType**<br>**IsridOrToken** |
| `iCodedToken`..`iCodedTokenMax`<br>(64..95) | Token codificado | **IsCodedTokenType** <br>**IsridOrToken** |
| `iSHORT`(96)            | Int16         | **IsFixedType**                   |
| `iUSHORT`(97)           | UInt16        | **IsFixedType**                   |
| `iLONG`(98)             | Int32         | **IsFixedType**                   |
| `iULONG`(99)            | UInt32        | **IsFixedType**                   |
| `iBYTE`(100)            | Byte          | **IsFixedType**                   |
| `iSTRING`(101)          | String        | **IsHeapType**                    |
| `iGUID`(102)            | Guid          | **IsHeapType**                    |
| `iBLOB`(103)            | Blob          | **IsHeapType**                    |

Los valores que se almacenan en `IsHeapType == true`el *montón* (es decir, ) se pueden leer mediante:

- `iSTRING`: **IMetadataTables.GetString**
- `iGUID`: **IMetadataTables.GetGUID**
- `iBLOB`: **IMetadataTables.GetBlob**

> [!IMPORTANT]
> Para utilizar las constantes definidas en la `#define _DEFINE_META_DATA_META_CONSTANTS` tabla anterior, incluya la directiva proporcionada por el archivo de encabezado *cor.h.*

## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor.h  
  
 **Biblioteca:** Se utiliza como recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [IMetaDataTables (Interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [IMetaDataTables2 (Interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
