---
title: InitDbgTransportManager (Función)
ms.date: 03/30/2017
api_name:
- InitDbgTransportManager
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- InitDbgTransportManager
helpviewer_keywords:
- remote debugging API [Silverlight]
- InitDbgTransportManager function
- Silverlight, remote debugging
ms.assetid: a30102ff-c52e-48c9-b3a9-aa14286a42b2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 948e97064d12dc5b2044faf35aa374e5ba5f2592
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67764784"
---
# <a name="initdbgtransportmanager-function"></a><span data-ttu-id="05806-102">InitDbgTransportManager (Función)</span><span class="sxs-lookup"><span data-stu-id="05806-102">InitDbgTransportManager Function</span></span>
<span data-ttu-id="05806-103">Inicializa el administrador de transporte para conectarse a un destino remoto para la enumeración de procesos y tiempos de ejecución.</span><span class="sxs-lookup"><span data-stu-id="05806-103">Initializes the transport manager to connect to a remote target for process and runtime enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05806-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="05806-104">Syntax</span></span>  
  
```cpp  
HRESULT InitDbgTransportManager ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="05806-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="05806-105">Return Value</span></span>  
 <span data-ttu-id="05806-106">S_OK</span><span class="sxs-lookup"><span data-stu-id="05806-106">S_OK</span></span>  
 <span data-ttu-id="05806-107">Correcto.</span><span class="sxs-lookup"><span data-stu-id="05806-107">Success.</span></span>  
  
 <span data-ttu-id="05806-108">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="05806-108">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="05806-109">La función no pudo asignar memoria para un administrador de transporte.</span><span class="sxs-lookup"><span data-stu-id="05806-109">The function was unable to allocate memory for a transport manager.</span></span>  
  
 <span data-ttu-id="05806-110">E_FAIL (u otros códigos devueltos de E_)</span><span class="sxs-lookup"><span data-stu-id="05806-110">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="05806-111">Otros errores.</span><span class="sxs-lookup"><span data-stu-id="05806-111">Other failures.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="05806-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="05806-112">Requirements</span></span>  
 <span data-ttu-id="05806-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="05806-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="05806-114">**Encabezado**: CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="05806-114">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="05806-115">**Library:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="05806-115">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="05806-116">**Versiones de .NET framework:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="05806-116">**.NET Framework Versions:** 3.5 SP1</span></span>
