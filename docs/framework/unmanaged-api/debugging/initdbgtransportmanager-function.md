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
ms.openlocfilehash: e18ceb25b9c58a9710ef967cb071e3ef55beea8c
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421051"
---
# <a name="initdbgtransportmanager-function"></a><span data-ttu-id="5a85d-102">InitDbgTransportManager (Función)</span><span class="sxs-lookup"><span data-stu-id="5a85d-102">InitDbgTransportManager Function</span></span>
<span data-ttu-id="5a85d-103">Inicializa el administrador de transporte para conectarse a un destino remoto para la enumeración de procesos y tiempos de ejecución.</span><span class="sxs-lookup"><span data-stu-id="5a85d-103">Initializes the transport manager to connect to a remote target for process and runtime enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a85d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5a85d-104">Syntax</span></span>  
  
```cpp  
HRESULT InitDbgTransportManager ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="5a85d-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="5a85d-105">Return Value</span></span>  
 <span data-ttu-id="5a85d-106">S_OK</span><span class="sxs-lookup"><span data-stu-id="5a85d-106">S_OK</span></span>  
 <span data-ttu-id="5a85d-107">Correcto.</span><span class="sxs-lookup"><span data-stu-id="5a85d-107">Success.</span></span>  
  
 <span data-ttu-id="5a85d-108">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="5a85d-108">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="5a85d-109">La función no pudo asignar memoria para un administrador de transporte.</span><span class="sxs-lookup"><span data-stu-id="5a85d-109">The function was unable to allocate memory for a transport manager.</span></span>  
  
 <span data-ttu-id="5a85d-110">E_FAIL (u otros códigos devueltos de E_)</span><span class="sxs-lookup"><span data-stu-id="5a85d-110">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="5a85d-111">Otros errores.</span><span class="sxs-lookup"><span data-stu-id="5a85d-111">Other failures.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a85d-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5a85d-112">Requirements</span></span>  
 <span data-ttu-id="5a85d-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5a85d-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a85d-114">**Encabezado:** CoreClrRemoteDebuggingInterfaces. h</span><span class="sxs-lookup"><span data-stu-id="5a85d-114">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="5a85d-115">**Biblioteca:** mscordbi_macx86. dll</span><span class="sxs-lookup"><span data-stu-id="5a85d-115">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="5a85d-116">**.NET Framework versiones:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="5a85d-116">**.NET Framework Versions:** 3.5 SP1</span></span>
