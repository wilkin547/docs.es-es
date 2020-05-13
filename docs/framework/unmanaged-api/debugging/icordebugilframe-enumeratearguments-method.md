---
title: ICorDebugILFrame::EnumerateArguments (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.EnumerateArguments
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::EnumerateArguments
helpviewer_keywords:
- ICorDebugILFrame::EnumerateArguments method [.NET Framework debugging]
- EnumerateArguments method [.NET Framework debugging]
ms.assetid: 00ac81e2-a774-422a-bd88-54a4b3c99f73
topic_type:
- apiref
ms.openlocfilehash: 3945b1dea62dc0616d669356faf60f0d09cfb084
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210311"
---
# <a name="icordebugilframeenumeratearguments-method"></a><span data-ttu-id="e3d59-102">ICorDebugILFrame::EnumerateArguments (Método)</span><span class="sxs-lookup"><span data-stu-id="e3d59-102">ICorDebugILFrame::EnumerateArguments Method</span></span>
<span data-ttu-id="e3d59-103">Obtiene un enumerador para los argumentos de este marco.</span><span class="sxs-lookup"><span data-stu-id="e3d59-103">Gets an enumerator for the arguments in this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3d59-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e3d59-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateArguments (  
    [out] ICorDebugValueEnum    **ppValueEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e3d59-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e3d59-105">Parameters</span></span>  
 `ppValueEnum`  
 <span data-ttu-id="e3d59-106">enuncia Puntero a la dirección de un objeto ICorDebugValueEnum que es el enumerador de los argumentos de este marco.</span><span class="sxs-lookup"><span data-stu-id="e3d59-106">[out] A pointer to the address of an ICorDebugValueEnum object that is the enumerator for the arguments in this frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e3d59-107">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e3d59-107">Remarks</span></span>  
 <span data-ttu-id="e3d59-108">`EnumerateArguments`Obtiene un enumerador que puede enumerar los argumentos disponibles en el marco de llamada representado por este objeto ICorDebugILFrame.</span><span class="sxs-lookup"><span data-stu-id="e3d59-108">`EnumerateArguments` gets an enumerator that can list the arguments available in the call frame that is represented by this ICorDebugILFrame object.</span></span> <span data-ttu-id="e3d59-109">La lista incluirá argumentos que son [vararg](/cpp/windows/vararg) (es decir, un número variable de argumentos), así como argumentos que no son `vararg` .</span><span class="sxs-lookup"><span data-stu-id="e3d59-109">The list will include arguments that are [vararg](/cpp/windows/vararg) (that is, a variable number of arguments) as well as arguments that are not `vararg`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e3d59-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e3d59-110">Requirements</span></span>  
 <span data-ttu-id="e3d59-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e3d59-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e3d59-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e3d59-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e3d59-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e3d59-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e3d59-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e3d59-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
