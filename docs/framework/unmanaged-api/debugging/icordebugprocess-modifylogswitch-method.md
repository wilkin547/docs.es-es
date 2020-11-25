---
title: ICorDebugProcess::ModifyLogSwitch (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.ModifyLogSwitch
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::ModifyLogSwitch
helpviewer_keywords:
- ICorDebugProcess::ModifyLogSwitch method [.NET Framework debugging]
- ModifyLogSwitch method [.NET Framework debugging]
ms.assetid: 5fd30875-555e-4e96-877b-5dd266cde7c4
topic_type:
- apiref
ms.openlocfilehash: 3ac1b3606131f534195df9b6b59bf72b1bff27fb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724538"
---
# <a name="icordebugprocessmodifylogswitch-method"></a><span data-ttu-id="27e93-102">ICorDebugProcess::ModifyLogSwitch (Método)</span><span class="sxs-lookup"><span data-stu-id="27e93-102">ICorDebugProcess::ModifyLogSwitch Method</span></span>

<span data-ttu-id="27e93-103">Establece el nivel de gravedad del modificador de registro especificado.</span><span class="sxs-lookup"><span data-stu-id="27e93-103">Sets the severity level of the specified log switch.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27e93-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="27e93-104">Syntax</span></span>  
  
```cpp  
HRESULT ModifyLogSwitch(  
    [in] WCHAR *pLogSwitchName,  
    [in] LONG  lLevel);  
```  
  
## <a name="parameters"></a><span data-ttu-id="27e93-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="27e93-105">Parameters</span></span>  

 `pLogSwitchName`  
 <span data-ttu-id="27e93-106">de Puntero a una cadena que especifica el nombre del modificador de registro.</span><span class="sxs-lookup"><span data-stu-id="27e93-106">[in] A pointer to a string that specifies the name of the log switch.</span></span>  
  
 `lLevel`  
 <span data-ttu-id="27e93-107">de Nivel de gravedad que se va a establecer para el modificador de registro especificado.</span><span class="sxs-lookup"><span data-stu-id="27e93-107">[in] The severity level to be set for the specified log switch.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="27e93-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="27e93-108">Remarks</span></span>  

 <span data-ttu-id="27e93-109">Este método es válido solo después de que se haya producido la devolución de llamada [ICorDebugManagedCallback:: CreateProcess](icordebugmanagedcallback-createprocess-method.md) .</span><span class="sxs-lookup"><span data-stu-id="27e93-109">This method is valid only after the [ICorDebugManagedCallback::CreateProcess](icordebugmanagedcallback-createprocess-method.md) callback has occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27e93-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="27e93-110">Requirements</span></span>  

 <span data-ttu-id="27e93-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="27e93-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27e93-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="27e93-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="27e93-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="27e93-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="27e93-114">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27e93-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
