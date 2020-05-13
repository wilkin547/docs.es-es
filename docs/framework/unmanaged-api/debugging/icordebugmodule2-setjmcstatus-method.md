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
ms.openlocfilehash: d5109043a8601d7997f52e88ea472644f1b9ca03
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83208790"
---
# <a name="icordebugmodule2setjmcstatus-method"></a><span data-ttu-id="551f1-102">ICorDebugModule2::SetJMCStatus (Método)</span><span class="sxs-lookup"><span data-stu-id="551f1-102">ICorDebugModule2::SetJMCStatus Method</span></span>
<span data-ttu-id="551f1-103">Establece el Estado Solo mi código (JMC) de todos los métodos de todas las clases de este ICorDebugModule2 en el valor especificado, excepto los de la `pTokens` matriz, que se establece en el valor opuesto.</span><span class="sxs-lookup"><span data-stu-id="551f1-103">Sets the Just My Code (JMC) status of all methods of all the classes in this ICorDebugModule2 to the specified value, except those in the `pTokens` array, which it sets to the opposite value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="551f1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="551f1-104">Syntax</span></span>  
  
```cpp  
HRESULT SetJMCStatus (  
    [in] BOOL                        bIsJustMyCode,  
    [in] ULONG32                     cTokens,  
    [in, size_is(cTokens)] mdToken   pTokens[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="551f1-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="551f1-105">Parameters</span></span>  
 `bIsJustMycode`  
 <span data-ttu-id="551f1-106">de Se establece en `true` si se va a depurar el código; de lo contrario, se establece en `false` .</span><span class="sxs-lookup"><span data-stu-id="551f1-106">[in] Set to `true` if the code is to be debugged; otherwise, set to `false`.</span></span>  
  
 `cTokens`  
 <span data-ttu-id="551f1-107">[in] Tamaño de la matriz `pTokens`.</span><span class="sxs-lookup"><span data-stu-id="551f1-107">[in] The size of the `pTokens` array.</span></span>  
  
 `pTokens`  
 <span data-ttu-id="551f1-108">de Una matriz de `mdToken` valores, cada uno de los cuales hace referencia a un método que tendrá su estado JMC establecido en! `bIsJustMycode` .</span><span class="sxs-lookup"><span data-stu-id="551f1-108">[in] An array of `mdToken` values, each of which refers to a method that will have its JMC status set to !`bIsJustMycode`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="551f1-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="551f1-109">Remarks</span></span>  
 <span data-ttu-id="551f1-110">El estado de JMC de cada método que se especifica en la `pTokens` matriz se establece en el opuesto del `bIsJustMycode` valor.</span><span class="sxs-lookup"><span data-stu-id="551f1-110">The JMC status of each method that is specified in the `pTokens` array is set to the opposite of the `bIsJustMycode` value.</span></span> <span data-ttu-id="551f1-111">El estado de todos los demás métodos de este módulo se establece en el `bIsJustMycode` valor.</span><span class="sxs-lookup"><span data-stu-id="551f1-111">The status of all other methods in this module is set to the `bIsJustMycode` value.</span></span>  
  
 <span data-ttu-id="551f1-112">El `SetJMCStatus` método borra todas las configuraciones de JMC anteriores de este módulo.</span><span class="sxs-lookup"><span data-stu-id="551f1-112">The `SetJMCStatus` method erases all previous JMC settings in this module.</span></span>  
  
 <span data-ttu-id="551f1-113">El `SetJMCStatus` método devuelve un S_OK HRESULT si todas las funciones se establecieron correctamente.</span><span class="sxs-lookup"><span data-stu-id="551f1-113">The `SetJMCStatus` method returns an S_OK HRESULT if all functions were set successfully.</span></span> <span data-ttu-id="551f1-114">Devuelve un CORDBG_E_FUNCTION_NOT_DEBUGGABLE HRESULT si algunas funciones marcadas `true` no se pueden depurar.</span><span class="sxs-lookup"><span data-stu-id="551f1-114">It returns a CORDBG_E_FUNCTION_NOT_DEBUGGABLE HRESULT if some functions that are marked `true` are not debuggable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="551f1-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="551f1-115">Requirements</span></span>  
 <span data-ttu-id="551f1-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="551f1-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="551f1-117">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="551f1-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="551f1-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="551f1-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="551f1-119">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="551f1-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
