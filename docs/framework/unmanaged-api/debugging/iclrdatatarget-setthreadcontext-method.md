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
ms.openlocfilehash: d76a907434b12b85aaedeef169390ec6f0df724a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179127"
---
# <a name="iclrdatatargetsetthreadcontext-method"></a><span data-ttu-id="7ac0f-102">ICLRDataTarget::SetThreadContext (Método)</span><span class="sxs-lookup"><span data-stu-id="7ac0f-102">ICLRDataTarget::SetThreadContext Method</span></span>
<span data-ttu-id="7ac0f-103">Establece el contexto actual del subproceso especificado en el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="7ac0f-103">Sets the current context of the specified thread in the target process.</span></span> <span data-ttu-id="7ac0f-104">Los servicios de acceso a datos de Common Language Runtime (CLR) llaman a este método.</span><span class="sxs-lookup"><span data-stu-id="7ac0f-104">This method is called by the common language runtime (CLR) data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ac0f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7ac0f-105">Syntax</span></span>  
  
```cpp  
HRESULT SetThreadContext (  
    [in] ULONG32            threadID,  
    [in] ULONG32            contextSize,  
    [in, size_is(contextSize)]
         BYTE               *context  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7ac0f-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7ac0f-106">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="7ac0f-107">[en] Identificador del sistema operativo de un subproceso en el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="7ac0f-107">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="7ac0f-108">[en] El tamaño del contexto.</span><span class="sxs-lookup"><span data-stu-id="7ac0f-108">[in] The size of the context.</span></span>  
  
 `context`  
 <span data-ttu-id="7ac0f-109">[en] Puntero a un búfer que contiene el contexto.</span><span class="sxs-lookup"><span data-stu-id="7ac0f-109">[in] Pointer to a buffer containing the context.</span></span>  
  
 <span data-ttu-id="7ac0f-110">Los datos `context` del búfer tendrán el formato `CONTEXT` de la estructura Win32.</span><span class="sxs-lookup"><span data-stu-id="7ac0f-110">The data in the `context` buffer will be in the format of the Win32 `CONTEXT` structure.</span></span> <span data-ttu-id="7ac0f-111">El contexto especifica datos de registro específicos del procesador, por lo que la definición de la estructura Win32 `CONTEXT` depende de la arquitectura del procesador.</span><span class="sxs-lookup"><span data-stu-id="7ac0f-111">The context specifies processor-specific register data, so the definition of the Win32 `CONTEXT` structure depends on the processor's architecture.</span></span> <span data-ttu-id="7ac0f-112">Consulte el archivo de encabezado WinNT.h para `CONTEXT` obtener la definición de la estructura Win32.</span><span class="sxs-lookup"><span data-stu-id="7ac0f-112">Refer to the WinNT.h header file for the definition of the Win32 `CONTEXT` structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7ac0f-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="7ac0f-113">Remarks</span></span>  
 <span data-ttu-id="7ac0f-114">Este método lo implementa el escritor de la aplicación de depuración.</span><span class="sxs-lookup"><span data-stu-id="7ac0f-114">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ac0f-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7ac0f-115">Requirements</span></span>  
 <span data-ttu-id="7ac0f-116">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7ac0f-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ac0f-117">**Encabezado:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="7ac0f-117">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="7ac0f-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7ac0f-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7ac0f-119">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ac0f-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ac0f-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7ac0f-120">See also</span></span>

- [<span data-ttu-id="7ac0f-121">ICLRDataTarget (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7ac0f-121">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
