---
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a56b5c31c26dbe5c5371fdb7a10c13ad11847117
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33419477"
---
# <a name="icordebugmodule2setjmcstatus-method"></a><span data-ttu-id="42861-102">ICorDebugModule2::SetJMCStatus (Método)</span><span class="sxs-lookup"><span data-stu-id="42861-102">ICorDebugModule2::SetJMCStatus Method</span></span>
<span data-ttu-id="42861-103">Establece el estado de "sólo mi código" (JMC) de todos los métodos de todas las clases en este ICorDebugModule2 en el valor especificado, excepto los de la `pTokens` matriz, que establece en el valor opuesto.</span><span class="sxs-lookup"><span data-stu-id="42861-103">Sets the Just My Code (JMC) status of all methods of all the classes in this ICorDebugModule2 to the specified value, except those in the `pTokens` array, which it sets to the opposite value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42861-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="42861-104">Syntax</span></span>  
  
```  
HRESULT SetJMCStatus (  
    [in] BOOL                        bIsJustMyCode,  
    [in] ULONG32                     cTokens,  
    [in, size_is(cTokens)] mdToken   pTokens[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="42861-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="42861-105">Parameters</span></span>  
 `bIsJustMycode`  
 <span data-ttu-id="42861-106">[in] Establecido en `true` si el código depurado; en caso contrario, se establece en `false`.</span><span class="sxs-lookup"><span data-stu-id="42861-106">[in] Set to `true` if the code is to be debugged; otherwise, set to `false`.</span></span>  
  
 `cTokens`  
 <span data-ttu-id="42861-107">[in] Tamaño de la matriz `pTokens`.</span><span class="sxs-lookup"><span data-stu-id="42861-107">[in] The size of the `pTokens` array.</span></span>  
  
 `pTokens`  
 <span data-ttu-id="42861-108">[in] Una matriz de `mdToken` valores, cada uno de los cuales se refiere a un método que tendrá su estado JMC establecido en!`bIsJustMycode`.</span><span class="sxs-lookup"><span data-stu-id="42861-108">[in] An array of `mdToken` values, each of which refers to a method that will have its JMC status set to !`bIsJustMycode`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="42861-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="42861-109">Remarks</span></span>  
 <span data-ttu-id="42861-110">El estado JMC de cada método que se especifica en el `pTokens` matriz se establece con el valor opuesto de la `bIsJustMycode` valor.</span><span class="sxs-lookup"><span data-stu-id="42861-110">The JMC status of each method that is specified in the `pTokens` array is set to the opposite of the `bIsJustMycode` value.</span></span> <span data-ttu-id="42861-111">El estado de todos los demás métodos de este módulo se establece en el `bIsJustMycode` valor.</span><span class="sxs-lookup"><span data-stu-id="42861-111">The status of all other methods in this module is set to the `bIsJustMycode` value.</span></span>  
  
 <span data-ttu-id="42861-112">El `SetJMCStatus` método borra toda la configuración JMC anterior de este módulo.</span><span class="sxs-lookup"><span data-stu-id="42861-112">The `SetJMCStatus` method erases all previous JMC settings in this module.</span></span>  
  
 <span data-ttu-id="42861-113">El `SetJMCStatus` método devuelve un HRESULT de S_OK si todas las funciones se establecieron correctamente.</span><span class="sxs-lookup"><span data-stu-id="42861-113">The `SetJMCStatus` method returns an S_OK HRESULT if all functions were set successfully.</span></span> <span data-ttu-id="42861-114">Devuelve un HRESULT de CORDBG_E_FUNCTION_NOT_DEBUGGABLE si algunas funciones que se marcan `true` no son depurable.</span><span class="sxs-lookup"><span data-stu-id="42861-114">It returns a CORDBG_E_FUNCTION_NOT_DEBUGGABLE HRESULT if some functions that are marked `true` are not debuggable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42861-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="42861-115">Requirements</span></span>  
 <span data-ttu-id="42861-116">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="42861-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42861-117">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="42861-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="42861-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="42861-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="42861-119">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42861-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
