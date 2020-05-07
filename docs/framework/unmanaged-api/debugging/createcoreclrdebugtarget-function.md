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
ms.openlocfilehash: 2271611b5cbbfe487e5798be0429ed94c227a67f
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860876"
---
# <a name="createcoreclrdebugtarget-function"></a><span data-ttu-id="01de1-102">CreateCoreClrDebugTarget (Función)</span><span class="sxs-lookup"><span data-stu-id="01de1-102">CreateCoreClrDebugTarget Function</span></span>
<span data-ttu-id="01de1-103">Crea una conexión a un proxy del depurador que se ejecuta en un equipo remoto y devuelve un objeto [ICoreClrDebugTarget](icoreclrdebugtarget-interface.md) que se puede usar para consultar los procesos en ejecución y los tiempos de ejecución cargados en el equipo remoto.</span><span class="sxs-lookup"><span data-stu-id="01de1-103">Creates a connection to a debugger proxy that is running on a remote machine, and returns an [ICoreClrDebugTarget](icoreclrdebugtarget-interface.md) object that can be used to query running processes and loaded runtimes on the remote machine.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01de1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="01de1-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateCoreClrDebugTarget (  
       [in]  DWORD    dwAddress,
       [out] ICoreClrDebugTarget**     ppTarget  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="01de1-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="01de1-105">Parameters</span></span>  
 `dwAddress`  
 <span data-ttu-id="01de1-106">[in] Dirección IPv4 de un equipo de destino remoto.</span><span class="sxs-lookup"><span data-stu-id="01de1-106">[in] IPv4 address of a remote target machine.</span></span>  
  
 `ppTarget`  
 <span data-ttu-id="01de1-107">enuncia Puntero a un puntero a un objeto [ICoreClrDebugTarget](icoreclrdebugtarget-interface.md) que se creará.</span><span class="sxs-lookup"><span data-stu-id="01de1-107">[out] Pointer to a pointer to an [ICoreClrDebugTarget](icoreclrdebugtarget-interface.md) object that will be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="01de1-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="01de1-108">Return Value</span></span>  
 <span data-ttu-id="01de1-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="01de1-109">S_OK</span></span>  
 <span data-ttu-id="01de1-110">Se determinó el número de CLR en el proceso y las matrices de rutas de acceso e identificadores correspondientes se rellenaron correctamente.</span><span class="sxs-lookup"><span data-stu-id="01de1-110">The number of CLRs in the process was successfully determined, and the corresponding handle and path arrays were properly filled.</span></span>  
  
 <span data-ttu-id="01de1-111">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="01de1-111">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="01de1-112">No se puede asignar memoria suficiente para `ppTarget`.</span><span class="sxs-lookup"><span data-stu-id="01de1-112">Unable to allocate enough memory for `ppTarget`.</span></span>  
  
 <span data-ttu-id="01de1-113">E_FAIL (u otros códigos devueltos de E_)</span><span class="sxs-lookup"><span data-stu-id="01de1-113">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="01de1-114">Otros errores.</span><span class="sxs-lookup"><span data-stu-id="01de1-114">Other failures.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="01de1-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="01de1-115">Requirements</span></span>  
 <span data-ttu-id="01de1-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="01de1-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="01de1-117">**Encabezado:** CoreClrRemoteDebuggingInterfaces. h</span><span class="sxs-lookup"><span data-stu-id="01de1-117">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="01de1-118">**Biblioteca:** mscordbi_macx86. dll</span><span class="sxs-lookup"><span data-stu-id="01de1-118">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="01de1-119">**.NET Framework versiones:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="01de1-119">**.NET Framework Versions:** 3.5 SP1</span></span>
