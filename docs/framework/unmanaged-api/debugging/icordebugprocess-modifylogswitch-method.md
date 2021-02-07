---
description: 'Más información acerca de: ICorDebugProcess:: Modifylogswitch ((método)'
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
ms.openlocfilehash: 3c825d6c6b075139793b54526dca696c8fba35a4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99746781"
---
# <a name="icordebugprocessmodifylogswitch-method"></a><span data-ttu-id="54427-103">ICorDebugProcess::ModifyLogSwitch (Método)</span><span class="sxs-lookup"><span data-stu-id="54427-103">ICorDebugProcess::ModifyLogSwitch Method</span></span>

<span data-ttu-id="54427-104">Establece el nivel de gravedad del modificador de registro especificado.</span><span class="sxs-lookup"><span data-stu-id="54427-104">Sets the severity level of the specified log switch.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54427-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="54427-105">Syntax</span></span>  
  
```cpp  
HRESULT ModifyLogSwitch(  
    [in] WCHAR *pLogSwitchName,  
    [in] LONG  lLevel);  
```  
  
## <a name="parameters"></a><span data-ttu-id="54427-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="54427-106">Parameters</span></span>  

 `pLogSwitchName`  
 <span data-ttu-id="54427-107">de Puntero a una cadena que especifica el nombre del modificador de registro.</span><span class="sxs-lookup"><span data-stu-id="54427-107">[in] A pointer to a string that specifies the name of the log switch.</span></span>  
  
 `lLevel`  
 <span data-ttu-id="54427-108">de Nivel de gravedad que se va a establecer para el modificador de registro especificado.</span><span class="sxs-lookup"><span data-stu-id="54427-108">[in] The severity level to be set for the specified log switch.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="54427-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="54427-109">Remarks</span></span>  

 <span data-ttu-id="54427-110">Este método es válido solo después de que se haya producido la devolución de llamada [ICorDebugManagedCallback:: CreateProcess](icordebugmanagedcallback-createprocess-method.md) .</span><span class="sxs-lookup"><span data-stu-id="54427-110">This method is valid only after the [ICorDebugManagedCallback::CreateProcess](icordebugmanagedcallback-createprocess-method.md) callback has occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="54427-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="54427-111">Requirements</span></span>  

 <span data-ttu-id="54427-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="54427-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="54427-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="54427-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="54427-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="54427-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="54427-115">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="54427-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
