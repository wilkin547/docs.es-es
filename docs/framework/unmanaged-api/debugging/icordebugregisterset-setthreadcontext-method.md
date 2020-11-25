---
title: ICorDebugRegisterSet::SetThreadContext (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet.SetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet::SetThreadContext
helpviewer_keywords:
- ICorDebugRegisterSet::SetThreadContext method [.NET Framework debugging]
- SetThreadContext method, ICorDebugRegisterSet interface [.NET Framework debugging]
ms.assetid: 73afa930-32cb-4c40-81f8-83e8e6fbe213
topic_type:
- apiref
ms.openlocfilehash: 66e8cf3f73e92f58765b1fa98b3eef11b976094c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95712279"
---
# <a name="icordebugregistersetsetthreadcontext-method"></a>ICorDebugRegisterSet::SetThreadContext (Método)

`SetThreadContext` no se implementa en la versión .NET Framework 2,0. No llame a este método.  
  
> [!NOTE]
> Use la operación de nivel superior [ICorDebugNativeFrame:: setip](icordebugnativeframe-setip-method.md) para establecer el contexto de un subproceso.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SetThreadContext (  
    [in] ULONG32 contextSize,  
    [in, length_is(contextSize),  
         size_is(contextSize)] BYTE context[]  
);  
```  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** 1,1, 1,0  
  
## <a name="see-also"></a>Consulte también

- [ICorDebugRegisterSet (Interfaz)](icordebugregisterset-interface.md)
- [ICorDebugRegisterSet2 (Interfaz)](icordebugregisterset2-interface.md)
