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
ms.openlocfilehash: 42f7020212dd2db793b7c7d20a15c129157e7261
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860765"
---
# <a name="_efn_getmanagedobjectfieldinfo-function"></a><span data-ttu-id="64c4b-102">\_EFN\_GetManagedObjectFieldInfo función)</span><span class="sxs-lookup"><span data-stu-id="64c4b-102">\_EFN\_GetManagedObjectFieldInfo Function</span></span>
<span data-ttu-id="64c4b-103">Obtiene el desplazamiento desde el inicio de un objeto hasta un campo y el valor del campo, a partir del puntero de objeto y nombre de campo especificados.</span><span class="sxs-lookup"><span data-stu-id="64c4b-103">Gets the offset from the start of an object to a field and the field's value, using the provided object pointer and field name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64c4b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="64c4b-104">Syntax</span></span>  
  
```cpp  
HRESULT _EFN_GetManagedObjectFieldInfo(  
    [in]  PDEBUG_CLIENT Client,  
    [in]  ULONG64       objAddr,  
    [in]  __out_ecount (mdNameLen) PSTR szFieldName,  
    [out] PULONG64      pValue,  
    [out] PULONG        pOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="64c4b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="64c4b-105">Parameters</span></span>  
 `Client`  
 <span data-ttu-id="64c4b-106">de Puntero al cliente de depuración.</span><span class="sxs-lookup"><span data-stu-id="64c4b-106">[in] A pointer to the debug client.</span></span>  
  
 `objAddr`  
 <span data-ttu-id="64c4b-107">de Puntero de objeto administrado.</span><span class="sxs-lookup"><span data-stu-id="64c4b-107">[in] A managed object pointer.</span></span>  
  
 <span data-ttu-id="64c4b-108">szFieldName</span><span class="sxs-lookup"><span data-stu-id="64c4b-108">szFieldName</span></span>  
 <span data-ttu-id="64c4b-109">de Puntero de objeto administrado al nombre del campo.</span><span class="sxs-lookup"><span data-stu-id="64c4b-109">[in] A managed object pointer to the field name.</span></span>  
  
 `pValue`  
 <span data-ttu-id="64c4b-110">enuncia Valor del campo.</span><span class="sxs-lookup"><span data-stu-id="64c4b-110">[out] The field value.</span></span> <span data-ttu-id="64c4b-111">Este parámetro puede ser NULL.</span><span class="sxs-lookup"><span data-stu-id="64c4b-111">This parameter can be null.</span></span>  
  
 `pOffset`  
 <span data-ttu-id="64c4b-112">enuncia Desplazamiento desde `objAddr` hasta el campo.</span><span class="sxs-lookup"><span data-stu-id="64c4b-112">[out] The offset from `objAddr` to the field.</span></span> <span data-ttu-id="64c4b-113">Este parámetro puede ser NULL.</span><span class="sxs-lookup"><span data-stu-id="64c4b-113">This parameter can be null.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="64c4b-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="64c4b-114">Remarks</span></span>  
 <span data-ttu-id="64c4b-115">Si el desplazamiento es 0, no se escribe ningún desplazamiento.</span><span class="sxs-lookup"><span data-stu-id="64c4b-115">If the offset is 0, no offset is written.</span></span>  
  
 <span data-ttu-id="64c4b-116">Si no hay código administrado en el subproceso actualmente en contexto, la función devuelve HRESULT SOS_E_NOMANAGEDCODE con un valor de instalación de 0XA0 y un código de error de 0x1000.</span><span class="sxs-lookup"><span data-stu-id="64c4b-116">If there is no managed code on the thread currently in context, the function returns HRESULT SOS_E_NOMANAGEDCODE with a facility value of 0xa0 and an error code of 0x1000.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="64c4b-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="64c4b-117">Requirements</span></span>  
 <span data-ttu-id="64c4b-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="64c4b-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="64c4b-119">**Encabezado:** SOS_Stacktrace. h</span><span class="sxs-lookup"><span data-stu-id="64c4b-119">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="64c4b-120">**Versión de .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="64c4b-120">**.NET Framework Version:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64c4b-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="64c4b-121">See also</span></span>

- [<span data-ttu-id="64c4b-122">Funciones estáticas globales para la depuración</span><span class="sxs-lookup"><span data-stu-id="64c4b-122">Debugging Global Static Functions</span></span>](debugging-global-static-functions.md)
