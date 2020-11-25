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
ms.openlocfilehash: 9b0bc59b67b5d4b2184733f22616433bf33be616
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703231"
---
# <a name="icordebugilframeenumeratearguments-method"></a><span data-ttu-id="c332a-102">ICorDebugILFrame::EnumerateArguments (Método)</span><span class="sxs-lookup"><span data-stu-id="c332a-102">ICorDebugILFrame::EnumerateArguments Method</span></span>

<span data-ttu-id="c332a-103">Obtiene un enumerador para los argumentos de este marco.</span><span class="sxs-lookup"><span data-stu-id="c332a-103">Gets an enumerator for the arguments in this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c332a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c332a-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateArguments (  
    [out] ICorDebugValueEnum    **ppValueEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c332a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c332a-105">Parameters</span></span>  

 `ppValueEnum`  
 <span data-ttu-id="c332a-106">enuncia Puntero a la dirección de un objeto ICorDebugValueEnum que es el enumerador de los argumentos de este marco.</span><span class="sxs-lookup"><span data-stu-id="c332a-106">[out] A pointer to the address of an ICorDebugValueEnum object that is the enumerator for the arguments in this frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c332a-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c332a-107">Remarks</span></span>  

 <span data-ttu-id="c332a-108">`EnumerateArguments` Obtiene un enumerador que puede enumerar los argumentos disponibles en el marco de llamada representado por este objeto ICorDebugILFrame.</span><span class="sxs-lookup"><span data-stu-id="c332a-108">`EnumerateArguments` gets an enumerator that can list the arguments available in the call frame that is represented by this ICorDebugILFrame object.</span></span> <span data-ttu-id="c332a-109">La lista incluirá argumentos que son [vararg](/cpp/windows/vararg) (es decir, un número variable de argumentos), así como argumentos que no son `vararg` .</span><span class="sxs-lookup"><span data-stu-id="c332a-109">The list will include arguments that are [vararg](/cpp/windows/vararg) (that is, a variable number of arguments) as well as arguments that are not `vararg`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c332a-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c332a-110">Requirements</span></span>  

 <span data-ttu-id="c332a-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c332a-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c332a-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c332a-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c332a-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c332a-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c332a-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c332a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
