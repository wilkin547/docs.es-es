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
ms.openlocfilehash: cd4b7ffef9c0ba3aba54387245b2d5c9ec1ae906
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33441761"
---
# <a name="lpoverlappedcompletionroutine-function-pointer"></a><span data-ttu-id="1c493-102">puntero a la función LPOVERLAPPED_COMPLETION_ROUTINE</span><span class="sxs-lookup"><span data-stu-id="1c493-102">LPOVERLAPPED_COMPLETION_ROUTINE Function Pointer</span></span>
<span data-ttu-id="1c493-103">Señala a una función que notifica al host cuándo una superposición (es decir, asincrónica) ha completado la E/S en un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1c493-103">Points to a function that notifies the host when an overlapped (that is, asynchronous) I/O to a device has completed.</span></span>  
  
 <span data-ttu-id="1c493-104">Este puntero de función está desusada en la [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1c493-104">This function pointer has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c493-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1c493-105">Syntax</span></span>  
  
```  
typedef VOID (*LPOVERLAPPED_COMPLETION_ROUTINE) (  
    [in] DWORD  dwErrorCode,  
    [in] DWORD  dwNumberOfBytesTransfered,  
    [in] LPVOID lpOverlapped  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1c493-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1c493-106">Parameters</span></span>  
 `dwErrorCode`  
 <span data-ttu-id="1c493-107">[in] Un valor que es un código de error si se ha cerrado el dispositivo; en caso contrario, este valor es cero.</span><span class="sxs-lookup"><span data-stu-id="1c493-107">[in] A value that is an error code if the device has been closed; otherwise, this value is zero.</span></span>  
  
 <span data-ttu-id="1c493-108">Cerrar un dispositivo, se produce todas pendientes de E/S en el dispositivo para completar de forma inmediata.</span><span class="sxs-lookup"><span data-stu-id="1c493-108">Closing a device causes all pending I/O to the device to be completed immediately.</span></span>  
  
 `dwNumberOfBytesTransfered`  
 <span data-ttu-id="1c493-109">[in] El número de bytes transferidos por la operación de E/S.</span><span class="sxs-lookup"><span data-stu-id="1c493-109">[in] The number of bytes transferred by the I/O operation.</span></span>  
  
 `lpOverlapped`  
 <span data-ttu-id="1c493-110">[in] Un puntero a una estructura que contiene información que se utilizará para completar la solicitud de E/S.</span><span class="sxs-lookup"><span data-stu-id="1c493-110">[in] A pointer to a structure that contains information to be used to complete the I/O request.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1c493-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1c493-111">Remarks</span></span>  
 <span data-ttu-id="1c493-112">La función a la que `LPOVERLAPPED_COMPLETION_ROUTINE` puntos es una función de devolución de llamada y debe ser implementada por el sistema de escritura de la aplicación host.</span><span class="sxs-lookup"><span data-stu-id="1c493-112">The function to which `LPOVERLAPPED_COMPLETION_ROUTINE` points is a callback function and must be implemented by the writer of the hosting application.</span></span> <span data-ttu-id="1c493-113">La función de devolución de llamada permite al host procesar la solicitud de E/S completada.</span><span class="sxs-lookup"><span data-stu-id="1c493-113">The callback function allows the host to process the completed I/O request.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c493-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1c493-114">Requirements</span></span>  
 <span data-ttu-id="1c493-115">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1c493-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c493-116">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1c493-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1c493-117">**Biblioteca:** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="1c493-117">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="1c493-118">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c493-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c493-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="1c493-119">See Also</span></span>  
 [<span data-ttu-id="1c493-120">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="1c493-120">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
