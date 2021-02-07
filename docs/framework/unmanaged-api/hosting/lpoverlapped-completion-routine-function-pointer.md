---
description: 'Más información acerca de: LPOVERLAPPED_COMPLETION_ROUTINE puntero a función'
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
ms.openlocfilehash: 6645e6a9746404a4ae355a22cf16e6d164c63bed
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99679841"
---
# <a name="lpoverlapped_completion_routine-function-pointer"></a><span data-ttu-id="113f6-103">puntero a la función LPOVERLAPPED_COMPLETION_ROUTINE</span><span class="sxs-lookup"><span data-stu-id="113f6-103">LPOVERLAPPED_COMPLETION_ROUTINE Function Pointer</span></span>

<span data-ttu-id="113f6-104">Apunta a una función que notifica al host cuando se ha completado una e/s superpuesta (es decir, asincrónica) a un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="113f6-104">Points to a function that notifies the host when an overlapped (that is, asynchronous) I/O to a device has completed.</span></span>  
  
 <span data-ttu-id="113f6-105">Este puntero de función ha quedado en desuso en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="113f6-105">This function pointer has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="113f6-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="113f6-106">Syntax</span></span>  
  
```cpp  
typedef VOID (*LPOVERLAPPED_COMPLETION_ROUTINE) (  
    [in] DWORD  dwErrorCode,  
    [in] DWORD  dwNumberOfBytesTransfered,  
    [in] LPVOID lpOverlapped  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="113f6-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="113f6-107">Parameters</span></span>  

 `dwErrorCode`  
 <span data-ttu-id="113f6-108">de Un valor que es un código de error si se ha cerrado el dispositivo; de lo contrario, este valor es cero.</span><span class="sxs-lookup"><span data-stu-id="113f6-108">[in] A value that is an error code if the device has been closed; otherwise, this value is zero.</span></span>  
  
 <span data-ttu-id="113f6-109">Al cerrar un dispositivo, todas las e/s pendientes en el dispositivo se completarán inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="113f6-109">Closing a device causes all pending I/O to the device to be completed immediately.</span></span>  
  
 `dwNumberOfBytesTransfered`  
 <span data-ttu-id="113f6-110">de Número de bytes transferidos por la operación de e/s.</span><span class="sxs-lookup"><span data-stu-id="113f6-110">[in] The number of bytes transferred by the I/O operation.</span></span>  
  
 `lpOverlapped`  
 <span data-ttu-id="113f6-111">de Puntero a una estructura que contiene información que se va a usar para completar la solicitud de e/s.</span><span class="sxs-lookup"><span data-stu-id="113f6-111">[in] A pointer to a structure that contains information to be used to complete the I/O request.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="113f6-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="113f6-112">Remarks</span></span>  

 <span data-ttu-id="113f6-113">La función a la que `LPOVERLAPPED_COMPLETION_ROUTINE` apunta es una función de devolución de llamada y debe ser implementada por el escritor de la aplicación de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="113f6-113">The function to which `LPOVERLAPPED_COMPLETION_ROUTINE` points is a callback function and must be implemented by the writer of the hosting application.</span></span> <span data-ttu-id="113f6-114">La función de devolución de llamada permite al host procesar la solicitud de e/s completada.</span><span class="sxs-lookup"><span data-stu-id="113f6-114">The callback function allows the host to process the completed I/O request.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="113f6-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="113f6-115">Requirements</span></span>  

 <span data-ttu-id="113f6-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="113f6-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="113f6-117">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="113f6-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="113f6-118">**Biblioteca:** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="113f6-118">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="113f6-119">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="113f6-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="113f6-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="113f6-120">See also</span></span>

- [<span data-ttu-id="113f6-121">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="113f6-121">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
