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
ms.openlocfilehash: b7d3fbafaab6d43fa89d45855628dbd6b9ab81e2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95696224"
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
  
## <a name="remarks"></a>Comentarios  

 Si se permite editar y continuar en esta función, el `GetILCode` método obtendrá el código MSIL correspondiente a la versión editada de esta función del código en el Common Language Runtime (CLR).  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
