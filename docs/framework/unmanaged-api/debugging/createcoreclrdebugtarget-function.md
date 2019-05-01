---
title: CreateCoreClrDebugTarget (Función)
ms.date: 03/30/2017
api_name:
- CreateCorClrDebugTarget
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- CreateCoreClrDebugTarget
helpviewer_keywords:
- remote debugging API [Silverlight]
- Silverlight, remote debugging
- CreateCoreClrDebugTarget function
ms.assetid: 1cf4ca8e-d9bb-4633-9adf-5e24315bf87a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 48ce5381c745669b813f5b28d801add7daba7825
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61965846"
---
# <a name="createcoreclrdebugtarget-function"></a><span data-ttu-id="c9339-102">CreateCoreClrDebugTarget (Función)</span><span class="sxs-lookup"><span data-stu-id="c9339-102">CreateCoreClrDebugTarget Function</span></span>
<span data-ttu-id="c9339-103">Crea una conexión a un proxy del depurador que se está ejecutando en un equipo remoto y devuelve un [ICoreClrDebugTarget](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md) objeto que puede usarse para consultar los procesos en ejecución y tiempos de ejecución cargados en el equipo remoto.</span><span class="sxs-lookup"><span data-stu-id="c9339-103">Creates a connection to a debugger proxy that is running on a remote machine, and returns an [ICoreClrDebugTarget](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md) object that can be used to query running processes and loaded runtimes on the remote machine.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9339-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c9339-104">Syntax</span></span>  
  
```  
HRESULT CreateCoreClrDebugTarget (  
       [in]  DWORD    dwAddress,   
       [out] ICoreClrDebugTarget**     ppTarget  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c9339-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c9339-105">Parameters</span></span>  
 `dwAddress`  
 <span data-ttu-id="c9339-106">[in] Dirección IPv4 de un equipo de destino remoto.</span><span class="sxs-lookup"><span data-stu-id="c9339-106">[in] IPv4 address of a remote target machine.</span></span>  
  
 `ppTarget`  
 <span data-ttu-id="c9339-107">[out] Puntero a un puntero a un [ICoreClrDebugTarget](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md) objeto que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="c9339-107">[out] Pointer to a pointer to an [ICoreClrDebugTarget](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md) object that will be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c9339-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c9339-108">Return Value</span></span>  
 <span data-ttu-id="c9339-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="c9339-109">S_OK</span></span>  
 <span data-ttu-id="c9339-110">Se determinó el número de CLR en el proceso y las matrices de rutas de acceso e identificadores correspondientes se rellenaron correctamente.</span><span class="sxs-lookup"><span data-stu-id="c9339-110">The number of CLRs in the process was successfully determined, and the corresponding handle and path arrays were properly filled.</span></span>  
  
 <span data-ttu-id="c9339-111">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="c9339-111">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="c9339-112">No se puede asignar memoria suficiente para `ppTarget`.</span><span class="sxs-lookup"><span data-stu-id="c9339-112">Unable to allocate enough memory for `ppTarget`.</span></span>  
  
 <span data-ttu-id="c9339-113">E_FAIL (u otros códigos devueltos de E_)</span><span class="sxs-lookup"><span data-stu-id="c9339-113">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="c9339-114">Otros errores.</span><span class="sxs-lookup"><span data-stu-id="c9339-114">Other failures.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c9339-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c9339-115">Requirements</span></span>  
 <span data-ttu-id="c9339-116">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c9339-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c9339-117">**Encabezado**: CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="c9339-117">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="c9339-118">**Library:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="c9339-118">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="c9339-119">**Versiones de .NET framework:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="c9339-119">**.NET Framework Versions:** 3.5 SP1</span></span>
