---
title: puntero a la función LPOVERLAPPED_COMPLETION_ROUTINE
ms.date: 03/30/2017
api_name:
- LPOVERLAPPED_COMPLETION_ROUTINE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- LPOVERLAPPED_COMPLETION_ROUTINE
helpviewer_keywords:
- LPOVERLAPPED_COMPLETION_ROUTINE function pointer [.NET Framework hosting]
ms.assetid: 5fb645d9-b818-401c-8c2c-c30d86de58ba
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 59565b28991f6d61ff2c6c77540eace92461aa89
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490171"
---
# <a name="lpoverlappedcompletionroutine-function-pointer"></a><span data-ttu-id="43b30-102">puntero a la función LPOVERLAPPED_COMPLETION_ROUTINE</span><span class="sxs-lookup"><span data-stu-id="43b30-102">LPOVERLAPPED_COMPLETION_ROUTINE Function Pointer</span></span>
<span data-ttu-id="43b30-103">Señala a una función que notifica al host cuándo una superpuesta (es decir, asincrónica) se ha completado la E/S en un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="43b30-103">Points to a function that notifies the host when an overlapped (that is, asynchronous) I/O to a device has completed.</span></span>  
  
 <span data-ttu-id="43b30-104">Este puntero de función ha quedado obsoleto en .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="43b30-104">This function pointer has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43b30-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="43b30-105">Syntax</span></span>  
  
```  
typedef VOID (*LPOVERLAPPED_COMPLETION_ROUTINE) (  
    [in] DWORD  dwErrorCode,  
    [in] DWORD  dwNumberOfBytesTransfered,  
    [in] LPVOID lpOverlapped  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="43b30-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="43b30-106">Parameters</span></span>  
 `dwErrorCode`  
 <span data-ttu-id="43b30-107">[in] Un valor que es un código de error si el dispositivo se ha cerrado; en caso contrario, este valor es cero.</span><span class="sxs-lookup"><span data-stu-id="43b30-107">[in] A value that is an error code if the device has been closed; otherwise, this value is zero.</span></span>  
  
 <span data-ttu-id="43b30-108">Cerrar un dispositivo hace que todas las pendientes de E/S en el dispositivo para completarse inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="43b30-108">Closing a device causes all pending I/O to the device to be completed immediately.</span></span>  
  
 `dwNumberOfBytesTransfered`  
 <span data-ttu-id="43b30-109">[in] El número de bytes transferidos por la operación de E/S.</span><span class="sxs-lookup"><span data-stu-id="43b30-109">[in] The number of bytes transferred by the I/O operation.</span></span>  
  
 `lpOverlapped`  
 <span data-ttu-id="43b30-110">[in] Un puntero a una estructura que contiene información que se utilizará para completar la solicitud de E/S.</span><span class="sxs-lookup"><span data-stu-id="43b30-110">[in] A pointer to a structure that contains information to be used to complete the I/O request.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="43b30-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="43b30-111">Remarks</span></span>  
 <span data-ttu-id="43b30-112">La función a la que `LPOVERLAPPED_COMPLETION_ROUTINE` puntos es una función de devolución de llamada y debe ser implementada por el sistema de escritura de la aplicación de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="43b30-112">The function to which `LPOVERLAPPED_COMPLETION_ROUTINE` points is a callback function and must be implemented by the writer of the hosting application.</span></span> <span data-ttu-id="43b30-113">La función de devolución de llamada permite al host procesar la solicitud de E/S completada.</span><span class="sxs-lookup"><span data-stu-id="43b30-113">The callback function allows the host to process the completed I/O request.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43b30-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="43b30-114">Requirements</span></span>  
 <span data-ttu-id="43b30-115">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="43b30-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43b30-116">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="43b30-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="43b30-117">**Biblioteca:** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="43b30-117">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="43b30-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43b30-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43b30-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="43b30-119">See also</span></span>

- [<span data-ttu-id="43b30-120">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="43b30-120">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
