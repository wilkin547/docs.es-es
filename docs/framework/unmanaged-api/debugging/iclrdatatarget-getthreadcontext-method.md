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
ms.openlocfilehash: 3777ad4b12c7d0593c095c470aba81088137a859
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179181"
---
# <a name="iclrdatatargetgetthreadcontext-method"></a><span data-ttu-id="bf4c4-102">ICLRDataTarget::GetThreadContext (Método)</span><span class="sxs-lookup"><span data-stu-id="bf4c4-102">ICLRDataTarget::GetThreadContext Method</span></span>
<span data-ttu-id="bf4c4-103">Obtiene el contexto de ejecución actual para el subproceso especificado en el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="bf4c4-103">Gets the current execution context for the given thread in the target process.</span></span> <span data-ttu-id="bf4c4-104">Los servicios de acceso a datos de Common Language Runtime llaman a este método.</span><span class="sxs-lookup"><span data-stu-id="bf4c4-104">This method is called by the common language runtime data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf4c4-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bf4c4-105">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadContext (  
    [in] ULONG32            threadID,  
    [in] ULONG32            contextFlags,  
    [in] ULONG32            contextSize,  
    [out, size_is(contextSize)]
        BYTE                *context  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bf4c4-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bf4c4-106">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="bf4c4-107">[en] Identificador del sistema operativo de un subproceso en el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="bf4c4-107">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `contextFlags`  
 <span data-ttu-id="bf4c4-108">[en] Indicadores que especifican qué partes del contexto se va a devolver.</span><span class="sxs-lookup"><span data-stu-id="bf4c4-108">[in] Flags that specify which parts of the context to return.</span></span> <span data-ttu-id="bf4c4-109">La implementación devolverá al menos estas partes del contexto.</span><span class="sxs-lookup"><span data-stu-id="bf4c4-109">The implementation will return at least these parts of the context.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="bf4c4-110">[en] El tamaño del contexto.</span><span class="sxs-lookup"><span data-stu-id="bf4c4-110">[in] The size of the context.</span></span>  
  
 `context`  
 <span data-ttu-id="bf4c4-111">[fuera] Puntero a un búfer en el que se va a colocar el contexto.</span><span class="sxs-lookup"><span data-stu-id="bf4c4-111">[out] Pointer to a buffer in which to place the context.</span></span>  
  
 <span data-ttu-id="bf4c4-112">Los datos `context` del búfer deben tener el formato `CONTEXT` de la estructura Win32.</span><span class="sxs-lookup"><span data-stu-id="bf4c4-112">The data in the `context` buffer must be in the format of the Win32 `CONTEXT` structure.</span></span> <span data-ttu-id="bf4c4-113">El contexto especifica datos de registro específicos del procesador, por lo que la definición de la estructura Win32 `CONTEXT` depende de la arquitectura del procesador.</span><span class="sxs-lookup"><span data-stu-id="bf4c4-113">The context specifies processor-specific register data, so the definition of the Win32 `CONTEXT` structure depends on the processor's architecture.</span></span> <span data-ttu-id="bf4c4-114">Consulte el archivo de encabezado WinNT.h para `CONTEXT` obtener la definición de la estructura Win32.</span><span class="sxs-lookup"><span data-stu-id="bf4c4-114">Refer to the WinNT.h header file for the definition of the Win32 `CONTEXT` structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bf4c4-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="bf4c4-115">Remarks</span></span>  
 <span data-ttu-id="bf4c4-116">Este método lo implementa el escritor de la aplicación de depuración.</span><span class="sxs-lookup"><span data-stu-id="bf4c4-116">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf4c4-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bf4c4-117">Requirements</span></span>  
 <span data-ttu-id="bf4c4-118">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bf4c4-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf4c4-119">**Encabezado:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="bf4c4-119">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="bf4c4-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bf4c4-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bf4c4-121">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bf4c4-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf4c4-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bf4c4-122">See also</span></span>

- [<span data-ttu-id="bf4c4-123">ICLRDataTarget (interfaz)</span><span class="sxs-lookup"><span data-stu-id="bf4c4-123">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
