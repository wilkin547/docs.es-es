---
description: 'Más información acerca de: _EFN_GetManagedObjectFieldInfo función'
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
ms.openlocfilehash: 749ab286a86db07c1b66ff2b61ff073d15334800
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99637894"
---
# <a name="_efn_getmanagedobjectfieldinfo-function"></a><span data-ttu-id="69d92-103">\_EFN \_ GetManagedObjectFieldInfo función)</span><span class="sxs-lookup"><span data-stu-id="69d92-103">\_EFN\_GetManagedObjectFieldInfo Function</span></span>

<span data-ttu-id="69d92-104">Obtiene el desplazamiento desde el inicio de un objeto hasta un campo y el valor del campo, a partir del puntero de objeto y nombre de campo especificados.</span><span class="sxs-lookup"><span data-stu-id="69d92-104">Gets the offset from the start of an object to a field and the field's value, using the provided object pointer and field name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69d92-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="69d92-105">Syntax</span></span>  
  
```cpp  
HRESULT _EFN_GetManagedObjectFieldInfo(  
    [in]  PDEBUG_CLIENT Client,  
    [in]  ULONG64       objAddr,  
    [in]  __out_ecount (mdNameLen) PSTR szFieldName,  
    [out] PULONG64      pValue,  
    [out] PULONG        pOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="69d92-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="69d92-106">Parameters</span></span>  

 `Client`  
 <span data-ttu-id="69d92-107">de Puntero al cliente de depuración.</span><span class="sxs-lookup"><span data-stu-id="69d92-107">[in] A pointer to the debug client.</span></span>  
  
 `objAddr`  
 <span data-ttu-id="69d92-108">de Puntero de objeto administrado.</span><span class="sxs-lookup"><span data-stu-id="69d92-108">[in] A managed object pointer.</span></span>  
  
 <span data-ttu-id="69d92-109">szFieldName</span><span class="sxs-lookup"><span data-stu-id="69d92-109">szFieldName</span></span>  
 <span data-ttu-id="69d92-110">de Puntero de objeto administrado al nombre del campo.</span><span class="sxs-lookup"><span data-stu-id="69d92-110">[in] A managed object pointer to the field name.</span></span>  
  
 `pValue`  
 <span data-ttu-id="69d92-111">enuncia Valor del campo.</span><span class="sxs-lookup"><span data-stu-id="69d92-111">[out] The field value.</span></span> <span data-ttu-id="69d92-112">Este parámetro puede ser NULL.</span><span class="sxs-lookup"><span data-stu-id="69d92-112">This parameter can be null.</span></span>  
  
 `pOffset`  
 <span data-ttu-id="69d92-113">enuncia Desplazamiento desde `objAddr` hasta el campo.</span><span class="sxs-lookup"><span data-stu-id="69d92-113">[out] The offset from `objAddr` to the field.</span></span> <span data-ttu-id="69d92-114">Este parámetro puede ser NULL.</span><span class="sxs-lookup"><span data-stu-id="69d92-114">This parameter can be null.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="69d92-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="69d92-115">Remarks</span></span>  

 <span data-ttu-id="69d92-116">Si el desplazamiento es 0, no se escribe ningún desplazamiento.</span><span class="sxs-lookup"><span data-stu-id="69d92-116">If the offset is 0, no offset is written.</span></span>  
  
 <span data-ttu-id="69d92-117">Si no hay código administrado en el subproceso actualmente en contexto, la función devuelve HRESULT SOS_E_NOMANAGEDCODE con un valor de instalación de 0XA0 y un código de error de 0x1000.</span><span class="sxs-lookup"><span data-stu-id="69d92-117">If there is no managed code on the thread currently in context, the function returns HRESULT SOS_E_NOMANAGEDCODE with a facility value of 0xa0 and an error code of 0x1000.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="69d92-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="69d92-118">Requirements</span></span>  

 <span data-ttu-id="69d92-119">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="69d92-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="69d92-120">**Encabezado:** SOS_Stacktrace. h</span><span class="sxs-lookup"><span data-stu-id="69d92-120">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="69d92-121">**Versión de .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="69d92-121">**.NET Framework Version:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69d92-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="69d92-122">See also</span></span>

- [<span data-ttu-id="69d92-123">Funciones estáticas globales para la depuración</span><span class="sxs-lookup"><span data-stu-id="69d92-123">Debugging Global Static Functions</span></span>](debugging-global-static-functions.md)
