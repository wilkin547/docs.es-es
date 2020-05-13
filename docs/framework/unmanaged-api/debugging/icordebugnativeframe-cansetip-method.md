---
title: ICorDebugNativeFrame::CanSetIP (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.CanSetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::CanSetIP
helpviewer_keywords:
- ICorDebugNativeFrame::CanSetIP method [.NET Framework debugging]
- CanSetIP method, ICorDebugNativeFrame interface [.NET Framework debugging]
ms.assetid: 13258ac6-f4e4-4f66-8fc3-f1244417a3c3
topic_type:
- apiref
ms.openlocfilehash: 21890f8130ec677cb88f2f5d7ef648aa19e67e71
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213067"
---
# <a name="icordebugnativeframecansetip-method"></a>ICorDebugNativeFrame::CanSetIP (Método)
Obtiene un valor HRESULT que indica si es seguro establecer el puntero de instrucción (IP) en la ubicación de desplazamiento especificada en código nativo.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT CanSetIP (  
    [in] ULONG32            nOffset  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `nOffset`  
 de La configuración deseada para el puntero de instrucción.  
  
## <a name="remarks"></a>Observaciones  
 Use el `CanSetIP` método antes de llamar al método [ICorDebugNativeFrame:: setip](icordebugnativeframe-setip-method.md) . Si `CanSetIP` devuelve un valor HRESULT distinto de S_OK, todavía puede invocar `ICorDebugNativeFrame::SetIP` , pero no hay ninguna garantía de que el depurador siga la ejecución segura y correcta del código que se está depurando.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también
