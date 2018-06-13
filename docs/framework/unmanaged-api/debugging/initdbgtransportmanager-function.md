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
ms.openlocfilehash: 74cb2c7d1f79d23e1331cc7192ba2d6acfd9835c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33423668"
---
# <a name="initdbgtransportmanager-function"></a><span data-ttu-id="9ee27-102">InitDbgTransportManager (Función)</span><span class="sxs-lookup"><span data-stu-id="9ee27-102">InitDbgTransportManager Function</span></span>
<span data-ttu-id="9ee27-103">Inicializa el administrador de transporte para conectarse a un destino remoto para la enumeración de proceso y tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="9ee27-103">Initializes the transport manager to connect to a remote target for process and runtime enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ee27-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9ee27-104">Syntax</span></span>  
  
```  
HRESULT InitDbgTransportManager ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="9ee27-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="9ee27-105">Return Value</span></span>  
 <span data-ttu-id="9ee27-106">S_OK</span><span class="sxs-lookup"><span data-stu-id="9ee27-106">S_OK</span></span>  
 <span data-ttu-id="9ee27-107">Correcto.</span><span class="sxs-lookup"><span data-stu-id="9ee27-107">Success.</span></span>  
  
 <span data-ttu-id="9ee27-108">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="9ee27-108">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="9ee27-109">La función no pudo asignar memoria para un administrador de transporte.</span><span class="sxs-lookup"><span data-stu-id="9ee27-109">The function was unable to allocate memory for a transport manager.</span></span>  
  
 <span data-ttu-id="9ee27-110">E_FAIL (u otros códigos devueltos de E_)</span><span class="sxs-lookup"><span data-stu-id="9ee27-110">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="9ee27-111">Otros errores.</span><span class="sxs-lookup"><span data-stu-id="9ee27-111">Other failures.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ee27-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9ee27-112">Requirements</span></span>  
 <span data-ttu-id="9ee27-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9ee27-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ee27-114">**Encabezado:** CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="9ee27-114">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="9ee27-115">**Biblioteca:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="9ee27-115">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="9ee27-116">**Versiones de .NET framework:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="9ee27-116">**.NET Framework Versions:** 3.5 SP1</span></span>
