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
ms.openlocfilehash: a5b4783eadb8045733b9ebd6d10c4e31f7829498
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95716686"
---
# <a name="initdbgtransportmanager-function"></a><span data-ttu-id="87864-102">InitDbgTransportManager (Función)</span><span class="sxs-lookup"><span data-stu-id="87864-102">InitDbgTransportManager Function</span></span>

<span data-ttu-id="87864-103">Inicializa el administrador de transporte para conectarse a un destino remoto para la enumeración de procesos y tiempos de ejecución.</span><span class="sxs-lookup"><span data-stu-id="87864-103">Initializes the transport manager to connect to a remote target for process and runtime enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87864-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="87864-104">Syntax</span></span>  
  
```cpp  
HRESULT InitDbgTransportManager ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="87864-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="87864-105">Return Value</span></span>  

 <span data-ttu-id="87864-106">S_OK</span><span class="sxs-lookup"><span data-stu-id="87864-106">S_OK</span></span>  
 <span data-ttu-id="87864-107">Correcto.</span><span class="sxs-lookup"><span data-stu-id="87864-107">Success.</span></span>  
  
 <span data-ttu-id="87864-108">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="87864-108">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="87864-109">La función no pudo asignar memoria para un administrador de transporte.</span><span class="sxs-lookup"><span data-stu-id="87864-109">The function was unable to allocate memory for a transport manager.</span></span>  
  
 <span data-ttu-id="87864-110">E_FAIL (u otros códigos devueltos de E_)</span><span class="sxs-lookup"><span data-stu-id="87864-110">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="87864-111">Otros errores.</span><span class="sxs-lookup"><span data-stu-id="87864-111">Other failures.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87864-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="87864-112">Requirements</span></span>  

 <span data-ttu-id="87864-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="87864-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="87864-114">**Encabezado:** CoreClrRemoteDebuggingInterfaces. h</span><span class="sxs-lookup"><span data-stu-id="87864-114">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="87864-115">**Biblioteca:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="87864-115">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="87864-116">**.NET Framework versiones:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="87864-116">**.NET Framework Versions:** 3.5 SP1</span></span>
