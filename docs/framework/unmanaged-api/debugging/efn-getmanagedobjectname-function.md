---
title: _EFN_GetManagedObjectName (Función)
ms.date: 03/30/2017
api_name:
- _EFN_GetManagedObjectName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- _EFN_GetManagedObjectName
helpviewer_keywords:
- _EFN_GetManagedObjectName function [.NET Framework debugging]
ms.assetid: 6e7c6bee-7ced-495f-bf6c-2a5f0c716f7e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c4eddb1461ad448a1a1718db8a11173e5e2e4a17
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54527788"
---
# <a name="efngetmanagedobjectname-function"></a><span data-ttu-id="8b216-102">_EFN_GetManagedObjectName (Función)</span><span class="sxs-lookup"><span data-stu-id="8b216-102">_EFN_GetManagedObjectName Function</span></span>
<span data-ttu-id="8b216-103">Obtiene el nombre de un tipo mediante el puntero de objeto administrado proporcionado.</span><span class="sxs-lookup"><span data-stu-id="8b216-103">Gets the name of a type using the provided managed object pointer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b216-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8b216-104">Syntax</span></span>  
  
```  
HRESULT _EFN_GetManagedObjectName(  
    [in]  PDEBUG_CLIENT  Client,  
    [in]  ULONG64        objAddr,  
    [out] __out_ecount(cbName) PSTR szName,  
    [out] ULONG          cbName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8b216-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8b216-105">Parameters</span></span>  
 `Client`  
 <span data-ttu-id="8b216-106">[in] Un puntero al cliente de depuración.</span><span class="sxs-lookup"><span data-stu-id="8b216-106">[in] A pointer to the debug client.</span></span>  
  
 `objAddr`  
 <span data-ttu-id="8b216-107">[in] Un puntero de objeto administrado.</span><span class="sxs-lookup"><span data-stu-id="8b216-107">[in] A managed object pointer.</span></span>  
  
 <span data-ttu-id="8b216-108">szName</span><span class="sxs-lookup"><span data-stu-id="8b216-108">szName</span></span>  
 <span data-ttu-id="8b216-109">[out] El nombre del tipo.</span><span class="sxs-lookup"><span data-stu-id="8b216-109">[out] The name of the type.</span></span>  
  
 `cbName`  
 <span data-ttu-id="8b216-110">[out] El número de caracteres disponibles en el búfer de cadena.</span><span class="sxs-lookup"><span data-stu-id="8b216-110">[out] The number of characters available in the string buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8b216-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8b216-111">Remarks</span></span>  
 <span data-ttu-id="8b216-112">Si no hay ningún código administrado en el subproceso actualmente en contexto, la función devuelve HRESULT SOS_E_NOMANAGEDCODE con un valor 0xa0 y un código de error de 0 x 1000.</span><span class="sxs-lookup"><span data-stu-id="8b216-112">If there is no managed code on the thread currently in context, the function returns HRESULT SOS_E_NOMANAGEDCODE with a facility value of 0xa0 and an error code of 0x1000.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8b216-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8b216-113">Requirements</span></span>  
 <span data-ttu-id="8b216-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8b216-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b216-115">**Encabezado**: SOS_Stacktrace.h</span><span class="sxs-lookup"><span data-stu-id="8b216-115">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="8b216-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8b216-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b216-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="8b216-117">See also</span></span>
- [<span data-ttu-id="8b216-118">Funciones estáticas globales de depuración</span><span class="sxs-lookup"><span data-stu-id="8b216-118">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
