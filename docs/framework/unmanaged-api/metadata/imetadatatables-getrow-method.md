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
ms.openlocfilehash: 71f6c496816fec1a7537f5ccdfdc1b47d17da871
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177117"
---
# <a name="imetadatatablesgetrow-method"></a>IMetaDataTables::GetRow (Método)
Obtiene la fila en el índice de fila especificado, en la tabla en el índice de tabla especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetRow (
    [in]  ULONG   ixTbl,  
    [in]  ULONG   rid,  
    [out] void    **ppRow  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `ixTbl`  
 [en] El índice de la tabla desde la que se recuperará la fila.  
  
 `rid`  
 [en] El índice de la fila que se ha de obtener.  
  
 `ppRow`  
 [fuera] Un puntero a un puntero a la fila.  
  
## <a name="remarks"></a>Observaciones  

  No se recomienda el uso de este método, porque no devuelve resultados coherentes. Para obtener información acerca de la tabla GUID, consulte la documentación de Common Language Infrastructure (CLI), especialmente "Partition II: Metadata Definition and Semantics". La documentación está disponible en línea; Véanse los estándares de infraestructura de [ECMA C y Lenguaje Común](../../../standard/components.md#applicable-standards) y la norma [ECMA-335 - Common Language Infrastructure (CLI).](http://www.ecma-international.org/publications/standards/Ecma-335.htm)  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor.h  
  
 **Biblioteca:** Se utiliza como recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [IMetaDataTables (Interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [IMetaDataTables2 (Interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
