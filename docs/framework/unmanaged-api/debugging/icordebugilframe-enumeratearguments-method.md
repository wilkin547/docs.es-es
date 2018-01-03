---
title: "ICorDebugILFrame::EnumerateArguments (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugILFrame.EnumerateArguments
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugILFrame::EnumerateArguments
helpviewer_keywords:
- ICorDebugILFrame::EnumerateArguments method [.NET Framework debugging]
- EnumerateArguments method [.NET Framework debugging]
ms.assetid: 00ac81e2-a774-422a-bd88-54a4b3c99f73
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 474118abc505928d16737d792a619e75f1209344
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugilframeenumeratearguments-method"></a><span data-ttu-id="7d646-102">ICorDebugILFrame::EnumerateArguments (Método)</span><span class="sxs-lookup"><span data-stu-id="7d646-102">ICorDebugILFrame::EnumerateArguments Method</span></span>
<span data-ttu-id="7d646-103">Obtiene un enumerador para los argumentos de este marco.</span><span class="sxs-lookup"><span data-stu-id="7d646-103">Gets an enumerator for the arguments in this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d646-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7d646-104">Syntax</span></span>  
  
```  
HRESULT EnumerateArguments (  
    [out] ICorDebugValueEnum    **ppValueEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7d646-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7d646-105">Parameters</span></span>  
 `ppValueEnum`  
 <span data-ttu-id="7d646-106">[out] Un puntero a la dirección de un objeto ICorDebugValueEnum que es el enumerador para los argumentos de este marco.</span><span class="sxs-lookup"><span data-stu-id="7d646-106">[out] A pointer to the address of an ICorDebugValueEnum object that is the enumerator for the arguments in this frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7d646-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7d646-107">Remarks</span></span>  
 <span data-ttu-id="7d646-108">`EnumerateArguments`Obtiene un enumerador que puede enumerar los argumentos disponibles en el marco de llamadas representado por este objeto ICorDebugILFrame.</span><span class="sxs-lookup"><span data-stu-id="7d646-108">`EnumerateArguments` gets an enumerator that can list the arguments available in the call frame that is represented by this ICorDebugILFrame object.</span></span> <span data-ttu-id="7d646-109">La lista incluirá los argumentos que son [vararg](/cpp/windows/vararg) (es decir, un número variable de argumentos), así como de los argumentos que no son `vararg`.</span><span class="sxs-lookup"><span data-stu-id="7d646-109">The list will include arguments that are [vararg](/cpp/windows/vararg) (that is, a variable number of arguments) as well as arguments that are not `vararg`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d646-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7d646-110">Requirements</span></span>  
 <span data-ttu-id="7d646-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7d646-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d646-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7d646-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7d646-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7d646-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7d646-114">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d646-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
