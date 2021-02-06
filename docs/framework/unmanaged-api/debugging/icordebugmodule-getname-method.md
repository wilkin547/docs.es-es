---
description: 'Más información acerca de: ICorDebugModule:: GetName (método)'
title: ICorDebugModule::GetName (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetName
helpviewer_keywords:
- ICorDebugModule::GetName method [.NET Framework debugging]
- GetName method, ICorDebugModule interface [.NET Framework debugging]
ms.assetid: db499637-7ba9-421e-b8b1-35856995e80b
topic_type:
- apiref
ms.openlocfilehash: 0f81271b2be283621027f4c835b6f220a383d771
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99660218"
---
# <a name="icordebugmodulegetname-method"></a>ICorDebugModule::GetName (Método)

Obtiene el nombre de archivo del módulo.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp
HRESULT GetName(  
    [in] ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `cchname`  
 [in] Tamaño de la matriz `szName`.  
  
 `pcchName`  
 de Puntero a la longitud del nombre devuelto.  
  
 `szName`  
 enuncia Matriz que almacena el nombre devuelto.  
  
## <a name="remarks"></a>Observaciones  

 El `GetName` método devuelve un S_OK HRESULT si el nombre de archivo del módulo coincide con el nombre en el disco. `GetName` Devuelve un S_FALSE HRESULT si se ha fabricado el nombre, por ejemplo para un módulo dinámico o en memoria.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también
