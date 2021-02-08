---
description: 'Más información acerca de: ICorDebugILFrame:: EnumerateArguments ((método)'
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
ms.openlocfilehash: 513f931e70a4e914b89f440545cf33ea1cce1fdf
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791405"
---
# <a name="icordebugilframeenumeratearguments-method"></a><span data-ttu-id="1a173-103">ICorDebugILFrame::EnumerateArguments (Método)</span><span class="sxs-lookup"><span data-stu-id="1a173-103">ICorDebugILFrame::EnumerateArguments Method</span></span>

<span data-ttu-id="1a173-104">Obtiene un enumerador para los argumentos de este marco.</span><span class="sxs-lookup"><span data-stu-id="1a173-104">Gets an enumerator for the arguments in this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a173-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1a173-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateArguments (  
    [out] ICorDebugValueEnum    **ppValueEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1a173-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1a173-106">Parameters</span></span>  

 `ppValueEnum`  
 <span data-ttu-id="1a173-107">enuncia Puntero a la dirección de un objeto ICorDebugValueEnum que es el enumerador de los argumentos de este marco.</span><span class="sxs-lookup"><span data-stu-id="1a173-107">[out] A pointer to the address of an ICorDebugValueEnum object that is the enumerator for the arguments in this frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1a173-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1a173-108">Remarks</span></span>  

 <span data-ttu-id="1a173-109">`EnumerateArguments` Obtiene un enumerador que puede enumerar los argumentos disponibles en el marco de llamada representado por este objeto ICorDebugILFrame.</span><span class="sxs-lookup"><span data-stu-id="1a173-109">`EnumerateArguments` gets an enumerator that can list the arguments available in the call frame that is represented by this ICorDebugILFrame object.</span></span> <span data-ttu-id="1a173-110">La lista incluirá argumentos que son [vararg](/cpp/windows/vararg) (es decir, un número variable de argumentos), así como argumentos que no son `vararg` .</span><span class="sxs-lookup"><span data-stu-id="1a173-110">The list will include arguments that are [vararg](/cpp/windows/vararg) (that is, a variable number of arguments) as well as arguments that are not `vararg`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1a173-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1a173-111">Requirements</span></span>  

 <span data-ttu-id="1a173-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1a173-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1a173-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1a173-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1a173-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1a173-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1a173-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1a173-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
