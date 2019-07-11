---
title: ICorDebug::CreateProcess (Método)
ms.date: 03/30/2017
api_name:
- ICorDebug.CreateProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::CreateProcess
helpviewer_keywords:
- ICorDebug::CreateProcess method [.NET Framework debugging]
- CreateProcess method, ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: b6128694-11ed-46e7-bd4e-49ea1914c46a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5d6220270634dd8e2d15787d717020b8f6f86bb9
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67738326"
---
# <a name="icordebugcreateprocess-method"></a><span data-ttu-id="e9056-102">ICorDebug::CreateProcess (Método)</span><span class="sxs-lookup"><span data-stu-id="e9056-102">ICorDebug::CreateProcess Method</span></span>
<span data-ttu-id="e9056-103">Inicia un proceso y su subproceso principal bajo el control del depurador.</span><span class="sxs-lookup"><span data-stu-id="e9056-103">Launches a process and its primary thread under the control of the debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9056-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e9056-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateProcess (  
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
    [out] ICorDebugProcess            **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e9056-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e9056-105">Parameters</span></span>  
 `lpApplicationName`  
 <span data-ttu-id="e9056-106">[in] Puntero a una cadena terminada en null que especifica el módulo que va a ejecutar el proceso iniciado.</span><span class="sxs-lookup"><span data-stu-id="e9056-106">[in] Pointer to a null-terminated string that specifies the module to be executed by the launched process.</span></span> <span data-ttu-id="e9056-107">El módulo se ejecuta en el contexto de seguridad del proceso que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="e9056-107">The module is executed in the security context of the calling process.</span></span>  
  
 `lpCommandLine`  
 <span data-ttu-id="e9056-108">[in] Puntero a una cadena terminada en null que especifica la línea de comandos que va a ejecutar el proceso iniciado.</span><span class="sxs-lookup"><span data-stu-id="e9056-108">[in] Pointer to a null-terminated string that specifies the command line to be executed by the launched process.</span></span> <span data-ttu-id="e9056-109">El nombre de la aplicación (por ejemplo, "SomeApp.exe") debe ser el primer argumento.</span><span class="sxs-lookup"><span data-stu-id="e9056-109">The application name (for example, "SomeApp.exe") must be the first argument.</span></span>  
  
 `lpProcessAttributes`  
 <span data-ttu-id="e9056-110">[in] Puntero a un Win32 `SECURITY_ATTRIBUTES` estructura que especifica el descriptor de seguridad para el proceso.</span><span class="sxs-lookup"><span data-stu-id="e9056-110">[in] Pointer to a Win32 `SECURITY_ATTRIBUTES` structure that specifies the security descriptor for the process.</span></span> <span data-ttu-id="e9056-111">Si `lpProcessAttributes` es null, el proceso obtiene un descriptor de seguridad predeterminado.</span><span class="sxs-lookup"><span data-stu-id="e9056-111">If `lpProcessAttributes` is null, the process gets a default security descriptor.</span></span>  
  
 `lpThreadAttributes`  
 <span data-ttu-id="e9056-112">[in] Puntero a un Win32 `SECURITY_ATTRIBUTES` estructura que especifica el descriptor de seguridad para el subproceso principal del proceso.</span><span class="sxs-lookup"><span data-stu-id="e9056-112">[in] Pointer to a Win32 `SECURITY_ATTRIBUTES` structure that specifies the security descriptor for the primary thread of the process.</span></span> <span data-ttu-id="e9056-113">Si `lpThreadAttributes` es null, el subproceso obtiene un descriptor de seguridad predeterminado.</span><span class="sxs-lookup"><span data-stu-id="e9056-113">If `lpThreadAttributes` is null, the thread gets a default security descriptor.</span></span>  
  
 `bInheritHandles`  
 <span data-ttu-id="e9056-114">[in] Establecido en `true` para indicar que el proceso iniciado, heredan todos los identificadores heredables en el proceso de llamada o `false` para indicar que no se heredan los identificadores.</span><span class="sxs-lookup"><span data-stu-id="e9056-114">[in] Set to `true` to indicate that each inheritable handle in the calling process is inherited by the launched process, or `false` to indicate that the handles are not inherited.</span></span> <span data-ttu-id="e9056-115">Los identificadores heredados tienen los mismos derechos de acceso y el valor que los identificadores originales.</span><span class="sxs-lookup"><span data-stu-id="e9056-115">The inherited handles have the same value and access rights as the original handles.</span></span>  
  
 `dwCreationFlags`  
 <span data-ttu-id="e9056-116">[in] Una combinación bit a bit de los [marcas de creación de proceso Win32](https://go.microsoft.com/fwlink/?linkid=69981) que controlan la clase de prioridad y el comportamiento del proceso iniciado.</span><span class="sxs-lookup"><span data-stu-id="e9056-116">[in] A bitwise combination of the [Win32 Process Creation Flags](https://go.microsoft.com/fwlink/?linkid=69981) that control the priority class and the behavior of the launched process.</span></span>  
  
 `lpEnvironment`  
 <span data-ttu-id="e9056-117">[in] Puntero a un bloque de entorno para el nuevo proceso.</span><span class="sxs-lookup"><span data-stu-id="e9056-117">[in] Pointer to an environment block for the new process.</span></span>  
  
 `lpCurrentDirectory`  
 <span data-ttu-id="e9056-118">[in] Puntero a una cadena terminada en null que especifica la ruta de acceso completa al directorio actual para el proceso.</span><span class="sxs-lookup"><span data-stu-id="e9056-118">[in] Pointer to a null-terminated string that specifies the full path to the current directory for the process.</span></span> <span data-ttu-id="e9056-119">Si este parámetro es null, el nuevo proceso tendrá la misma unidad actual y el directorio que el proceso que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="e9056-119">If this parameter is null, the new process will have the same current drive and directory as the calling process.</span></span>  
  
 `lpStartupInfo`  
 <span data-ttu-id="e9056-120">[in] Puntero a un Win32 `STARTUPINFOW` estructura que especifica la estación de ventana, escritorio, los identificadores estándar y apariencia de la ventana principal para el proceso iniciado.</span><span class="sxs-lookup"><span data-stu-id="e9056-120">[in] Pointer to a Win32 `STARTUPINFOW` structure that specifies the window station, desktop, standard handles, and appearance of the main window for the launched process.</span></span>  
  
 `lpProcessInformation`  
 <span data-ttu-id="e9056-121">[in] Puntero a un Win32 `PROCESS_INFORMATION` estructura que especifica la información de identificación sobre el proceso que se inicie.</span><span class="sxs-lookup"><span data-stu-id="e9056-121">[in] Pointer to a Win32 `PROCESS_INFORMATION` structure that specifies the identification information about the process to be launched.</span></span>  
  
 `debuggingFlags`  
 <span data-ttu-id="e9056-122">[in] Un valor de la enumeración CorDebugCreateProcessFlags que especifica las opciones de depuración.</span><span class="sxs-lookup"><span data-stu-id="e9056-122">[in] A value of the CorDebugCreateProcessFlags enumeration that specifies the debugging options.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="e9056-123">[out] Un puntero a la dirección de un objeto ICorDebugProcess que representa el proceso.</span><span class="sxs-lookup"><span data-stu-id="e9056-123">[out] A pointer to the address of a ICorDebugProcess object that represents the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e9056-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e9056-124">Remarks</span></span>  
 <span data-ttu-id="e9056-125">Los parámetros de este método son los mismos que los de Win32 `CreateProcess` método.</span><span class="sxs-lookup"><span data-stu-id="e9056-125">The parameters of this method are the same as those of the Win32 `CreateProcess` method.</span></span>  
  
 <span data-ttu-id="e9056-126">Para habilitar la depuración en modo mixto no administrado, establezca `dwCreationFlags` a DEBUG_PROCESS &#124; DEBUG_ONLY_THIS_PROCESS.</span><span class="sxs-lookup"><span data-stu-id="e9056-126">To enable unmanaged mixed-mode debugging, set `dwCreationFlags` to DEBUG_PROCESS &#124; DEBUG_ONLY_THIS_PROCESS.</span></span> <span data-ttu-id="e9056-127">Si desea usar la depuración sólo administrada, no establezca estos indicadores.</span><span class="sxs-lookup"><span data-stu-id="e9056-127">If you want to use only managed debugging, do not set these flags.</span></span>  
  
 <span data-ttu-id="e9056-128">Si el depurador y el proceso de ser depurando (el proceso asociado) comparten una única consola y, si se usa la depuración de interoperabilidad, es posible que el proceso asociado contener los bloqueos de la consola y detenerse en un evento de depuración.</span><span class="sxs-lookup"><span data-stu-id="e9056-128">If the debugger and the process to be debugged (the attached process) share a single console, and if interop debugging is used, it is possible for the attached process to hold console locks and stop at a debug event.</span></span> <span data-ttu-id="e9056-129">El depurador, a continuación, bloqueará cualquier intento de utilizar la consola.</span><span class="sxs-lookup"><span data-stu-id="e9056-129">The debugger will then block any attempt to use the console.</span></span> <span data-ttu-id="e9056-130">Para evitar este problema, establezca el marcador CREATE_NEW_CONSOLE el `dwCreationFlags` parámetro.</span><span class="sxs-lookup"><span data-stu-id="e9056-130">To avoid this problem, set the CREATE_NEW_CONSOLE flag in the `dwCreationFlags` parameter.</span></span>  
  
 <span data-ttu-id="e9056-131">No se admite la depuración de interoperabilidad en plataformas Win9x y no x86 como las plataformas basadas en IA-64 y basado en AMD64.</span><span class="sxs-lookup"><span data-stu-id="e9056-131">Interop debugging is not supported on Win9x and non-x86 platforms such as IA-64-based and AMD64-based platforms.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9056-132">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e9056-132">Requirements</span></span>  
 <span data-ttu-id="e9056-133">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e9056-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9056-134">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e9056-134">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e9056-135">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e9056-135">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e9056-136">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9056-136">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9056-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="e9056-137">See also</span></span>

- [<span data-ttu-id="e9056-138">ICorDebug (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e9056-138">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
