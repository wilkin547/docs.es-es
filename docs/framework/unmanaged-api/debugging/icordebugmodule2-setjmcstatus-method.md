---
description: 'Más información sobre: ICorDebugModule2:: Setjmcstatus ((método)'
title: ICorDebugModule2::SetJMCStatus (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugModule2.SetJMCStatus
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule2::SetJMCStatus
helpviewer_keywords:
- SetJMCStatus method, ICorDebugModule2 interface [.NET Framework debugging]
- ICorDebugModule2::SetJMCStatus method [.NET Framework debugging]
ms.assetid: 8c6d2089-4dbb-4715-b9e9-2a4491c8c9ce
topic_type:
- apiref
ms.openlocfilehash: 7d91d098c21eac39d18a0aa7c3d4fd795be509ae
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790807"
---
# <a name="icordebugmodule2setjmcstatus-method"></a><span data-ttu-id="d6ac1-103">ICorDebugModule2::SetJMCStatus (Método)</span><span class="sxs-lookup"><span data-stu-id="d6ac1-103">ICorDebugModule2::SetJMCStatus Method</span></span>

<span data-ttu-id="d6ac1-104">Establece el Estado Solo mi código (JMC) de todos los métodos de todas las clases de este ICorDebugModule2 en el valor especificado, excepto los de la `pTokens` matriz, que se establece en el valor opuesto.</span><span class="sxs-lookup"><span data-stu-id="d6ac1-104">Sets the Just My Code (JMC) status of all methods of all the classes in this ICorDebugModule2 to the specified value, except those in the `pTokens` array, which it sets to the opposite value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6ac1-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d6ac1-105">Syntax</span></span>  
  
```cpp  
HRESULT SetJMCStatus (  
    [in] BOOL                        bIsJustMyCode,  
    [in] ULONG32                     cTokens,  
    [in, size_is(cTokens)] mdToken   pTokens[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d6ac1-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d6ac1-106">Parameters</span></span>  

 `bIsJustMycode`  
 <span data-ttu-id="d6ac1-107">de Se establece en `true` si se va a depurar el código; de lo contrario, se establece en `false` .</span><span class="sxs-lookup"><span data-stu-id="d6ac1-107">[in] Set to `true` if the code is to be debugged; otherwise, set to `false`.</span></span>  
  
 `cTokens`  
 <span data-ttu-id="d6ac1-108">[in] Tamaño de la matriz `pTokens`.</span><span class="sxs-lookup"><span data-stu-id="d6ac1-108">[in] The size of the `pTokens` array.</span></span>  
  
 `pTokens`  
 <span data-ttu-id="d6ac1-109">de Una matriz de `mdToken` valores, cada uno de los cuales hace referencia a un método que tendrá su estado JMC establecido en! `bIsJustMycode` .</span><span class="sxs-lookup"><span data-stu-id="d6ac1-109">[in] An array of `mdToken` values, each of which refers to a method that will have its JMC status set to !`bIsJustMycode`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d6ac1-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d6ac1-110">Remarks</span></span>  

 <span data-ttu-id="d6ac1-111">El estado de JMC de cada método que se especifica en la `pTokens` matriz se establece en el opuesto del `bIsJustMycode` valor.</span><span class="sxs-lookup"><span data-stu-id="d6ac1-111">The JMC status of each method that is specified in the `pTokens` array is set to the opposite of the `bIsJustMycode` value.</span></span> <span data-ttu-id="d6ac1-112">El estado de todos los demás métodos de este módulo se establece en el `bIsJustMycode` valor.</span><span class="sxs-lookup"><span data-stu-id="d6ac1-112">The status of all other methods in this module is set to the `bIsJustMycode` value.</span></span>  
  
 <span data-ttu-id="d6ac1-113">El `SetJMCStatus` método borra todas las configuraciones de JMC anteriores de este módulo.</span><span class="sxs-lookup"><span data-stu-id="d6ac1-113">The `SetJMCStatus` method erases all previous JMC settings in this module.</span></span>  
  
 <span data-ttu-id="d6ac1-114">El `SetJMCStatus` método devuelve un S_OK HRESULT si todas las funciones se establecieron correctamente.</span><span class="sxs-lookup"><span data-stu-id="d6ac1-114">The `SetJMCStatus` method returns an S_OK HRESULT if all functions were set successfully.</span></span> <span data-ttu-id="d6ac1-115">Devuelve un CORDBG_E_FUNCTION_NOT_DEBUGGABLE HRESULT si algunas funciones marcadas `true` no se pueden depurar.</span><span class="sxs-lookup"><span data-stu-id="d6ac1-115">It returns a CORDBG_E_FUNCTION_NOT_DEBUGGABLE HRESULT if some functions that are marked `true` are not debuggable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d6ac1-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d6ac1-116">Requirements</span></span>  

 <span data-ttu-id="d6ac1-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d6ac1-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d6ac1-118">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d6ac1-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d6ac1-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d6ac1-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d6ac1-120">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d6ac1-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
