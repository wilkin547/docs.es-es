---
description: 'Más información acerca de: _EFN_GetManagedExcepStack función'
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
ms.openlocfilehash: a3c7e30a377e10b9d4d0b1dd663a594a0e872f3c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99738317"
---
# <a name="_efn_getmanagedexcepstack-function"></a><span data-ttu-id="2372d-103">\_EFN \_ GetManagedExcepStack función)</span><span class="sxs-lookup"><span data-stu-id="2372d-103">\_EFN\_GetManagedExcepStack Function</span></span>

<span data-ttu-id="2372d-104">Dada una dirección de objeto de excepción administrado, devuelve una versión de cadena del seguimiento de pila que contiene.</span><span class="sxs-lookup"><span data-stu-id="2372d-104">Given a managed exception object address, returns a string version of the stack trace contained inside.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2372d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2372d-105">Syntax</span></span>  
  
```cpp  
HRESULT _EFN_GetManagedExcepStack(  
    [in]  PDEBUG_CLIENT Client,  
    [in]  ULONG64       StackObjAddr,  
    [out] __out_ecount(cbString) PSTR szStackString,  
    [out] ULONG         cbString  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2372d-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2372d-106">Parameters</span></span>  

 `Client`  
 <span data-ttu-id="2372d-107">de Cliente que se está depurando.</span><span class="sxs-lookup"><span data-stu-id="2372d-107">[in] The client being debugged.</span></span>  
  
 `StackObjAddr`  
 <span data-ttu-id="2372d-108">de Un puntero de objeto administrado, derivado de <xref:System.Exception> .</span><span class="sxs-lookup"><span data-stu-id="2372d-108">[in] A managed object pointer, derived from <xref:System.Exception>.</span></span>  
  
 <span data-ttu-id="2372d-109">szStackString</span><span class="sxs-lookup"><span data-stu-id="2372d-109">szStackString</span></span>  
 <span data-ttu-id="2372d-110">enuncia La cadena devuelta.</span><span class="sxs-lookup"><span data-stu-id="2372d-110">[out] The returned string.</span></span>  
  
 `cbString`  
 <span data-ttu-id="2372d-111">enuncia Número de caracteres disponibles en el búfer de cadena.</span><span class="sxs-lookup"><span data-stu-id="2372d-111">[out] The number of characters available in the string buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2372d-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="2372d-112">Remarks</span></span>  

 <span data-ttu-id="2372d-113">Si no hay código administrado en el subproceso actualmente en contexto, la función devuelve HRESULT SOS_E_NOMANAGEDCODE con un valor de instalación de 0XA0 y un código de error de 0x1000.</span><span class="sxs-lookup"><span data-stu-id="2372d-113">If there is no managed code on the thread currently in context, the function returns HRESULT SOS_E_NOMANAGEDCODE with a facility value of 0xa0 and an error code of 0x1000.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2372d-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2372d-114">Requirements</span></span>  

 <span data-ttu-id="2372d-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2372d-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2372d-116">**Encabezado:** SOS_Stacktrace. h</span><span class="sxs-lookup"><span data-stu-id="2372d-116">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="2372d-117">**Versión de .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2372d-117">**.NET Framework Version:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2372d-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="2372d-118">See also</span></span>

- [<span data-ttu-id="2372d-119">Funciones estáticas globales para la depuración</span><span class="sxs-lookup"><span data-stu-id="2372d-119">Debugging Global Static Functions</span></span>](debugging-global-static-functions.md)
