---
description: 'Más información acerca de: Initdbgtransportmanager ((función)'
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
ms.openlocfilehash: 19cdfcbe3a5b120c11fc781476410833997b8c6e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790443"
---
# <a name="initdbgtransportmanager-function"></a><span data-ttu-id="7f1c5-103">InitDbgTransportManager (Función)</span><span class="sxs-lookup"><span data-stu-id="7f1c5-103">InitDbgTransportManager Function</span></span>

<span data-ttu-id="7f1c5-104">Inicializa el administrador de transporte para conectarse a un destino remoto para la enumeración de procesos y tiempos de ejecución.</span><span class="sxs-lookup"><span data-stu-id="7f1c5-104">Initializes the transport manager to connect to a remote target for process and runtime enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f1c5-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7f1c5-105">Syntax</span></span>  
  
```cpp  
HRESULT InitDbgTransportManager ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="7f1c5-106">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="7f1c5-106">Return Value</span></span>  

 <span data-ttu-id="7f1c5-107">S_OK</span><span class="sxs-lookup"><span data-stu-id="7f1c5-107">S_OK</span></span>  
 <span data-ttu-id="7f1c5-108">Correcto.</span><span class="sxs-lookup"><span data-stu-id="7f1c5-108">Success.</span></span>  
  
 <span data-ttu-id="7f1c5-109">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="7f1c5-109">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="7f1c5-110">La función no pudo asignar memoria para un administrador de transporte.</span><span class="sxs-lookup"><span data-stu-id="7f1c5-110">The function was unable to allocate memory for a transport manager.</span></span>  
  
 <span data-ttu-id="7f1c5-111">E_FAIL (u otros códigos devueltos de E_)</span><span class="sxs-lookup"><span data-stu-id="7f1c5-111">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="7f1c5-112">Otros errores.</span><span class="sxs-lookup"><span data-stu-id="7f1c5-112">Other failures.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7f1c5-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7f1c5-113">Requirements</span></span>  

 <span data-ttu-id="7f1c5-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7f1c5-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7f1c5-115">**Encabezado:** CoreClrRemoteDebuggingInterfaces. h</span><span class="sxs-lookup"><span data-stu-id="7f1c5-115">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="7f1c5-116">**Biblioteca:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="7f1c5-116">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="7f1c5-117">**.NET Framework versiones:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="7f1c5-117">**.NET Framework Versions:** 3.5 SP1</span></span>
