---
title: ICorDebugModule::GetMetaDataInterface (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetMetaDataInterface
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetMetaDataInterface
helpviewer_keywords:
- ICorDebugModule::GetMetaDatainterface method [.NET Framework debugging]
- GetMetaDatainterface method [.NET Framework debugging]
ms.assetid: 30d906f2-cf35-4fa9-9d4c-0c31b58c9f3a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e5d28118ea1cc26f80ecc67ccedd160447aa69a4
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57479043"
---
# <a name="icordebugmodulegetmetadatainterface-method"></a>ICorDebugModule::GetMetaDataInterface (Método)
Obtiene un objeto de interfaz de metadatos que puede usarse para examinar los metadatos para el módulo.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetMetaDataInterface (  
    [in] REFIID      riid,  
    [out] IUnknown **ppObj  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `riid`  
 [in] El identificador de referencia que especifica la interfaz de metadatos.  
  
 `ppObj`  
 [out] Un puntero a la dirección de un `T:IUnknown` objeto que es uno de los [interfaces de metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md).  
  
## <a name="remarks"></a>Comentarios  
 Puede usar el depurador el `GetMetaDataInterface` método para realizar una copia de los metadatos originales para un módulo, lo que es necesario para poder editar ese módulo. El depurador llama `GetMetaDataInterface` para obtener un [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) objeto de interfaz del módulo, a continuación, llama a [SaveToMemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetomemory-method.md) para guardar una copia de los metadatos del módulo en memoria.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [Metadatos](../../../../docs/framework/unmanaged-api/metadata/index.md)
