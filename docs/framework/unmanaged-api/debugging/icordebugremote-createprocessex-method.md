---
description: 'Más información sobre: ICorDebugRemote:: Createprocessex ((método)'
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
ms.openlocfilehash: cd27400f5c9f348621fb66b3b7730cf15d397151
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794733"
---
# <a name="icordebugremotecreateprocessex-method"></a><span data-ttu-id="a2dca-103">ICorDebugRemote::CreateProcessEx (Método)</span><span class="sxs-lookup"><span data-stu-id="a2dca-103">ICorDebugRemote::CreateProcessEx Method</span></span>

<span data-ttu-id="a2dca-104">Inicia un proceso en un equipo remoto en el depurador.</span><span class="sxs-lookup"><span data-stu-id="a2dca-104">Launches a process on a remote machine under the debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2dca-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a2dca-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="a2dca-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a2dca-106">Parameters</span></span>  

 `pRemoteTarget`  
 <span data-ttu-id="a2dca-107">de Puntero a una [interfaz ICorDebugRemoteTarget](icordebugremotetarget-interface.md).</span><span class="sxs-lookup"><span data-stu-id="a2dca-107">[in] Pointer to an [ICorDebugRemoteTarget Interface](icordebugremotetarget-interface.md).</span></span> <span data-ttu-id="a2dca-108">Se utiliza para determinar el equipo remoto en el que se va a iniciar el proceso.</span><span class="sxs-lookup"><span data-stu-id="a2dca-108">Used to determine the remote machine on which the process will be launched.</span></span>  
  
 `lpApplicationName`  
 <span data-ttu-id="a2dca-109">de Puntero a una cadena terminada en null que especifica el módulo que va a ser ejecutado por el proceso iniciado.</span><span class="sxs-lookup"><span data-stu-id="a2dca-109">[in] Pointer to a null-terminated string that specifies the module to be executed by the launched process.</span></span> <span data-ttu-id="a2dca-110">El módulo se ejecuta en el contexto de seguridad del proceso de llamada.</span><span class="sxs-lookup"><span data-stu-id="a2dca-110">The module is executed in the security context of the calling process.</span></span>  
  
 `lpCommandLine`  
 <span data-ttu-id="a2dca-111">de Puntero a una cadena terminada en null que especifica la línea de comandos que va a ejecutar el proceso iniciado.</span><span class="sxs-lookup"><span data-stu-id="a2dca-111">[in] Pointer to a null-terminated string that specifies the command line to be executed by the launched process.</span></span>  
  
 `lpProcessAttributes`  
 <span data-ttu-id="a2dca-112">de No se usa para la depuración remota.</span><span class="sxs-lookup"><span data-stu-id="a2dca-112">[in] Unused for remote debugging.</span></span>  
  
 `lpThreadAttributes`  
 <span data-ttu-id="a2dca-113">de No se usa para la depuración remota.</span><span class="sxs-lookup"><span data-stu-id="a2dca-113">[in] Unused for remote debugging.</span></span>  
  
 `bInheritHandles`  
 <span data-ttu-id="a2dca-114">de No se usa para la depuración remota.</span><span class="sxs-lookup"><span data-stu-id="a2dca-114">[in] Unused for remote debugging.</span></span>  
  
 `dwCreationFlags`  
 <span data-ttu-id="a2dca-115">de No se usa para la depuración remota.</span><span class="sxs-lookup"><span data-stu-id="a2dca-115">[in] Unused for remote debugging.</span></span>  
  
 `lpEnvironment`  
 <span data-ttu-id="a2dca-116">de Puntero a un bloque de entorno para el nuevo proceso.</span><span class="sxs-lookup"><span data-stu-id="a2dca-116">[in] Pointer to an environment block for the new process.</span></span>  
  
 `lpCurrentDirectory`  
 <span data-ttu-id="a2dca-117">de Puntero a una cadena terminada en null que especifica la ruta de acceso completa al directorio actual para el proceso.</span><span class="sxs-lookup"><span data-stu-id="a2dca-117">[in] Pointer to a null-terminated string that specifies the full path to the current directory for the process.</span></span> <span data-ttu-id="a2dca-118">Si este parámetro es null, el nuevo proceso tendrá la misma unidad actual y el mismo directorio que el proceso que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="a2dca-118">If this parameter is null, the new process will have the same current drive and directory as the calling process.</span></span>  
  
 `lpStartupInfo`  
 <span data-ttu-id="a2dca-119">de No se usa para la depuración remota.</span><span class="sxs-lookup"><span data-stu-id="a2dca-119">[in] Unused for remote debugging.</span></span>  
  
 `lpProcessInformation`  
 <span data-ttu-id="a2dca-120">de No se usa para la depuración remota.</span><span class="sxs-lookup"><span data-stu-id="a2dca-120">[in] Unused for remote debugging.</span></span>  
  
 `debuggingFlags`  
 <span data-ttu-id="a2dca-121">de No se usa para la depuración remota.</span><span class="sxs-lookup"><span data-stu-id="a2dca-121">[in] Unused for remote debugging.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="a2dca-122">enuncia Puntero a la dirección de un objeto "ICorDebugProcess interface" que representa el proceso.</span><span class="sxs-lookup"><span data-stu-id="a2dca-122">[out] A pointer to the address of a"ICorDebugProcess Interface" object that represents the process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a2dca-123">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a2dca-123">Return Value</span></span>  

 <span data-ttu-id="a2dca-124">S_OK</span><span class="sxs-lookup"><span data-stu-id="a2dca-124">S_OK</span></span>  
 <span data-ttu-id="a2dca-125">Inició correctamente el proceso en el equipo remoto y devolvió una "ICorDebugProcess interface" para la depuración.</span><span class="sxs-lookup"><span data-stu-id="a2dca-125">Successfully launched the process on the remote machine and returned an "ICorDebugProcess Interface" for debugging.</span></span>  
  
 <span data-ttu-id="a2dca-126">E_FAIL (u otros códigos devueltos de E_)</span><span class="sxs-lookup"><span data-stu-id="a2dca-126">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="a2dca-127">No se puede iniciar el proceso en el equipo remoto y devolver una "ICorDebugProcess interface" para la depuración.</span><span class="sxs-lookup"><span data-stu-id="a2dca-127">Unable to launch the process on the remote machine and return an "ICorDebugProcess Interface" for debugging.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a2dca-128">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a2dca-128">Remarks</span></span>  

 <span data-ttu-id="a2dca-129">En Silverlight no se admite la depuración en modo mixto.</span><span class="sxs-lookup"><span data-stu-id="a2dca-129">Mixed-mode debugging is not supported in Silverlight.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a2dca-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a2dca-130">Requirements</span></span>  

 <span data-ttu-id="a2dca-131">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a2dca-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a2dca-132">**Encabezado:** Cordebug. idl</span><span class="sxs-lookup"><span data-stu-id="a2dca-132">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="a2dca-133">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a2dca-133">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a2dca-134">**.NET Framework versiones:** 4,5, 4, 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="a2dca-134">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2dca-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="a2dca-135">See also</span></span>

- [<span data-ttu-id="a2dca-136">ICorDebugRemote (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a2dca-136">ICorDebugRemote Interface</span></span>](icordebugremote-interface.md)
- [<span data-ttu-id="a2dca-137">ICorDebug (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a2dca-137">ICorDebug Interface</span></span>](icordebug-interface.md)

- [<span data-ttu-id="a2dca-138">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="a2dca-138">Debugging Interfaces</span></span>](debugging-interfaces.md)
