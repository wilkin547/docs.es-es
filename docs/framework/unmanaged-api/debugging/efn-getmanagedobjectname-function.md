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
ms.openlocfilehash: 708ac2e407bf6f87dbe314a0e87cdd16f45b2bcf
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860745"
---
# <a name="_efn_getmanagedobjectname-function"></a><span data-ttu-id="94bea-102">\_EFN\_GetManagedObjectName función)</span><span class="sxs-lookup"><span data-stu-id="94bea-102">\_EFN\_GetManagedObjectName Function</span></span>
<span data-ttu-id="94bea-103">Obtiene el nombre de un tipo mediante el puntero de objeto administrado proporcionado.</span><span class="sxs-lookup"><span data-stu-id="94bea-103">Gets the name of a type using the provided managed object pointer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94bea-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="94bea-104">Syntax</span></span>  
  
```cpp  
HRESULT _EFN_GetManagedObjectName(  
    [in]  PDEBUG_CLIENT  Client,  
    [in]  ULONG64        objAddr,  
    [out] __out_ecount(cbName) PSTR szName,  
    [out] ULONG          cbName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="94bea-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="94bea-105">Parameters</span></span>  
 `Client`  
 <span data-ttu-id="94bea-106">de Puntero al cliente de depuración.</span><span class="sxs-lookup"><span data-stu-id="94bea-106">[in] A pointer to the debug client.</span></span>  
  
 `objAddr`  
 <span data-ttu-id="94bea-107">de Puntero de objeto administrado.</span><span class="sxs-lookup"><span data-stu-id="94bea-107">[in] A managed object pointer.</span></span>  
  
 <span data-ttu-id="94bea-108">szName</span><span class="sxs-lookup"><span data-stu-id="94bea-108">szName</span></span>  
 <span data-ttu-id="94bea-109">enuncia Nombre del tipo.</span><span class="sxs-lookup"><span data-stu-id="94bea-109">[out] The name of the type.</span></span>  
  
 `cbName`  
 <span data-ttu-id="94bea-110">enuncia Número de caracteres disponibles en el búfer de cadena.</span><span class="sxs-lookup"><span data-stu-id="94bea-110">[out] The number of characters available in the string buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="94bea-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="94bea-111">Remarks</span></span>  
 <span data-ttu-id="94bea-112">Si no hay código administrado en el subproceso actualmente en contexto, la función devuelve HRESULT SOS_E_NOMANAGEDCODE con un valor de instalación de 0XA0 y un código de error de 0x1000.</span><span class="sxs-lookup"><span data-stu-id="94bea-112">If there is no managed code on the thread currently in context, the function returns HRESULT SOS_E_NOMANAGEDCODE with a facility value of 0xa0 and an error code of 0x1000.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="94bea-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="94bea-113">Requirements</span></span>  
 <span data-ttu-id="94bea-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="94bea-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94bea-115">**Encabezado:** SOS_Stacktrace. h</span><span class="sxs-lookup"><span data-stu-id="94bea-115">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="94bea-116">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94bea-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94bea-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="94bea-117">See also</span></span>

- [<span data-ttu-id="94bea-118">Funciones estáticas globales para la depuración</span><span class="sxs-lookup"><span data-stu-id="94bea-118">Debugging Global Static Functions</span></span>](debugging-global-static-functions.md)
