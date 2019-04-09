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
ms.openlocfilehash: d3f98ab65512a380ebd4dc0ecd50e36f94a6d6b5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59104161"
---
# <a name="iclrdatatargetsetthreadcontext-method"></a><span data-ttu-id="2bf20-102">ICLRDataTarget::SetThreadContext (Método)</span><span class="sxs-lookup"><span data-stu-id="2bf20-102">ICLRDataTarget::SetThreadContext Method</span></span>
<span data-ttu-id="2bf20-103">Establece el contexto actual del subproceso especificado en el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="2bf20-103">Sets the current context of the specified thread in the target process.</span></span> <span data-ttu-id="2bf20-104">Este método llama a los servicios de acceso de datos de common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="2bf20-104">This method is called by the common language runtime (CLR) data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2bf20-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2bf20-105">Syntax</span></span>  
  
```  
HRESULT SetThreadContext (  
    [in] ULONG32            threadID,  
    [in] ULONG32            contextSize,  
    [in, size_is(contextSize)]   
         BYTE               *context  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2bf20-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2bf20-106">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="2bf20-107">[in] El identificador del sistema operativo de un subproceso del proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="2bf20-107">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="2bf20-108">[in] El tamaño del contexto.</span><span class="sxs-lookup"><span data-stu-id="2bf20-108">[in] The size of the context.</span></span>  
  
 `context`  
 <span data-ttu-id="2bf20-109">[in] Puntero a un búfer que contiene el contexto.</span><span class="sxs-lookup"><span data-stu-id="2bf20-109">[in] Pointer to a buffer containing the context.</span></span>  
  
 <span data-ttu-id="2bf20-110">Los datos en el `context` búfer estará en el formato de Win32 `CONTEXT` estructura.</span><span class="sxs-lookup"><span data-stu-id="2bf20-110">The data in the `context` buffer will be in the format of the Win32 `CONTEXT` structure.</span></span> <span data-ttu-id="2bf20-111">El contexto especifica los datos de registro específicas del procesador, por lo que la definición de Win32 `CONTEXT` estructura depende de la arquitectura del procesador.</span><span class="sxs-lookup"><span data-stu-id="2bf20-111">The context specifies processor-specific register data, so the definition of the Win32 `CONTEXT` structure depends on the processor's architecture.</span></span> <span data-ttu-id="2bf20-112">Consulte el archivo de encabezado WinNT.h para la definición de Win32 `CONTEXT` estructura.</span><span class="sxs-lookup"><span data-stu-id="2bf20-112">Refer to the WinNT.h header file for the definition of the Win32 `CONTEXT` structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2bf20-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2bf20-113">Remarks</span></span>  
 <span data-ttu-id="2bf20-114">Este método lo implementa el escritor de la aplicación de depuración.</span><span class="sxs-lookup"><span data-stu-id="2bf20-114">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2bf20-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2bf20-115">Requirements</span></span>  
 <span data-ttu-id="2bf20-116">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2bf20-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2bf20-117">**Encabezado**: ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="2bf20-117">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="2bf20-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2bf20-118">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="2bf20-119">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="2bf20-119">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2bf20-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="2bf20-120">See also</span></span>

- [<span data-ttu-id="2bf20-121">ICLRDataTarget (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2bf20-121">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
