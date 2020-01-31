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
ms.openlocfilehash: 182424632e4f81dfdf86e87dc6bb2c75c2780fce
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793772"
---
# <a name="_efn_getmanagedobjectfieldinfo-function"></a><span data-ttu-id="aae83-102">\_EFN\_función GetManagedObjectFieldInfo</span><span class="sxs-lookup"><span data-stu-id="aae83-102">\_EFN\_GetManagedObjectFieldInfo Function</span></span>
<span data-ttu-id="aae83-103">Obtiene el desplazamiento desde el inicio de un objeto hasta un campo y el valor del campo, a partir del puntero de objeto y nombre de campo especificados.</span><span class="sxs-lookup"><span data-stu-id="aae83-103">Gets the offset from the start of an object to a field and the field's value, using the provided object pointer and field name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aae83-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="aae83-104">Syntax</span></span>  
  
```cpp  
HRESULT _EFN_GetManagedObjectFieldInfo(  
    [in]  PDEBUG_CLIENT Client,  
    [in]  ULONG64       objAddr,  
    [in]  __out_ecount (mdNameLen) PSTR szFieldName,  
    [out] PULONG64      pValue,  
    [out] PULONG        pOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aae83-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="aae83-105">Parameters</span></span>  
 `Client`  
 <span data-ttu-id="aae83-106">de Puntero al cliente de depuración.</span><span class="sxs-lookup"><span data-stu-id="aae83-106">[in] A pointer to the debug client.</span></span>  
  
 `objAddr`  
 <span data-ttu-id="aae83-107">de Puntero de objeto administrado.</span><span class="sxs-lookup"><span data-stu-id="aae83-107">[in] A managed object pointer.</span></span>  
  
 <span data-ttu-id="aae83-108">szFieldName</span><span class="sxs-lookup"><span data-stu-id="aae83-108">szFieldName</span></span>  
 <span data-ttu-id="aae83-109">de Puntero de objeto administrado al nombre del campo.</span><span class="sxs-lookup"><span data-stu-id="aae83-109">[in] A managed object pointer to the field name.</span></span>  
  
 `pValue`  
 <span data-ttu-id="aae83-110">enuncia Valor del campo.</span><span class="sxs-lookup"><span data-stu-id="aae83-110">[out] The field value.</span></span> <span data-ttu-id="aae83-111">Este parámetro puede ser NULL.</span><span class="sxs-lookup"><span data-stu-id="aae83-111">This parameter can be null.</span></span>  
  
 `pOffset`  
 <span data-ttu-id="aae83-112">enuncia Desplazamiento desde `objAddr` al campo.</span><span class="sxs-lookup"><span data-stu-id="aae83-112">[out] The offset from `objAddr` to the field.</span></span> <span data-ttu-id="aae83-113">Este parámetro puede ser NULL.</span><span class="sxs-lookup"><span data-stu-id="aae83-113">This parameter can be null.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aae83-114">Notas</span><span class="sxs-lookup"><span data-stu-id="aae83-114">Remarks</span></span>  
 <span data-ttu-id="aae83-115">Si el desplazamiento es 0, no se escribe ningún desplazamiento.</span><span class="sxs-lookup"><span data-stu-id="aae83-115">If the offset is 0, no offset is written.</span></span>  
  
 <span data-ttu-id="aae83-116">Si no hay código administrado en el subproceso actualmente en contexto, la función devuelve HRESULT SOS_E_NOMANAGEDCODE con un valor de instalación de 0XA0 y un código de error de 0x1000.</span><span class="sxs-lookup"><span data-stu-id="aae83-116">If there is no managed code on the thread currently in context, the function returns HRESULT SOS_E_NOMANAGEDCODE with a facility value of 0xa0 and an error code of 0x1000.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aae83-117">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="aae83-117">Requirements</span></span>  
 <span data-ttu-id="aae83-118">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aae83-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aae83-119">**Encabezado:** SOS_Stacktrace. h</span><span class="sxs-lookup"><span data-stu-id="aae83-119">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="aae83-120">**Versión de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aae83-120">**.NET Framework Version:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aae83-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="aae83-121">See also</span></span>

- [<span data-ttu-id="aae83-122">Funciones estáticas globales de depuración</span><span class="sxs-lookup"><span data-stu-id="aae83-122">Debugging Global Static Functions</span></span>](debugging-global-static-functions.md)
