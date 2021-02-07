---
description: 'Más información acerca de: IMetaDataTables:: GetColumnInfo (método)'
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
ms.openlocfilehash: 21980567c5f9b364362f7e3ff02ee3a5e60b01ee
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99688239"
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

## <a name="remarks"></a>Observaciones

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
| `iGUID` (102)            | Guid          | **IsHeapType**                    |
| `iBLOB` (103)            | Blob          | **IsHeapType**                    |

Los valores que se almacenan en el *montón* (es decir, `IsHeapType == true` ) se pueden leer mediante:

- `iSTRING`: **IMetadataTables. GetString**
- `iGUID`: **IMetadataTables. GetGUID**
- `iBLOB`: **IMetadataTables. GetBlob**

> [!IMPORTANT]
> Para usar las constantes definidas en la tabla anterior, incluya la directiva `#define _DEFINE_META_DATA_META_CONSTANTS` proporcionada por el archivo de encabezado *Cor. h* .

## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se usa como un recurso en MsCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataTables (Interfaz)](imetadatatables-interface.md)
- [IMetaDataTables2 (Interfaz)](imetadatatables2-interface.md)
