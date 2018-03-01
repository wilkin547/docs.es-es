---
title: "_EFN_GetManagedObjectFieldInfo (Función)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- _EFN_GetManagedObjectFieldInfo
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- _EFN_GetManagedObjectFieldInfo
helpviewer_keywords:
- _EFN_GetManagedObjectFieldInfo function [.NET Framework debugging]
ms.assetid: 3b93bcff-62a4-47b2-babc-6bcf4216119a
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4822cab8816e97bd1d13c36ea7b63dc9a6f679d0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="efngetmanagedobjectfieldinfo-function"></a><span data-ttu-id="f8a54-102">_EFN_GetManagedObjectFieldInfo (Función)</span><span class="sxs-lookup"><span data-stu-id="f8a54-102">_EFN_GetManagedObjectFieldInfo Function</span></span>
<span data-ttu-id="f8a54-103">Obtiene el desplazamiento desde el inicio de un objeto hasta un campo y el valor del campo, a partir del puntero de objeto y nombre de campo especificados.</span><span class="sxs-lookup"><span data-stu-id="f8a54-103">Gets the offset from the start of an object to a field and the field's value, using the provided object pointer and field name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8a54-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f8a54-104">Syntax</span></span>  
  
```  
HRESULT _EFN_GetManagedObjectFieldInfo(  
    [in]  PDEBUG_CLIENT Client,  
    [in]  ULONG64       objAddr,  
    [in]  __out_ecount (mdNameLen) PSTR szFieldName,  
    [out] PULONG64      pValue,  
    [out] PULONG        pOffset  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f8a54-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f8a54-105">Parameters</span></span>  
 `Client`  
 <span data-ttu-id="f8a54-106">[in] Un puntero al cliente de depuración.</span><span class="sxs-lookup"><span data-stu-id="f8a54-106">[in] A pointer to the debug client.</span></span>  
  
 `objAddr`  
 <span data-ttu-id="f8a54-107">[in] Un puntero de objeto administrado.</span><span class="sxs-lookup"><span data-stu-id="f8a54-107">[in] A managed object pointer.</span></span>  
  
 <span data-ttu-id="f8a54-108">szFieldName</span><span class="sxs-lookup"><span data-stu-id="f8a54-108">szFieldName</span></span>  
 <span data-ttu-id="f8a54-109">[in] Un puntero de objeto administrado por el nombre de campo.</span><span class="sxs-lookup"><span data-stu-id="f8a54-109">[in] A managed object pointer to the field name.</span></span>  
  
 `pValue`  
 <span data-ttu-id="f8a54-110">[out] El valor del campo.</span><span class="sxs-lookup"><span data-stu-id="f8a54-110">[out] The field value.</span></span> <span data-ttu-id="f8a54-111">Este parámetro puede ser NULL.</span><span class="sxs-lookup"><span data-stu-id="f8a54-111">This parameter can be null.</span></span>  
  
 `pOffset`  
 <span data-ttu-id="f8a54-112">[out] El desplazamiento de `objAddr` al campo.</span><span class="sxs-lookup"><span data-stu-id="f8a54-112">[out] The offset from `objAddr` to the field.</span></span> <span data-ttu-id="f8a54-113">Este parámetro puede ser NULL.</span><span class="sxs-lookup"><span data-stu-id="f8a54-113">This parameter can be null.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f8a54-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f8a54-114">Remarks</span></span>  
 <span data-ttu-id="f8a54-115">Si el desplazamiento es 0, no se escribe ningún desplazamiento.</span><span class="sxs-lookup"><span data-stu-id="f8a54-115">If the offset is 0, no offset is written.</span></span>  
  
 <span data-ttu-id="f8a54-116">Si no hay código administrado en el subproceso actualmente en contexto, la función devuelve HRESULT SOS_E_NOMANAGEDCODE con un valor 0xa0 y el código de error de 0 x 1000.</span><span class="sxs-lookup"><span data-stu-id="f8a54-116">If there is no managed code on the thread currently in context, the function returns HRESULT SOS_E_NOMANAGEDCODE with a facility value of 0xa0 and an error code of 0x1000.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8a54-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f8a54-117">Requirements</span></span>  
 <span data-ttu-id="f8a54-118">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f8a54-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8a54-119">**Encabezado:** SOS_Stacktrace.h</span><span class="sxs-lookup"><span data-stu-id="f8a54-119">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="f8a54-120">**Versión de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f8a54-120">**.NET Framework Version:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8a54-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="f8a54-121">See Also</span></span>  
 [<span data-ttu-id="f8a54-122">Funciones estáticas globales de depuración</span><span class="sxs-lookup"><span data-stu-id="f8a54-122">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
