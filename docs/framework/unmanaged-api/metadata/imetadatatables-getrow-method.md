---
description: 'Más información acerca de: IMetaDataTables:: GetRow (método)'
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
ms.openlocfilehash: f3888bbb53339dc60eb0c2d36f2d7383e5f8c228
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99687823"
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
  
## <a name="parameters"></a>Parámetros  

 `ixTbl`  
 de Índice de la tabla de la que se recuperará la fila.  
  
 `rid`  
 de Índice de la fila que se va a obtener.  
  
 `ppRow`  
 enuncia Un puntero a un puntero a la fila.  
  
## <a name="remarks"></a>Observaciones  

  No se recomienda el uso de este método, ya que no devuelve resultados coherentes. Para obtener información acerca de la tabla de GUID, consulte la documentación de Common Language Infrastructure (CLI), especialmente "partición II: definición y semántica de los metadatos". La documentación está disponible en línea; vea [ECMA C# and Common Language Infrastructure Standards](../../../standard/components.md#applicable-standards) y [standard ECMA-335-Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se usa como un recurso en MsCorEE.dll  
  
 **.NET Framework versiones**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataTables (Interfaz)](imetadatatables-interface.md)
- [IMetaDataTables2 (Interfaz)](imetadatatables2-interface.md)
