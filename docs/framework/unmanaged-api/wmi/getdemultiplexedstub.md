---
title: "Función GetDemultiplexedStub (referencia de API no administrada)"
description: "La función GetDemultiplexedStub crea un receptor de reenviador de objeto para ayudar a un cliente recibir las llamadas asincrónicas de administración de Windows."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: GetDemultiplexedStub
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: GetDemultiplexedStub
helpviewer_keywords: GetDemultiplexedStub function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6ba7ca9941dc148444a4c605fecc8aaf150e8601
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="getdemultiplexedstub-function"></a><span data-ttu-id="fcdfa-103">GetDemultiplexedStub (función)</span><span class="sxs-lookup"><span data-stu-id="fcdfa-103">GetDemultiplexedStub function</span></span>
<span data-ttu-id="fcdfa-104">Crea un receptor de reenviador de objeto para ayudar a un cliente recibir las llamadas asincrónicas de administración de Windows.</span><span class="sxs-lookup"><span data-stu-id="fcdfa-104">Creates an object forwarder sink to assist a client in receiving asynchronous calls from Windows Management.</span></span>
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="fcdfa-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fcdfa-105">Syntax</span></span>  
  
```  
HRESULT GetDemultiplexedStub (
   [in] IUnknown*    pObject, 
   [in] boolean      isLocal, 
   [out] IUnknown**  ppObject
); 
```  

## <a name="parameters"></a><span data-ttu-id="fcdfa-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fcdfa-106">Parameters</span></span>

`pObject`  
<span data-ttu-id="fcdfa-107">[in] Un puntero a la implementación de en proceso del cliente de [IWbemObjectSink](https://msdn.microsoft.com/en-us/library/aa391787(v=vs.85).aspx).</span><span class="sxs-lookup"><span data-stu-id="fcdfa-107">[in] A pointer to the client's in-process implementation of [IWbemObjectSink](https://msdn.microsoft.com/en-us/library/aa391787(v=vs.85).aspx).</span></span>

`isLocal`  
<span data-ttu-id="fcdfa-108">[in] Una marca que indica si el evento es local (`true`); en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="fcdfa-108">[in] A flag that indicates whether the event is local (`true`); otherwise, `false`.</span></span>

`ppObject`  
<span data-ttu-id="fcdfa-109">[out] Un receptor de reenviador de objeto para ayudar a un cliente recibir las llamadas asincrónicas de administración de Windows.</span><span class="sxs-lookup"><span data-stu-id="fcdfa-109">[out] A object forwarder sink to assist a client in receiving asynchronous calls from Windows Management.</span></span>

## <a name="return-value"></a><span data-ttu-id="fcdfa-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="fcdfa-110">Return value</span></span>

<span data-ttu-id="fcdfa-111">Si la función se realiza correctamente, el valor devuelto es `S_OK` (0).</span><span class="sxs-lookup"><span data-stu-id="fcdfa-111">If the function succeeds, the return value is `S_OK` (0).</span></span>

<span data-ttu-id="fcdfa-112">Si se produce un error en la función, el valor devuelto es un código de error distinto de cero.</span><span class="sxs-lookup"><span data-stu-id="fcdfa-112">If the function fails, the return value is a non-zero error code.</span></span> <span data-ttu-id="fcdfa-113">Para obtener información de error extendida, llame a la [GetErrorInfo](geterrorinfo.md) función.</span><span class="sxs-lookup"><span data-stu-id="fcdfa-113">To get extended error information, call the [GetErrorInfo](geterrorinfo.md) function.</span></span>
    
## <a name="requirements"></a><span data-ttu-id="fcdfa-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fcdfa-114">Requirements</span></span>  
 <span data-ttu-id="fcdfa-115">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fcdfa-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fcdfa-116">**Encabezado:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="fcdfa-116">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="fcdfa-117">**Versiones de .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="fcdfa-117">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcdfa-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="fcdfa-118">See also</span></span>  
[<span data-ttu-id="fcdfa-119">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="fcdfa-119">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
