---
title: ICLRDataTarget::SetThreadContext (Método)
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.SetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::SetThreadContext
helpviewer_keywords:
- SetThreadContext method, ICLRDataTarget interface [.NET Framework debugging]
- ICLRDataTarget::SetThreadContext method [.NET Framework debugging]
ms.assetid: 103c8502-81fe-40d7-9c1e-9008d8fb19e1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 73697fdd19f2492aabdc0d76e8c1a27c917c85f1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33405543"
---
# <a name="iclrdatatargetsetthreadcontext-method"></a><span data-ttu-id="d7bf8-102">ICLRDataTarget::SetThreadContext (Método)</span><span class="sxs-lookup"><span data-stu-id="d7bf8-102">ICLRDataTarget::SetThreadContext Method</span></span>
<span data-ttu-id="d7bf8-103">Establece el contexto actual del subproceso especificado en el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="d7bf8-103">Sets the current context of the specified thread in the target process.</span></span> <span data-ttu-id="d7bf8-104">Los servicios de acceso a datos de common language runtime (CLR) llama a este método.</span><span class="sxs-lookup"><span data-stu-id="d7bf8-104">This method is called by the common language runtime (CLR) data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7bf8-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d7bf8-105">Syntax</span></span>  
  
```  
HRESULT SetThreadContext (  
    [in] ULONG32            threadID,  
    [in] ULONG32            contextSize,  
    [in, size_is(contextSize)]   
         BYTE               *context  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d7bf8-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d7bf8-106">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="d7bf8-107">[in] El identificador de sistema operativo de un subproceso en el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="d7bf8-107">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="d7bf8-108">[in] El tamaño del contexto.</span><span class="sxs-lookup"><span data-stu-id="d7bf8-108">[in] The size of the context.</span></span>  
  
 `context`  
 <span data-ttu-id="d7bf8-109">[in] Puntero a un búfer que contiene el contexto.</span><span class="sxs-lookup"><span data-stu-id="d7bf8-109">[in] Pointer to a buffer containing the context.</span></span>  
  
 <span data-ttu-id="d7bf8-110">Los datos de la `context` búfer estará en el formato de Win32 `CONTEXT` estructura.</span><span class="sxs-lookup"><span data-stu-id="d7bf8-110">The data in the `context` buffer will be in the format of the Win32 `CONTEXT` structure.</span></span> <span data-ttu-id="d7bf8-111">El contexto especifica los datos de registro específica del procesador, por lo que la definición de Win32 `CONTEXT` estructura depende de la arquitectura del procesador.</span><span class="sxs-lookup"><span data-stu-id="d7bf8-111">The context specifies processor-specific register data, so the definition of the Win32 `CONTEXT` structure depends on the processor's architecture.</span></span> <span data-ttu-id="d7bf8-112">Consulte el archivo de encabezado WinNT.h para la definición de Win32 `CONTEXT` estructura.</span><span class="sxs-lookup"><span data-stu-id="d7bf8-112">Refer to the WinNT.h header file for the definition of the Win32 `CONTEXT` structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d7bf8-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d7bf8-113">Remarks</span></span>  
 <span data-ttu-id="d7bf8-114">Este método lo implementa el escritor de la aplicación de depuración.</span><span class="sxs-lookup"><span data-stu-id="d7bf8-114">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7bf8-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d7bf8-115">Requirements</span></span>  
 <span data-ttu-id="d7bf8-116">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d7bf8-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7bf8-117">**Encabezado:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="d7bf8-117">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="d7bf8-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d7bf8-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d7bf8-119">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7bf8-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7bf8-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="d7bf8-120">See Also</span></span>  
 [<span data-ttu-id="d7bf8-121">ICLRDataTarget (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d7bf8-121">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
