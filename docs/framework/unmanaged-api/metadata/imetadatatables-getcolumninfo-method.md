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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: dd67d9faafedf4fb92c69618d4464ebb2ce47dcc
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2019
ms.locfileid: "72774258"
---
# <a name="imetadatatablesgetcolumninfo-method"></a>IMetaDataTables::GetColumnInfo (Método)
Obtiene datos sobre la columna especificada de la tabla especificada.  
  
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
 de Índice de la tabla deseada.  
  
 `ixCol`  
 de Índice de la columna deseada.  
  
 `poCol`  
 enuncia Puntero al desplazamiento de la columna de la fila.  
  
 `pcbCol`  
 enuncia Puntero al tamaño, en bytes, de la columna.  
  
 `pType`  
 enuncia Puntero al tipo de los valores de la columna.  
  
 `ppName`  
 enuncia Un puntero a un puntero al nombre de la columna.  
 
## <a name="remarks"></a>Comentarios

El tipo de columna devuelto está dentro de un intervalo de valores:

| pType                    | Descripción   | Función auxiliar                   |
|--------------------------|---------------|-----------------------------------|
| `0`..`iRidMax`<br>(0.. 63)   | Libra           | **IsRidType**<br>**IsRidOrToken** |
| `iCodedToken`..`iCodedTokenMax`<br>(64.. 95) | Token codificado | **IsCodedTokenType** <br>**IsRidOrToken** |
| `iSHORT` (96)            | Int16         | **IsFixedType**                   |
| `iUSHORT` (97)           | UInt16        | **IsFixedType**                   |
| `iLONG` (98)             | Int32         | **IsFixedType**                   |
| `iULONG` (99)            | UInt32        | **IsFixedType**                   |
| `iBYTE` (100)            | Byte          | **IsFixedType**                   |
| `iSTRING` (101)          | String        | **IsHeapType**                    |
| `iGUID` (102)            | GUID          | **IsHeapType**                    |
| `iBLOB` (103)            | Blob          | **IsHeapType**                    |

Los valores que se almacenan en el *montón* (es decir, `IsHeapType == true`) se pueden leer mediante:

- `iSTRING`: **IMetadataTables. GetString**
- `iGUID`: **IMetadataTables. GetGUID**
- `iBLOB`: **IMetadataTables. GetBlob**

> [!IMPORTANT]
> Para usar las constantes definidas en la tabla anterior, incluya la Directiva `#define _DEFINE_META_DATA_META_CONSTANTS` proporciona el archivo de encabezado *Cor. h* .

## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se utiliza como recurso en MsCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataTables (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [IMetaDataTables2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
