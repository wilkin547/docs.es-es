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
ms.openlocfilehash: 375c4b2cece0bdfd763ae383c5412c9e25614baf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177543"
---
# <a name="imetadataemitsethandler-method"></a>IMetaDataEmit::SetHandler (Método)
Establece el método al `IUnknown` que hace referencia el puntero especificado como una devolución de llamada de notificación para las reasignaciones de tokens.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SetHandler (
    [in]  IUnknown    *pUnk  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pUnk`  
 [en] El controlador que se debe registrar.  
  
## <a name="remarks"></a>Observaciones  
 El motor de metadatos envía una notificación mediante el método proporcionado por `SetHandler`, a los compiladores que no generan registros de forma optimizada y que desean optimizar los registros guardados.  
  
 Si el método de `SetHandler`devolución de llamada no se proporciona a través de `IMapToken` , no se realizará ninguna optimización al guardar, excepto cuando se han combinado varios ámbitos de importación mediante la combinación para cada ámbito.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor.h  
  
 **Biblioteca:** Se utiliza como recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [IMetaDataEmit (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
