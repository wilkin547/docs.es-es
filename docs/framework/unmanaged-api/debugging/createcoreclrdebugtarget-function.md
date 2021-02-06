---
description: 'Más información acerca de: Createcoreclrdebugtarget ((función)'
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
ms.openlocfilehash: 30a6af29e6e1a6ee2c827049a3c792f2d663a702
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99661581"
---
# <a name="createcoreclrdebugtarget-function"></a><span data-ttu-id="d0d1d-103">CreateCoreClrDebugTarget (Función)</span><span class="sxs-lookup"><span data-stu-id="d0d1d-103">CreateCoreClrDebugTarget Function</span></span>

<span data-ttu-id="d0d1d-104">Crea una conexión a un proxy del depurador que se ejecuta en un equipo remoto y devuelve un objeto [ICoreClrDebugTarget](icoreclrdebugtarget-interface.md) que se puede usar para consultar los procesos en ejecución y los tiempos de ejecución cargados en el equipo remoto.</span><span class="sxs-lookup"><span data-stu-id="d0d1d-104">Creates a connection to a debugger proxy that is running on a remote machine, and returns an [ICoreClrDebugTarget](icoreclrdebugtarget-interface.md) object that can be used to query running processes and loaded runtimes on the remote machine.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0d1d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d0d1d-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateCoreClrDebugTarget (  
       [in]  DWORD    dwAddress,
       [out] ICoreClrDebugTarget**     ppTarget  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d0d1d-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d0d1d-106">Parameters</span></span>  

 `dwAddress`  
 <span data-ttu-id="d0d1d-107">[in] Dirección IPv4 de un equipo de destino remoto.</span><span class="sxs-lookup"><span data-stu-id="d0d1d-107">[in] IPv4 address of a remote target machine.</span></span>  
  
 `ppTarget`  
 <span data-ttu-id="d0d1d-108">enuncia Puntero a un puntero a un objeto [ICoreClrDebugTarget](icoreclrdebugtarget-interface.md) que se creará.</span><span class="sxs-lookup"><span data-stu-id="d0d1d-108">[out] Pointer to a pointer to an [ICoreClrDebugTarget](icoreclrdebugtarget-interface.md) object that will be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d0d1d-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d0d1d-109">Return Value</span></span>  

 <span data-ttu-id="d0d1d-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="d0d1d-110">S_OK</span></span>  
 <span data-ttu-id="d0d1d-111">Se determinó el número de CLR en el proceso y las matrices de rutas de acceso e identificadores correspondientes se rellenaron correctamente.</span><span class="sxs-lookup"><span data-stu-id="d0d1d-111">The number of CLRs in the process was successfully determined, and the corresponding handle and path arrays were properly filled.</span></span>  
  
 <span data-ttu-id="d0d1d-112">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="d0d1d-112">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="d0d1d-113">No se puede asignar memoria suficiente para `ppTarget`.</span><span class="sxs-lookup"><span data-stu-id="d0d1d-113">Unable to allocate enough memory for `ppTarget`.</span></span>  
  
 <span data-ttu-id="d0d1d-114">E_FAIL (u otros códigos devueltos de E_)</span><span class="sxs-lookup"><span data-stu-id="d0d1d-114">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="d0d1d-115">Otros errores.</span><span class="sxs-lookup"><span data-stu-id="d0d1d-115">Other failures.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d0d1d-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d0d1d-116">Requirements</span></span>  

 <span data-ttu-id="d0d1d-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d0d1d-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d0d1d-118">**Encabezado:** CoreClrRemoteDebuggingInterfaces. h</span><span class="sxs-lookup"><span data-stu-id="d0d1d-118">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="d0d1d-119">**Biblioteca:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="d0d1d-119">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="d0d1d-120">**.NET Framework versiones:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="d0d1d-120">**.NET Framework Versions:** 3.5 SP1</span></span>
