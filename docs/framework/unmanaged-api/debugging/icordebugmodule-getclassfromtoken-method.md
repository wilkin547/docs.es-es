---
title: ICorDebugModule::GetClassFromToken (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetClassFromToken
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetClassFromToken
helpviewer_keywords:
- GetClassFromToken method, ICorDebugModule interface [.NET Framework debugging]
- ICorDebugModule::GetClassFromToken method [.NET Framework debugging]
ms.assetid: 622a4d3c-0425-4c54-a7e4-0735377cdad2
topic_type:
- apiref
ms.openlocfilehash: 011d763ce244e18c7ba1203e18eb0700a8c8b13a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710238"
---
# <a name="icordebugmodulegetclassfromtoken-method"></a>ICorDebugModule::GetClassFromToken (Método)

Obtiene la clase especificada por el token de metadatos.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetClassFromToken(  
    [in]  mdTypeDef        typeDef,  
    [out] ICorDebugClass **ppClass  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `typedef`  
 de `mdTypeDef` Token de metadatos que hace referencia a los metadatos de una clase.  
  
 `ppClass`  
 enuncia Puntero a la dirección de un objeto ICorDebugClass que representa la clase.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
