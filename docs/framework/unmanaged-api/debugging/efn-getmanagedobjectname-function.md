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
ms.openlocfilehash: 9230e1fcba7c0492e50773e7ca13fb16f07238a2
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789133"
---
# <a name="_efn_getmanagedobjectname-function"></a><span data-ttu-id="e7fa7-102">\_EFN\_función GetManagedObjectName</span><span class="sxs-lookup"><span data-stu-id="e7fa7-102">\_EFN\_GetManagedObjectName Function</span></span>
<span data-ttu-id="e7fa7-103">Obtiene el nombre de un tipo mediante el puntero de objeto administrado proporcionado.</span><span class="sxs-lookup"><span data-stu-id="e7fa7-103">Gets the name of a type using the provided managed object pointer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7fa7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e7fa7-104">Syntax</span></span>  
  
```cpp  
HRESULT _EFN_GetManagedObjectName(  
    [in]  PDEBUG_CLIENT  Client,  
    [in]  ULONG64        objAddr,  
    [out] __out_ecount(cbName) PSTR szName,  
    [out] ULONG          cbName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e7fa7-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="e7fa7-105">Parameters</span></span>  
 `Client`  
 <span data-ttu-id="e7fa7-106">de Puntero al cliente de depuración.</span><span class="sxs-lookup"><span data-stu-id="e7fa7-106">[in] A pointer to the debug client.</span></span>  
  
 `objAddr`  
 <span data-ttu-id="e7fa7-107">de Puntero de objeto administrado.</span><span class="sxs-lookup"><span data-stu-id="e7fa7-107">[in] A managed object pointer.</span></span>  
  
 <span data-ttu-id="e7fa7-108">szName</span><span class="sxs-lookup"><span data-stu-id="e7fa7-108">szName</span></span>  
 <span data-ttu-id="e7fa7-109">enuncia Nombre del tipo.</span><span class="sxs-lookup"><span data-stu-id="e7fa7-109">[out] The name of the type.</span></span>  
  
 `cbName`  
 <span data-ttu-id="e7fa7-110">enuncia Número de caracteres disponibles en el búfer de cadena.</span><span class="sxs-lookup"><span data-stu-id="e7fa7-110">[out] The number of characters available in the string buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e7fa7-111">Notas</span><span class="sxs-lookup"><span data-stu-id="e7fa7-111">Remarks</span></span>  
 <span data-ttu-id="e7fa7-112">Si no hay código administrado en el subproceso actualmente en contexto, la función devuelve HRESULT SOS_E_NOMANAGEDCODE con un valor de instalación de 0XA0 y un código de error de 0x1000.</span><span class="sxs-lookup"><span data-stu-id="e7fa7-112">If there is no managed code on the thread currently in context, the function returns HRESULT SOS_E_NOMANAGEDCODE with a facility value of 0xa0 and an error code of 0x1000.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7fa7-113">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="e7fa7-113">Requirements</span></span>  
 <span data-ttu-id="e7fa7-114">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e7fa7-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7fa7-115">**Encabezado:** SOS_Stacktrace. h</span><span class="sxs-lookup"><span data-stu-id="e7fa7-115">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="e7fa7-116">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e7fa7-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7fa7-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="e7fa7-117">See also</span></span>

- [<span data-ttu-id="e7fa7-118">Funciones estáticas globales de depuración</span><span class="sxs-lookup"><span data-stu-id="e7fa7-118">Debugging Global Static Functions</span></span>](debugging-global-static-functions.md)
