---
title: Función GetDemultiplexedStub (referencia de la API no administrada)
description: La función GetDemultiplexedStub crea un receptor de reenviador de objetos para ayudar a un cliente a recibir llamadas asincrónicas de la administración de Windows.
ms.date: 11/06/2017
api_name:
- GetDemultiplexedStub
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetDemultiplexedStub
helpviewer_keywords:
- GetDemultiplexedStub function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a2d3885a4a9e54950909053ba18de5b1891e7edf
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798613"
---
# <a name="getdemultiplexedstub-function"></a><span data-ttu-id="c3658-103">GetDemultiplexedStub función)</span><span class="sxs-lookup"><span data-stu-id="c3658-103">GetDemultiplexedStub function</span></span>
<span data-ttu-id="c3658-104">Crea un receptor de reenvío de objetos para ayudar a un cliente a recibir llamadas asincrónicas desde la administración de Windows.</span><span class="sxs-lookup"><span data-stu-id="c3658-104">Creates an object forwarder sink to assist a client in receiving asynchronous calls from Windows Management.</span></span>
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="c3658-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c3658-105">Syntax</span></span>  
  
```cpp  
HRESULT GetDemultiplexedStub (
   [in] IUnknown*    pObject, 
   [in] boolean      isLocal, 
   [out] IUnknown**  ppObject
); 
```  

## <a name="parameters"></a><span data-ttu-id="c3658-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c3658-106">Parameters</span></span>

`pObject`  
<span data-ttu-id="c3658-107">de Un puntero a la implementación en proceso del cliente de [IWbemObjectSink](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectsink).</span><span class="sxs-lookup"><span data-stu-id="c3658-107">[in] A pointer to the client's in-process implementation of [IWbemObjectSink](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectsink).</span></span>

`isLocal`  
<span data-ttu-id="c3658-108">de Marca que indica si el evento es local (`true`); en caso contrario,. `false`</span><span class="sxs-lookup"><span data-stu-id="c3658-108">[in] A flag that indicates whether the event is local (`true`); otherwise, `false`.</span></span>

`ppObject`  
<span data-ttu-id="c3658-109">enuncia Un receptor de reenviador de objetos para ayudar a un cliente a recibir llamadas asincrónicas de la administración de Windows.</span><span class="sxs-lookup"><span data-stu-id="c3658-109">[out] A object forwarder sink to assist a client in receiving asynchronous calls from Windows Management.</span></span>

## <a name="return-value"></a><span data-ttu-id="c3658-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c3658-110">Return value</span></span>

<span data-ttu-id="c3658-111">Si la función se ejecuta correctamente, el valor devuelto es `S_OK` (0).</span><span class="sxs-lookup"><span data-stu-id="c3658-111">If the function succeeds, the return value is `S_OK` (0).</span></span>

<span data-ttu-id="c3658-112">Si se produce un error en la función, el valor devuelto es un código de error distinto de cero.</span><span class="sxs-lookup"><span data-stu-id="c3658-112">If the function fails, the return value is a non-zero error code.</span></span> <span data-ttu-id="c3658-113">Para obtener información de error extendida, llame a la función [GetErrorInfo](geterrorinfo.md) .</span><span class="sxs-lookup"><span data-stu-id="c3658-113">To get extended error information, call the [GetErrorInfo](geterrorinfo.md) function.</span></span>
    
## <a name="requirements"></a><span data-ttu-id="c3658-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c3658-114">Requirements</span></span>  
 <span data-ttu-id="c3658-115">**Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c3658-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3658-116">**Encabezado**: WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="c3658-116">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="c3658-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="c3658-117">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3658-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="c3658-118">See also</span></span>

- [<span data-ttu-id="c3658-119">WMI y contadores de rendimiento (referencia de la API no administrada)</span><span class="sxs-lookup"><span data-stu-id="c3658-119">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
