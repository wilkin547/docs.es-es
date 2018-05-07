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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 60c9266806ef6b5d7e2e1c3a219a4485bc22d7f3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="imetadataemitsethandler-method"></a>IMetaDataEmit::SetHandler (Método)
Establece el método al que hace referencia especificado `IUnknown` puntero como una devolución de llamada de notificación para reasigna cada símbolo (token).  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT SetHandler (   
    [in]  IUnknown    *pUnk  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `pUnk`  
 [in] El controlador para registrar.  
  
## <a name="remarks"></a>Comentarios  
 El motor de metadatos envía la notificación mediante el método proporcionado por `SetHandler`, a los compiladores que no generan registros de forma optimizada y que le gustaría optimizar registros guardados.  
  
 Si el método de devolución de llamada no se proporciona a través de `SetHandler`, no se realizará ninguna optimización en Guardar excepto donde importación varios ámbitos se han combinado con `IMapToken` en cada ámbito de replicación de mezcla.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor.h  
  
 **Biblioteca:** usada como recurso en MSCorEE.dll  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [IMetaDataEmit (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [IMetaDataEmit2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
