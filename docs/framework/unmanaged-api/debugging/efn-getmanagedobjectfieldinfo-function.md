---
title: _EFN_GetManagedObjectFieldInfo (Función)
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c6195d9666afa8fba3f77322366e4709634e53bb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33405251"
---
# <a name="efngetmanagedobjectfieldinfo-function"></a><span data-ttu-id="99ab5-102">_EFN_GetManagedObjectFieldInfo (Función)</span><span class="sxs-lookup"><span data-stu-id="99ab5-102">_EFN_GetManagedObjectFieldInfo Function</span></span>
<span data-ttu-id="99ab5-103">Obtiene el desplazamiento desde el inicio de un objeto hasta un campo y el valor del campo, a partir del puntero de objeto y nombre de campo especificados.</span><span class="sxs-lookup"><span data-stu-id="99ab5-103">Gets the offset from the start of an object to a field and the field's value, using the provided object pointer and field name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99ab5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="99ab5-104">Syntax</span></span>  
  
```  
HRESULT _EFN_GetManagedObjectFieldInfo(  
    [in]  PDEBUG_CLIENT Client,  
    [in]  ULONG64       objAddr,  
    [in]  __out_ecount (mdNameLen) PSTR szFieldName,  
    [out] PULONG64      pValue,  
    [out] PULONG        pOffset  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="99ab5-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="99ab5-105">Parameters</span></span>  
 `Client`  
 <span data-ttu-id="99ab5-106">[in] Un puntero al cliente de depuración.</span><span class="sxs-lookup"><span data-stu-id="99ab5-106">[in] A pointer to the debug client.</span></span>  
  
 `objAddr`  
 <span data-ttu-id="99ab5-107">[in] Un puntero de objeto administrado.</span><span class="sxs-lookup"><span data-stu-id="99ab5-107">[in] A managed object pointer.</span></span>  
  
 <span data-ttu-id="99ab5-108">szFieldName</span><span class="sxs-lookup"><span data-stu-id="99ab5-108">szFieldName</span></span>  
 <span data-ttu-id="99ab5-109">[in] Un puntero de objeto administrado por el nombre de campo.</span><span class="sxs-lookup"><span data-stu-id="99ab5-109">[in] A managed object pointer to the field name.</span></span>  
  
 `pValue`  
 <span data-ttu-id="99ab5-110">[out] El valor del campo.</span><span class="sxs-lookup"><span data-stu-id="99ab5-110">[out] The field value.</span></span> <span data-ttu-id="99ab5-111">Este parámetro puede ser NULL.</span><span class="sxs-lookup"><span data-stu-id="99ab5-111">This parameter can be null.</span></span>  
  
 `pOffset`  
 <span data-ttu-id="99ab5-112">[out] El desplazamiento de `objAddr` al campo.</span><span class="sxs-lookup"><span data-stu-id="99ab5-112">[out] The offset from `objAddr` to the field.</span></span> <span data-ttu-id="99ab5-113">Este parámetro puede ser NULL.</span><span class="sxs-lookup"><span data-stu-id="99ab5-113">This parameter can be null.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="99ab5-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="99ab5-114">Remarks</span></span>  
 <span data-ttu-id="99ab5-115">Si el desplazamiento es 0, no se escribe ningún desplazamiento.</span><span class="sxs-lookup"><span data-stu-id="99ab5-115">If the offset is 0, no offset is written.</span></span>  
  
 <span data-ttu-id="99ab5-116">Si no hay código administrado en el subproceso actualmente en contexto, la función devuelve HRESULT SOS_E_NOMANAGEDCODE con un valor 0xa0 y el código de error de 0 x 1000.</span><span class="sxs-lookup"><span data-stu-id="99ab5-116">If there is no managed code on the thread currently in context, the function returns HRESULT SOS_E_NOMANAGEDCODE with a facility value of 0xa0 and an error code of 0x1000.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99ab5-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="99ab5-117">Requirements</span></span>  
 <span data-ttu-id="99ab5-118">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="99ab5-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99ab5-119">**Encabezado:** SOS_Stacktrace.h</span><span class="sxs-lookup"><span data-stu-id="99ab5-119">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="99ab5-120">**Versión de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99ab5-120">**.NET Framework Version:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99ab5-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="99ab5-121">See Also</span></span>  
 [<span data-ttu-id="99ab5-122">Funciones estáticas globales de depuración</span><span class="sxs-lookup"><span data-stu-id="99ab5-122">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
