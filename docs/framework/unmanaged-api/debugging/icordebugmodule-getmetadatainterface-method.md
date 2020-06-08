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
ms.openlocfilehash: f5d0dd7a99087b21a5f827e4dce0f6342ae7b25a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501773"
---
# <a name="icordebugmodulegetmetadatainterface-method"></a>ICorDebugModule::GetMetaDataInterface (Método)
Obtiene un objeto de interfaz de metadatos que se puede utilizar para examinar los metadatos del módulo.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetMetaDataInterface (  
    [in] REFIID      riid,  
    [out] IUnknown **ppObj  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `riid`  
 de IDENTIFICADOR de referencia que especifica la interfaz de metadatos.  
  
 `ppObj`  
 enuncia Puntero a la dirección de un `T:IUnknown` objeto que es una de las [interfaces de metadatos](../metadata/metadata-interfaces.md).  
  
## <a name="remarks"></a>Comentarios  
 El depurador puede utilizar el `GetMetaDataInterface` método para realizar una copia de los metadatos originales de un módulo, que debe hacer para editar ese módulo. El depurador llama `GetMetaDataInterface` a para obtener un objeto de interfaz [IMetaDataEmit](../metadata/imetadataemit-interface.md) para el módulo y, a continuación, llama a [IMetaDataEmit:: savetomemory (](../metadata/imetadataemit-savetomemory-method.md) para guardar una copia de los metadatos del módulo en la memoria.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también:

- [Metadata](../metadata/index.md)
