---
title: ICorDebugFunction::GetILCode (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetILCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetILCode
helpviewer_keywords:
- ICorDebugFunction::GetILCode method [.NET Framework debugging]
- GetILCode method [.NET Framework debugging]
ms.assetid: f794dd47-a7cd-47f6-96e9-a41a4dae8e72
topic_type:
- apiref
ms.openlocfilehash: 8c7be2d48a30a9f649c6d86e4edbc10085195b68
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213626"
---
# <a name="icordebugfunctiongetilcode-method"></a>ICorDebugFunction::GetILCode (Método)
Obtiene la instancia de ICorDebugCode que representa el código de lenguaje intermedio de Microsoft (MSIL) asociado a este objeto ICorDebugFunction.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetILCode (  
    [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `ppCode`  
 enuncia Un puntero a la `ICorDebugCode` instancia de, o null, si la función no se compiló en MSIL.  
  
## <a name="remarks"></a>Observaciones  
 Si se permite editar y continuar en esta función, el `GetILCode` método obtendrá el código MSIL correspondiente a la versión editada de esta función del código en el Common Language Runtime (CLR).  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
