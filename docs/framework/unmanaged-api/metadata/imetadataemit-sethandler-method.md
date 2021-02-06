---
description: 'Más información acerca de: IMetaDataEmit:: SetHandler (método)'
title: IMetaDataEmit::SetHandler (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetHandler
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetHandler
helpviewer_keywords:
- IMetaDataEmit::SetHandler method [.NET Framework metadata]
- SetHandler method [.NET Framework metadata]
ms.assetid: c6c1aaaf-e2cd-407c-b73e-fbe6ffd83bb3
topic_type:
- apiref
ms.openlocfilehash: 07ebf8eef816d373e92a82fc84adacfe5a8599fb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99657884"
---
# <a name="imetadataemitsethandler-method"></a>IMetaDataEmit::SetHandler (Método)

Establece el método al que hace referencia el `IUnknown` puntero especificado como una devolución de llamada de notificación para las reasignaciones de token.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SetHandler (
    [in]  IUnknown    *pUnk  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `pUnk`  
 de Controlador que se va a registrar.  
  
## <a name="remarks"></a>Observaciones  

 El motor de metadatos envía notificaciones mediante el método proporcionado por `SetHandler` , a los compiladores que no generan registros de una manera optimizada y que desean optimizar los registros guardados.  
  
 Si no se proporciona el método de devolución de llamada a través de `SetHandler` , no se realizará ninguna optimización al guardar, excepto en el caso de que se hayan combinado varios ámbitos de importación mediante `IMapToken` Merge para cada ámbito.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se usa como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataEmit (Interfaz)](imetadataemit-interface.md)
- [IMetaDataEmit2 (Interfaz)](imetadataemit2-interface.md)
