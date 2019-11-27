---
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
ms.openlocfilehash: 6737275fb77e6f177832eb1d96214c37942bcd22
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74442158"
---
# <a name="imetadataemitsethandler-method"></a>IMetaDataEmit::SetHandler (Método)
Establece el método al que hace referencia el puntero de `IUnknown` especificado como una devolución de llamada de notificación para las reasignaciones de token.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SetHandler (   
    [in]  IUnknown    *pUnk  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pUnk`  
 de Controlador que se va a registrar.  
  
## <a name="remarks"></a>Comentarios  
 El motor de metadatos envía notificaciones mediante el método proporcionado por `SetHandler`, a los compiladores que no generan registros de una manera optimizada y que desean optimizar los registros guardados.  
  
 Si el método de devolución de llamada no se proporciona a través de `SetHandler`, no se realizará ninguna optimización al guardar, excepto en el caso de que se hayan combinado varios ámbitos de importación mediante `IMapToken` en la combinación para cada ámbito.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se utiliza como recurso en MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataEmit (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
