---
title: ICorDebugChain::EnumerateFrames (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugChain.EnumerateFrames
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::EnumerateFrames method
helpviewer_keywords:
- EnumerateFrames method [.NET Framework debugging]
- ICorDebugChain::EnumerateFrames method [.NET Framework debugging]
ms.assetid: 9fcefa98-750d-4168-8915-8173a43accf2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d408f317b546fb7e8314e904e6f5ad9e6296ae6d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33403271"
---
# <a name="icordebugchainenumerateframes-method"></a><span data-ttu-id="0ad5f-102">ICorDebugChain::EnumerateFrames (Método)</span><span class="sxs-lookup"><span data-stu-id="0ad5f-102">ICorDebugChain::EnumerateFrames Method</span></span>
<span data-ttu-id="0ad5f-103">Obtiene un enumerador que contiene todos los marcos de pila administrados de la cadena, comenzando por el marco más reciente.</span><span class="sxs-lookup"><span data-stu-id="0ad5f-103">Gets an enumerator that contains all the managed stack frames in the chain, starting with the most recent frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ad5f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0ad5f-104">Syntax</span></span>  
  
```  
HRESULT EnumerateFrames (  
    [out] ICorDebugFrameEnum **ppFrames  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0ad5f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0ad5f-105">Parameters</span></span>  
 `ppFrames`  
 <span data-ttu-id="0ad5f-106">[out] Un puntero a la dirección de un objeto ICorDebugFrameEnum que es el enumerador de los marcos de pila.</span><span class="sxs-lookup"><span data-stu-id="0ad5f-106">[out] A pointer to the address of an ICorDebugFrameEnum object that is the enumerator for the stack frames.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0ad5f-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0ad5f-107">Remarks</span></span>  
 <span data-ttu-id="0ad5f-108">La cadena representa la pila de llamadas física del subproceso.</span><span class="sxs-lookup"><span data-stu-id="0ad5f-108">The chain represents the physical call stack for the thread.</span></span>  
  
 <span data-ttu-id="0ad5f-109">El `EnumerateFrames` método debe llamarse solo para cadenas administrados.</span><span class="sxs-lookup"><span data-stu-id="0ad5f-109">The `EnumerateFrames` method should be called only for managed chains.</span></span> <span data-ttu-id="0ad5f-110">La API de depuración no proporciona métodos para obtener los marcos incluidos en cadenas no administradas.</span><span class="sxs-lookup"><span data-stu-id="0ad5f-110">The debugging API does not provide methods for obtaining frames contained in unmanaged chains.</span></span> <span data-ttu-id="0ad5f-111">El depurador debe utilizar otros medios para obtener esta información.</span><span class="sxs-lookup"><span data-stu-id="0ad5f-111">The debugger must use other means to obtain this information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ad5f-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0ad5f-112">Requirements</span></span>  
 <span data-ttu-id="0ad5f-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0ad5f-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ad5f-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0ad5f-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0ad5f-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0ad5f-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0ad5f-116">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ad5f-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
