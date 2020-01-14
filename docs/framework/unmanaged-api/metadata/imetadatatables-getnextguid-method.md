---
title: IMetaDataTables::GetNextGuid (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetNextGuid
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetNextGuid
helpviewer_keywords:
- GetNextGuid method [.NET Framework metadata]
- IMetaDataTables::GetNextGuid method [.NET Framework metadata]
ms.assetid: 68f6ea4d-9112-4d6b-93d9-e34f1e2f2496
topic_type:
- apiref
ms.openlocfilehash: d4055975287267d08d2c2224ff6ddaa39fca548d
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937795"
---
# <a name="imetadatatablesgetnextguid-method"></a>IMetaDataTables::GetNextGuid (Método)
Obtiene el índice del siguiente valor de GUID en la columna de la tabla actual.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetNextGuid (  
    [in]  ULONG   ixGuid,  
    [out] ULONG   *pNext  
);  
```  
  
## <a name="parameters"></a>Parameters  
 `ixGuid`  
 de Valor de índice de una columna de la tabla GUID.  
  
 `pNext`  
 enuncia Puntero al índice del siguiente valor de GUID.  
  
## <a name="remarks"></a>Notas  

  No se recomienda el uso de este método, ya que no devuelve resultados coherentes. Para obtener información acerca de la tabla de GUID, consulte la documentación de Common Language Infrastructure (CLI), especialmente "partición II: definición y semántica de los metadatos". La documentación está disponible en línea; consulte [los C# estándares de ECMA y Common Language Infrastructure](../../../standard/components.md#applicable-standards) y [standard ECMA-335-Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se utiliza como recurso en MsCorEE. dll  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataTables (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [IMetaDataTables2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
