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
ms.openlocfilehash: 5c0fb023dd355f3a9c1ed846913f86b354592ed5
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860612"
---
# <a name="iclrdatatargetgetthreadcontext-method"></a><span data-ttu-id="cbe63-102">ICLRDataTarget::GetThreadContext (Método)</span><span class="sxs-lookup"><span data-stu-id="cbe63-102">ICLRDataTarget::GetThreadContext Method</span></span>
<span data-ttu-id="cbe63-103">Obtiene el contexto de ejecución actual para el subproceso dado en el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="cbe63-103">Gets the current execution context for the given thread in the target process.</span></span> <span data-ttu-id="cbe63-104">El servicio de acceso a datos de Common Language Runtime llama a este método.</span><span class="sxs-lookup"><span data-stu-id="cbe63-104">This method is called by the common language runtime data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cbe63-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cbe63-105">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadContext (  
    [in] ULONG32            threadID,  
    [in] ULONG32            contextFlags,  
    [in] ULONG32            contextSize,  
    [out, size_is(contextSize)]
        BYTE                *context  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cbe63-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cbe63-106">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="cbe63-107">de Identificador del sistema operativo de un subproceso en el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="cbe63-107">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `contextFlags`  
 <span data-ttu-id="cbe63-108">de Marcas que especifican qué partes del contexto se van a devolver.</span><span class="sxs-lookup"><span data-stu-id="cbe63-108">[in] Flags that specify which parts of the context to return.</span></span> <span data-ttu-id="cbe63-109">La implementación devolverá al menos estas partes del contexto.</span><span class="sxs-lookup"><span data-stu-id="cbe63-109">The implementation will return at least these parts of the context.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="cbe63-110">de Tamaño del contexto.</span><span class="sxs-lookup"><span data-stu-id="cbe63-110">[in] The size of the context.</span></span>  
  
 `context`  
 <span data-ttu-id="cbe63-111">enuncia Puntero a un búfer en el que se va a colocar el contexto.</span><span class="sxs-lookup"><span data-stu-id="cbe63-111">[out] Pointer to a buffer in which to place the context.</span></span>  
  
 <span data-ttu-id="cbe63-112">Los datos del `context` búfer deben tener el formato de la estructura de Win32 `CONTEXT` .</span><span class="sxs-lookup"><span data-stu-id="cbe63-112">The data in the `context` buffer must be in the format of the Win32 `CONTEXT` structure.</span></span> <span data-ttu-id="cbe63-113">El contexto especifica los datos de registro específicos del procesador, por lo que la `CONTEXT` definición de la estructura de Win32 depende de la arquitectura del procesador.</span><span class="sxs-lookup"><span data-stu-id="cbe63-113">The context specifies processor-specific register data, so the definition of the Win32 `CONTEXT` structure depends on the processor's architecture.</span></span> <span data-ttu-id="cbe63-114">Consulte el archivo de encabezado Winnt. h para ver la definición de `CONTEXT` la estructura de Win32.</span><span class="sxs-lookup"><span data-stu-id="cbe63-114">Refer to the WinNT.h header file for the definition of the Win32 `CONTEXT` structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cbe63-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cbe63-115">Remarks</span></span>  
 <span data-ttu-id="cbe63-116">Este método lo implementa el escritor de la aplicación de depuración.</span><span class="sxs-lookup"><span data-stu-id="cbe63-116">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cbe63-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cbe63-117">Requirements</span></span>  
 <span data-ttu-id="cbe63-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cbe63-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cbe63-119">**Encabezado:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="cbe63-119">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="cbe63-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cbe63-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cbe63-121">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cbe63-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbe63-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cbe63-122">See also</span></span>

- [<span data-ttu-id="cbe63-123">ICLRDataTarget (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="cbe63-123">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
