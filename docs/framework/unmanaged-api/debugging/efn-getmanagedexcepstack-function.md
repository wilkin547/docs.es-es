---
title: _EFN_GetManagedExcepStack (Función)
ms.date: 03/30/2017
api_name:
- _EFN_GetManagedExcepStack
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- _EFN_GetManagedExcepStack
helpviewer_keywords:
- _EFN_GetManagedExcepStack function [.NET Framework debugging]
ms.assetid: 21ceed9e-62b2-4024-b027-6d095109955a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7e86a1d2dfeb0d36b369d3b6cd7ea985591b5959
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57488418"
---
# <a name="efngetmanagedexcepstack-function"></a><span data-ttu-id="9395a-102">_EFN_GetManagedExcepStack (Función)</span><span class="sxs-lookup"><span data-stu-id="9395a-102">_EFN_GetManagedExcepStack Function</span></span>
<span data-ttu-id="9395a-103">Dada una dirección de objeto de excepción administrado, devuelve una versión de cadena del seguimiento de pila que contiene.</span><span class="sxs-lookup"><span data-stu-id="9395a-103">Given a managed exception object address, returns a string version of the stack trace contained inside.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9395a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9395a-104">Syntax</span></span>  
  
```  
HRESULT _EFN_GetManagedExcepStack(  
    [in]  PDEBUG_CLIENT Client,  
    [in]  ULONG64       StackObjAddr,  
    [out] __out_ecount(cbString) PSTR szStackString,  
    [out] ULONG         cbString  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9395a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9395a-105">Parameters</span></span>  
 `Client`  
 <span data-ttu-id="9395a-106">[in] El cliente que se está depurando.</span><span class="sxs-lookup"><span data-stu-id="9395a-106">[in] The client being debugged.</span></span>  
  
 `StackObjAddr`  
 <span data-ttu-id="9395a-107">[in] Un puntero de objeto administrado, derivado de <xref:System.Exception>.</span><span class="sxs-lookup"><span data-stu-id="9395a-107">[in] A managed object pointer, derived from <xref:System.Exception>.</span></span>  
  
 <span data-ttu-id="9395a-108">szStackString</span><span class="sxs-lookup"><span data-stu-id="9395a-108">szStackString</span></span>  
 <span data-ttu-id="9395a-109">[out] La cadena devuelta.</span><span class="sxs-lookup"><span data-stu-id="9395a-109">[out] The returned string.</span></span>  
  
 `cbString`  
 <span data-ttu-id="9395a-110">[out] El número de caracteres disponibles en el búfer de cadena.</span><span class="sxs-lookup"><span data-stu-id="9395a-110">[out] The number of characters available in the string buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9395a-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9395a-111">Remarks</span></span>  
 <span data-ttu-id="9395a-112">Si no hay ningún código administrado en el subproceso actualmente en contexto, la función devuelve HRESULT SOS_E_NOMANAGEDCODE con un valor 0xa0 y un código de error de 0 x 1000.</span><span class="sxs-lookup"><span data-stu-id="9395a-112">If there is no managed code on the thread currently in context, the function returns HRESULT SOS_E_NOMANAGEDCODE with a facility value of 0xa0 and an error code of 0x1000.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9395a-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9395a-113">Requirements</span></span>  
 <span data-ttu-id="9395a-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9395a-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9395a-115">**Encabezado**: SOS_Stacktrace.h</span><span class="sxs-lookup"><span data-stu-id="9395a-115">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="9395a-116">**Versión de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9395a-116">**.NET Framework Version:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9395a-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="9395a-117">See also</span></span>
- [<span data-ttu-id="9395a-118">Funciones estáticas globales de depuración</span><span class="sxs-lookup"><span data-stu-id="9395a-118">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
