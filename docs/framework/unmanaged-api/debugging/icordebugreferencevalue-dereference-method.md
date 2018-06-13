---
title: ICorDebugReferenceValue::Dereference (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugReferenceValue.Dereference
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugReferenceValue::Dereference
helpviewer_keywords:
- ICorDebugReferenceValue::Dereference method [.NET Framework debugging]
- Dereference method [.NET Framework debugging]
ms.assetid: 5ec8cf76-3deb-4ce6-9a49-77a4c35d80b9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2a0fd1981e7da5af19cf3a422c6008d373e9ac92
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33416598"
---
# <a name="icordebugreferencevaluedereference-method"></a>ICorDebugReferenceValue::Dereference (Método)
Obtiene el objeto al que hace referencia.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT Dereference (  
    [out] ICorDebugValue  **ppValue  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `ppValue`  
 [out] Un puntero a la dirección de ICorDebugValue que representa el objeto al que apunta este objeto ICorDebugReferenceValue.  
  
## <a name="remarks"></a>Comentarios  
 La `ICorDebugValue` objeto es válido solo mientras aún no se ha deshabilitado su referencia.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
