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
ms.openlocfilehash: c50fe09648793ba7340960654811ff31187269d8
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860787"
---
# <a name="_efn_getmanagedexcepstack-function"></a><span data-ttu-id="ce9e0-102">\_EFN\_GetManagedExcepStack función)</span><span class="sxs-lookup"><span data-stu-id="ce9e0-102">\_EFN\_GetManagedExcepStack Function</span></span>
<span data-ttu-id="ce9e0-103">Dada una dirección de objeto de excepción administrado, devuelve una versión de cadena del seguimiento de pila que contiene.</span><span class="sxs-lookup"><span data-stu-id="ce9e0-103">Given a managed exception object address, returns a string version of the stack trace contained inside.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce9e0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ce9e0-104">Syntax</span></span>  
  
```cpp  
HRESULT _EFN_GetManagedExcepStack(  
    [in]  PDEBUG_CLIENT Client,  
    [in]  ULONG64       StackObjAddr,  
    [out] __out_ecount(cbString) PSTR szStackString,  
    [out] ULONG         cbString  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ce9e0-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ce9e0-105">Parameters</span></span>  
 `Client`  
 <span data-ttu-id="ce9e0-106">de Cliente que se está depurando.</span><span class="sxs-lookup"><span data-stu-id="ce9e0-106">[in] The client being debugged.</span></span>  
  
 `StackObjAddr`  
 <span data-ttu-id="ce9e0-107">de Un puntero de objeto administrado, derivado <xref:System.Exception>de.</span><span class="sxs-lookup"><span data-stu-id="ce9e0-107">[in] A managed object pointer, derived from <xref:System.Exception>.</span></span>  
  
 <span data-ttu-id="ce9e0-108">szStackString</span><span class="sxs-lookup"><span data-stu-id="ce9e0-108">szStackString</span></span>  
 <span data-ttu-id="ce9e0-109">enuncia La cadena devuelta.</span><span class="sxs-lookup"><span data-stu-id="ce9e0-109">[out] The returned string.</span></span>  
  
 `cbString`  
 <span data-ttu-id="ce9e0-110">enuncia Número de caracteres disponibles en el búfer de cadena.</span><span class="sxs-lookup"><span data-stu-id="ce9e0-110">[out] The number of characters available in the string buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ce9e0-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ce9e0-111">Remarks</span></span>  
 <span data-ttu-id="ce9e0-112">Si no hay código administrado en el subproceso actualmente en contexto, la función devuelve HRESULT SOS_E_NOMANAGEDCODE con un valor de instalación de 0XA0 y un código de error de 0x1000.</span><span class="sxs-lookup"><span data-stu-id="ce9e0-112">If there is no managed code on the thread currently in context, the function returns HRESULT SOS_E_NOMANAGEDCODE with a facility value of 0xa0 and an error code of 0x1000.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce9e0-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ce9e0-113">Requirements</span></span>  
 <span data-ttu-id="ce9e0-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ce9e0-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce9e0-115">**Encabezado:** SOS_Stacktrace. h</span><span class="sxs-lookup"><span data-stu-id="ce9e0-115">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="ce9e0-116">**Versión de .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce9e0-116">**.NET Framework Version:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce9e0-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ce9e0-117">See also</span></span>

- [<span data-ttu-id="ce9e0-118">Funciones estáticas globales para la depuración</span><span class="sxs-lookup"><span data-stu-id="ce9e0-118">Debugging Global Static Functions</span></span>](debugging-global-static-functions.md)
