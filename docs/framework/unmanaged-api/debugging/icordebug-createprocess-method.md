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
ms.openlocfilehash: b9ae2b36bff9b4a6c048a8de99fa7d09350b1401
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2020
ms.locfileid: "82859711"
---
# <a name="icordebugcreateprocess-method"></a><span data-ttu-id="b9cc5-102">ICorDebug::CreateProcess (Método)</span><span class="sxs-lookup"><span data-stu-id="b9cc5-102">ICorDebug::CreateProcess Method</span></span>
<span data-ttu-id="b9cc5-103">Inicia un proceso y su subproceso primario bajo el control del depurador.</span><span class="sxs-lookup"><span data-stu-id="b9cc5-103">Launches a process and its primary thread under the control of the debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9cc5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b9cc5-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="b9cc5-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b9cc5-105">Parameters</span></span>  
 `lpApplicationName`  
 <span data-ttu-id="b9cc5-106">de Puntero a una cadena terminada en null que especifica el módulo que va a ser ejecutado por el proceso iniciado.</span><span class="sxs-lookup"><span data-stu-id="b9cc5-106">[in] Pointer to a null-terminated string that specifies the module to be executed by the launched process.</span></span> <span data-ttu-id="b9cc5-107">El módulo se ejecuta en el contexto de seguridad del proceso de llamada.</span><span class="sxs-lookup"><span data-stu-id="b9cc5-107">The module is executed in the security context of the calling process.</span></span>  
  
 `lpCommandLine`  
 <span data-ttu-id="b9cc5-108">de Puntero a una cadena terminada en null que especifica la línea de comandos que va a ejecutar el proceso iniciado.</span><span class="sxs-lookup"><span data-stu-id="b9cc5-108">[in] Pointer to a null-terminated string that specifies the command line to be executed by the launched process.</span></span> <span data-ttu-id="b9cc5-109">El nombre de la aplicación (por ejemplo, "SomeApp. exe") debe ser el primer argumento.</span><span class="sxs-lookup"><span data-stu-id="b9cc5-109">The application name (for example, "SomeApp.exe") must be the first argument.</span></span>  
  
 `lpProcessAttributes`  
 <span data-ttu-id="b9cc5-110">de Puntero a una estructura `SECURITY_ATTRIBUTES` de Win32 que especifica el descriptor de seguridad para el proceso.</span><span class="sxs-lookup"><span data-stu-id="b9cc5-110">[in] Pointer to a Win32 `SECURITY_ATTRIBUTES` structure that specifies the security descriptor for the process.</span></span> <span data-ttu-id="b9cc5-111">Si `lpProcessAttributes` es null, el proceso obtiene un descriptor de seguridad predeterminado.</span><span class="sxs-lookup"><span data-stu-id="b9cc5-111">If `lpProcessAttributes` is null, the process gets a default security descriptor.</span></span>  
  
 `lpThreadAttributes`  
 <span data-ttu-id="b9cc5-112">de Puntero a una estructura `SECURITY_ATTRIBUTES` de Win32 que especifica el descriptor de seguridad para el subproceso principal del proceso.</span><span class="sxs-lookup"><span data-stu-id="b9cc5-112">[in] Pointer to a Win32 `SECURITY_ATTRIBUTES` structure that specifies the security descriptor for the primary thread of the process.</span></span> <span data-ttu-id="b9cc5-113">Si `lpThreadAttributes` es null, el subproceso obtiene un descriptor de seguridad predeterminado.</span><span class="sxs-lookup"><span data-stu-id="b9cc5-113">If `lpThreadAttributes` is null, the thread gets a default security descriptor.</span></span>  
  
 `bInheritHandles`  
 <span data-ttu-id="b9cc5-114">de Se establece `true` en para indicar que el proceso iniciado hereda cada identificador heredable en el proceso de llamada, o `false` para indicar que no se heredan los identificadores.</span><span class="sxs-lookup"><span data-stu-id="b9cc5-114">[in] Set to `true` to indicate that each inheritable handle in the calling process is inherited by the launched process, or `false` to indicate that the handles are not inherited.</span></span> <span data-ttu-id="b9cc5-115">Los identificadores heredados tienen el mismo valor y derechos de acceso que los identificadores originales.</span><span class="sxs-lookup"><span data-stu-id="b9cc5-115">The inherited handles have the same value and access rights as the original handles.</span></span>  
  
 `dwCreationFlags`  
 <span data-ttu-id="b9cc5-116">de Combinación bit a bit de las [marcas de creación de procesos de Win32](/windows/win32/procthread/process-creation-flags) que controlan la clase de prioridad y el comportamiento del proceso iniciado.</span><span class="sxs-lookup"><span data-stu-id="b9cc5-116">[in] A bitwise combination of the [Win32 Process Creation Flags](/windows/win32/procthread/process-creation-flags) that control the priority class and the behavior of the launched process.</span></span>  
  
 `lpEnvironment`  
 <span data-ttu-id="b9cc5-117">de Puntero a un bloque de entorno para el nuevo proceso.</span><span class="sxs-lookup"><span data-stu-id="b9cc5-117">[in] Pointer to an environment block for the new process.</span></span>  
  
 `lpCurrentDirectory`  
 <span data-ttu-id="b9cc5-118">de Puntero a una cadena terminada en null que especifica la ruta de acceso completa al directorio actual para el proceso.</span><span class="sxs-lookup"><span data-stu-id="b9cc5-118">[in] Pointer to a null-terminated string that specifies the full path to the current directory for the process.</span></span> <span data-ttu-id="b9cc5-119">Si este parámetro es null, el nuevo proceso tendrá la misma unidad actual y el mismo directorio que el proceso que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="b9cc5-119">If this parameter is null, the new process will have the same current drive and directory as the calling process.</span></span>  
  
 `lpStartupInfo`  
 <span data-ttu-id="b9cc5-120">de Puntero a una estructura `STARTUPINFOW` de Win32 que especifica la estación de ventana, el escritorio, los identificadores estándar y la apariencia de la ventana principal del proceso iniciado.</span><span class="sxs-lookup"><span data-stu-id="b9cc5-120">[in] Pointer to a Win32 `STARTUPINFOW` structure that specifies the window station, desktop, standard handles, and appearance of the main window for the launched process.</span></span>  
  
 `lpProcessInformation`  
 <span data-ttu-id="b9cc5-121">de Puntero a una estructura `PROCESS_INFORMATION` de Win32 que especifica la información de identificación sobre el proceso que se va a iniciar.</span><span class="sxs-lookup"><span data-stu-id="b9cc5-121">[in] Pointer to a Win32 `PROCESS_INFORMATION` structure that specifies the identification information about the process to be launched.</span></span>  
  
 `debuggingFlags`  
 <span data-ttu-id="b9cc5-122">de Valor de la enumeración Cordebugcreateprocessflags (que especifica las opciones de depuración.</span><span class="sxs-lookup"><span data-stu-id="b9cc5-122">[in] A value of the CorDebugCreateProcessFlags enumeration that specifies the debugging options.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="b9cc5-123">enuncia Puntero a la dirección de un objeto ICorDebugProcess que representa el proceso.</span><span class="sxs-lookup"><span data-stu-id="b9cc5-123">[out] A pointer to the address of a ICorDebugProcess object that represents the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b9cc5-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b9cc5-124">Remarks</span></span>  
 <span data-ttu-id="b9cc5-125">Los parámetros de este método son los mismos que los del método Win32 `CreateProcess` .</span><span class="sxs-lookup"><span data-stu-id="b9cc5-125">The parameters of this method are the same as those of the Win32 `CreateProcess` method.</span></span>  
  
 <span data-ttu-id="b9cc5-126">Para habilitar la depuración en modo mixto no administrada `dwCreationFlags` , establezca en DEBUG_PROCESS &#124; DEBUG_ONLY_THIS_PROCESS.</span><span class="sxs-lookup"><span data-stu-id="b9cc5-126">To enable unmanaged mixed-mode debugging, set `dwCreationFlags` to DEBUG_PROCESS &#124; DEBUG_ONLY_THIS_PROCESS.</span></span> <span data-ttu-id="b9cc5-127">Si solo desea usar la depuración administrada, no establezca estas marcas.</span><span class="sxs-lookup"><span data-stu-id="b9cc5-127">If you want to use only managed debugging, do not set these flags.</span></span>  
  
 <span data-ttu-id="b9cc5-128">Si el depurador y el proceso que se va a depurar (el proceso asociado) comparten una sola consola y se usa la depuración de interoperabilidad, es posible que el proceso asociado mantenga bloqueos de la consola y se detenga en un evento de depuración.</span><span class="sxs-lookup"><span data-stu-id="b9cc5-128">If the debugger and the process to be debugged (the attached process) share a single console, and if interop debugging is used, it is possible for the attached process to hold console locks and stop at a debug event.</span></span> <span data-ttu-id="b9cc5-129">Después, el depurador bloqueará cualquier intento de usar la consola.</span><span class="sxs-lookup"><span data-stu-id="b9cc5-129">The debugger will then block any attempt to use the console.</span></span> <span data-ttu-id="b9cc5-130">Para evitar este problema, establezca la marca de CREATE_NEW_CONSOLE en `dwCreationFlags` el parámetro.</span><span class="sxs-lookup"><span data-stu-id="b9cc5-130">To avoid this problem, set the CREATE_NEW_CONSOLE flag in the `dwCreationFlags` parameter.</span></span>  
  
 <span data-ttu-id="b9cc5-131">No se admite la depuración de interoperabilidad en las plataformas Win9x y no x86, como las plataformas basadas en IA-64 y AMD64.</span><span class="sxs-lookup"><span data-stu-id="b9cc5-131">Interop debugging is not supported on Win9x and non-x86 platforms such as IA-64-based and AMD64-based platforms.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9cc5-132">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b9cc5-132">Requirements</span></span>  
 <span data-ttu-id="b9cc5-133">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b9cc5-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9cc5-134">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b9cc5-134">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b9cc5-135">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b9cc5-135">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b9cc5-136">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9cc5-136">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9cc5-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b9cc5-137">See also</span></span>

- [<span data-ttu-id="b9cc5-138">ICorDebug (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b9cc5-138">ICorDebug Interface</span></span>](icordebug-interface.md)
