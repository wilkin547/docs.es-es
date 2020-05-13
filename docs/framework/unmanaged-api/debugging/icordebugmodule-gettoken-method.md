---
title: ICorDebugModule::GetToken (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetToken
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetToken
helpviewer_keywords:
- ICorDebugModule::GetToken method [.NET Framework debugging]
- GetToken method, ICorDebugModule interface [.NET Framework debugging]
ms.assetid: f759f87a-18ae-4c1a-8300-29b803432d0a
topic_type:
- apiref
ms.openlocfilehash: a6aff37a480460bfed7064d59b4c5276daf3207c
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212508"
---
# <a name="icordebugmodulegettoken-method"></a>ICorDebugModule::GetToken (Método)
Obtiene el token para la entrada de la tabla para este módulo.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetToken(  
    [out] mdModule *pToken  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pToken`  
 enuncia Puntero al `mdModule` token que hace referencia a los metadatos del módulo.  
  
## <a name="remarks"></a>Observaciones  
 El token se puede pasar a las interfaces de importación de metadatos [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md), [IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)y [IMetaDataAssemblyImport](../metadata/imetadataassemblyimport-interface.md) .  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Metadatos](../metadata/index.md)
