---
title: ICLRDataTarget::GetThreadContext (Método)
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.GetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::GetThreadContext
helpviewer_keywords:
- ICLRDataTarget::GetThreadContext method [.NET Framework debugging]
- GetThreadContext method, ICLRDataTarget interface [.NET Framework debugging]
ms.assetid: b9d8c3b5-3a2e-4225-95d4-dd052c4532c3
topic_type:
- apiref
ms.openlocfilehash: b5f6a830cbe601443f03cd91a356c7e49450e7f3
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793730"
---
# <a name="iclrdatatargetgetthreadcontext-method"></a><span data-ttu-id="6080e-102">ICLRDataTarget::GetThreadContext (Método)</span><span class="sxs-lookup"><span data-stu-id="6080e-102">ICLRDataTarget::GetThreadContext Method</span></span>
<span data-ttu-id="6080e-103">Obtiene el contexto de ejecución actual para el subproceso dado en el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="6080e-103">Gets the current execution context for the given thread in the target process.</span></span> <span data-ttu-id="6080e-104">El servicio de acceso a datos de Common Language Runtime llama a este método.</span><span class="sxs-lookup"><span data-stu-id="6080e-104">This method is called by the common language runtime data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6080e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6080e-105">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadContext (  
    [in] ULONG32            threadID,  
    [in] ULONG32            contextFlags,  
    [in] ULONG32            contextSize,  
    [out, size_is(contextSize)]   
        BYTE                *context  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6080e-106">Parameters</span><span class="sxs-lookup"><span data-stu-id="6080e-106">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="6080e-107">de Identificador del sistema operativo de un subproceso en el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="6080e-107">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `contextFlags`  
 <span data-ttu-id="6080e-108">de Marcas que especifican qué partes del contexto se van a devolver.</span><span class="sxs-lookup"><span data-stu-id="6080e-108">[in] Flags that specify which parts of the context to return.</span></span> <span data-ttu-id="6080e-109">La implementación devolverá al menos estas partes del contexto.</span><span class="sxs-lookup"><span data-stu-id="6080e-109">The implementation will return at least these parts of the context.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="6080e-110">de Tamaño del contexto.</span><span class="sxs-lookup"><span data-stu-id="6080e-110">[in] The size of the context.</span></span>  
  
 `context`  
 <span data-ttu-id="6080e-111">enuncia Puntero a un búfer en el que se va a colocar el contexto.</span><span class="sxs-lookup"><span data-stu-id="6080e-111">[out] Pointer to a buffer in which to place the context.</span></span>  
  
 <span data-ttu-id="6080e-112">Los datos del búfer de `context` deben tener el formato de la estructura de `CONTEXT` de Win32.</span><span class="sxs-lookup"><span data-stu-id="6080e-112">The data in the `context` buffer must be in the format of the Win32 `CONTEXT` structure.</span></span> <span data-ttu-id="6080e-113">El contexto especifica datos de registro específicos del procesador, por lo que la definición de la estructura de `CONTEXT` de Win32 depende de la arquitectura del procesador.</span><span class="sxs-lookup"><span data-stu-id="6080e-113">The context specifies processor-specific register data, so the definition of the Win32 `CONTEXT` structure depends on the processor's architecture.</span></span> <span data-ttu-id="6080e-114">Consulte el archivo de encabezado Winnt. h para ver la definición de la estructura de `CONTEXT` de Win32.</span><span class="sxs-lookup"><span data-stu-id="6080e-114">Refer to the WinNT.h header file for the definition of the Win32 `CONTEXT` structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6080e-115">Notas</span><span class="sxs-lookup"><span data-stu-id="6080e-115">Remarks</span></span>  
 <span data-ttu-id="6080e-116">Este método lo implementa el escritor de la aplicación de depuración.</span><span class="sxs-lookup"><span data-stu-id="6080e-116">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6080e-117">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="6080e-117">Requirements</span></span>  
 <span data-ttu-id="6080e-118">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6080e-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6080e-119">**Encabezado:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="6080e-119">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="6080e-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6080e-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6080e-121">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6080e-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6080e-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="6080e-122">See also</span></span>

- [<span data-ttu-id="6080e-123">ICLRDataTarget (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6080e-123">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
