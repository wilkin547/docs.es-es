---
title: IMetaDataTables::GetRow (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetRow
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetRow
helpviewer_keywords:
- IMetaDataTables::GetRow method [.NET Framework metadata]
- GetRow method [.NET Framework metadata]
ms.assetid: a7408d51-0bce-45a2-b58f-da4660bbc039
topic_type:
- apiref
ms.openlocfilehash: 9ac6eba18ae23dc80a8dc90383aa67cfe41b39ff
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937407"
---
# <a name="imetadatatablesgetrow-method"></a>IMetaDataTables::GetRow (Método)
Obtiene la fila en el índice de fila especificado de la tabla en el índice de tabla especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetRow (   
    [in]  ULONG   ixTbl,  
    [in]  ULONG   rid,  
    [out] void    **ppRow  
);  
```  
  
## <a name="parameters"></a>Parameters  
 `ixTbl`  
 de Índice de la tabla de la que se recuperará la fila.  
  
 `rid`  
 de Índice de la fila que se va a obtener.  
  
 `ppRow`  
 enuncia Un puntero a un puntero a la fila.  
  
## <a name="remarks"></a>Notas  

  No se recomienda el uso de este método, ya que no devuelve resultados coherentes. Para obtener información acerca de la tabla de GUID, consulte la documentación de Common Language Infrastructure (CLI), especialmente "partición II: definición y semántica de los metadatos". La documentación está disponible en línea; consulte [los C# estándares de ECMA y Common Language Infrastructure](../../../standard/components.md#applicable-standards) y [standard ECMA-335-Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se utiliza como recurso en MsCorEE. dll  
  
 **.NET Framework versiones**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataTables (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [IMetaDataTables2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
