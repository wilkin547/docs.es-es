---
title: ICorDebugRemote::CreateProcessEx (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugRemote.CreateProcessEx
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugRemoteTarget::CreateProcessEx
helpviewer_keywords:
- CreateProcessEx method, ICorDebugRemote interface [.NET Framework debugging]
- ICorDebugRemote::CreateProcessEx method [.NET Framework debugging]
ms.assetid: 41af93c7-e448-4251-8d4d-413d38c635f2
topic_type:
- apiref
ms.openlocfilehash: 9e1a5ba65da09c90f33e5e8108c3bd91f3aee4a1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131296"
---
# <a name="icordebugremotecreateprocessex-method"></a><span data-ttu-id="f0342-102">ICorDebugRemote::CreateProcessEx (Método)</span><span class="sxs-lookup"><span data-stu-id="f0342-102">ICorDebugRemote::CreateProcessEx Method</span></span>
<span data-ttu-id="f0342-103">Inicia un proceso en un equipo remoto en el depurador.</span><span class="sxs-lookup"><span data-stu-id="f0342-103">Launches a process on a remote machine under the debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0342-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f0342-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateProcessEx (  
    [in]  ICorDebugRemoteTarget*      pRemoteTarget,  
    [in]  LPCWSTR                     lpApplicationName,  
    [in]  LPWSTR                      lpCommandLine,  
    [in]  LPSECURITY_ATTRIBUTES       lpProcessAttributes,  
    [in]  LPSECURITY_ATTRIBUTES       lpThreadAttributes,  
    [in]  BOOL                        bInheritHandles,  
    [in]  DWORD                       dwCreationFlags,  
    [in]  PVOID                       lpEnvironment,  
    [in]  LPCWSTR                     lpCurrentDirectory,  
    [in]  LPSTARTUPINFOW              lpStartupInfo,  
    [in]  LPPROCESS_INFORMATION       lpProcessInformation,  
    [in]  CorDebugCreateProcessFlags  debuggingFlags,  
    [out] ICorDebugProcess**          ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f0342-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f0342-105">Parameters</span></span>  
 `pRemoteTarget`  
 <span data-ttu-id="f0342-106">de Puntero a una [interfaz ICorDebugRemoteTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md).</span><span class="sxs-lookup"><span data-stu-id="f0342-106">[in] Pointer to an [ICorDebugRemoteTarget Interface](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md).</span></span> <span data-ttu-id="f0342-107">Se utiliza para determinar el equipo remoto en el que se va a iniciar el proceso.</span><span class="sxs-lookup"><span data-stu-id="f0342-107">Used to determine the remote machine on which the process will be launched.</span></span>  
  
 `lpApplicationName`  
 <span data-ttu-id="f0342-108">de Puntero a una cadena terminada en null que especifica el módulo que va a ser ejecutado por el proceso iniciado.</span><span class="sxs-lookup"><span data-stu-id="f0342-108">[in] Pointer to a null-terminated string that specifies the module to be executed by the launched process.</span></span> <span data-ttu-id="f0342-109">El módulo se ejecuta en el contexto de seguridad del proceso de llamada.</span><span class="sxs-lookup"><span data-stu-id="f0342-109">The module is executed in the security context of the calling process.</span></span>  
  
 `lpCommandLine`  
 <span data-ttu-id="f0342-110">de Puntero a una cadena terminada en null que especifica la línea de comandos que va a ejecutar el proceso iniciado.</span><span class="sxs-lookup"><span data-stu-id="f0342-110">[in] Pointer to a null-terminated string that specifies the command line to be executed by the launched process.</span></span>  
  
 `lpProcessAttributes`  
 <span data-ttu-id="f0342-111">de No se usa para la depuración remota.</span><span class="sxs-lookup"><span data-stu-id="f0342-111">[in] Unused for remote debugging.</span></span>  
  
 `lpThreadAttributes`  
 <span data-ttu-id="f0342-112">de No se usa para la depuración remota.</span><span class="sxs-lookup"><span data-stu-id="f0342-112">[in] Unused for remote debugging.</span></span>  
  
 `bInheritHandles`  
 <span data-ttu-id="f0342-113">de No se usa para la depuración remota.</span><span class="sxs-lookup"><span data-stu-id="f0342-113">[in] Unused for remote debugging.</span></span>  
  
 `dwCreationFlags`  
 <span data-ttu-id="f0342-114">de No se usa para la depuración remota.</span><span class="sxs-lookup"><span data-stu-id="f0342-114">[in] Unused for remote debugging.</span></span>  
  
 `lpEnvironment`  
 <span data-ttu-id="f0342-115">de Puntero a un bloque de entorno para el nuevo proceso.</span><span class="sxs-lookup"><span data-stu-id="f0342-115">[in] Pointer to an environment block for the new process.</span></span>  
  
 `lpCurrentDirectory`  
 <span data-ttu-id="f0342-116">de Puntero a una cadena terminada en null que especifica la ruta de acceso completa al directorio actual para el proceso.</span><span class="sxs-lookup"><span data-stu-id="f0342-116">[in] Pointer to a null-terminated string that specifies the full path to the current directory for the process.</span></span> <span data-ttu-id="f0342-117">Si este parámetro es null, el nuevo proceso tendrá la misma unidad actual y el mismo directorio que el proceso que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="f0342-117">If this parameter is null, the new process will have the same current drive and directory as the calling process.</span></span>  
  
 `lpStartupInfo`  
 <span data-ttu-id="f0342-118">de No se usa para la depuración remota.</span><span class="sxs-lookup"><span data-stu-id="f0342-118">[in] Unused for remote debugging.</span></span>  
  
 `lpProcessInformation`  
 <span data-ttu-id="f0342-119">de No se usa para la depuración remota.</span><span class="sxs-lookup"><span data-stu-id="f0342-119">[in] Unused for remote debugging.</span></span>  
  
 `debuggingFlags`  
 <span data-ttu-id="f0342-120">de No se usa para la depuración remota.</span><span class="sxs-lookup"><span data-stu-id="f0342-120">[in] Unused for remote debugging.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="f0342-121">enuncia Puntero a la dirección de un objeto "ICorDebugProcess interface" que representa el proceso.</span><span class="sxs-lookup"><span data-stu-id="f0342-121">[out] A pointer to the address of a"ICorDebugProcess Interface" object that represents the process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f0342-122">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f0342-122">Return Value</span></span>  
 <span data-ttu-id="f0342-123">S_OK</span><span class="sxs-lookup"><span data-stu-id="f0342-123">S_OK</span></span>  
 <span data-ttu-id="f0342-124">Inició correctamente el proceso en el equipo remoto y devolvió una "ICorDebugProcess interface" para la depuración.</span><span class="sxs-lookup"><span data-stu-id="f0342-124">Successfully launched the process on the remote machine and returned an "ICorDebugProcess Interface" for debugging.</span></span>  
  
 <span data-ttu-id="f0342-125">E_FAIL (u otros códigos devueltos de E_)</span><span class="sxs-lookup"><span data-stu-id="f0342-125">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="f0342-126">No se puede iniciar el proceso en el equipo remoto y devolver una "ICorDebugProcess interface" para la depuración.</span><span class="sxs-lookup"><span data-stu-id="f0342-126">Unable to launch the process on the remote machine and return an "ICorDebugProcess Interface" for debugging.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f0342-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f0342-127">Remarks</span></span>  
 <span data-ttu-id="f0342-128">En Silverlight no se admite la depuración en modo mixto.</span><span class="sxs-lookup"><span data-stu-id="f0342-128">Mixed-mode debugging is not supported in Silverlight.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0342-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f0342-129">Requirements</span></span>  
 <span data-ttu-id="f0342-130">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f0342-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0342-131">**Encabezado:** Cordebug. idl</span><span class="sxs-lookup"><span data-stu-id="f0342-131">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="f0342-132">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f0342-132">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f0342-133">**.NET Framework versiones:** 4,5, 4, 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="f0342-133">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0342-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="f0342-134">See also</span></span>

- [<span data-ttu-id="f0342-135">ICorDebugRemote (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f0342-135">ICorDebugRemote Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremote-interface.md)
- [<span data-ttu-id="f0342-136">ICorDebug (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f0342-136">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)

- [<span data-ttu-id="f0342-137">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="f0342-137">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
