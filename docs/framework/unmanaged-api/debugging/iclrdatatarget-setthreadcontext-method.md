---
description: 'Más información acerca de: ICLRDataTarget:: SetThreadContext (método)'
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
ms.openlocfilehash: fc428bc887f7ba10f3096cdf17a757fb252418f0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99738210"
---
# <a name="iclrdatatargetsetthreadcontext-method"></a><span data-ttu-id="c2c9e-103">ICLRDataTarget::SetThreadContext (Método)</span><span class="sxs-lookup"><span data-stu-id="c2c9e-103">ICLRDataTarget::SetThreadContext Method</span></span>

<span data-ttu-id="c2c9e-104">Establece el contexto actual del subproceso especificado en el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="c2c9e-104">Sets the current context of the specified thread in the target process.</span></span> <span data-ttu-id="c2c9e-105">Los servicios de acceso a datos de Common Language Runtime (CLR) llaman a este método.</span><span class="sxs-lookup"><span data-stu-id="c2c9e-105">This method is called by the common language runtime (CLR) data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2c9e-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c2c9e-106">Syntax</span></span>  
  
```cpp  
HRESULT SetThreadContext (  
    [in] ULONG32            threadID,  
    [in] ULONG32            contextSize,  
    [in, size_is(contextSize)]
         BYTE               *context  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c2c9e-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c2c9e-107">Parameters</span></span>  

 `threadID`  
 <span data-ttu-id="c2c9e-108">de Identificador del sistema operativo de un subproceso en el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="c2c9e-108">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="c2c9e-109">de Tamaño del contexto.</span><span class="sxs-lookup"><span data-stu-id="c2c9e-109">[in] The size of the context.</span></span>  
  
 `context`  
 <span data-ttu-id="c2c9e-110">de Puntero a un búfer que contiene el contexto.</span><span class="sxs-lookup"><span data-stu-id="c2c9e-110">[in] Pointer to a buffer containing the context.</span></span>  
  
 <span data-ttu-id="c2c9e-111">Los datos del `context` búfer estarán en el formato de la estructura de Win32 `CONTEXT` .</span><span class="sxs-lookup"><span data-stu-id="c2c9e-111">The data in the `context` buffer will be in the format of the Win32 `CONTEXT` structure.</span></span> <span data-ttu-id="c2c9e-112">El contexto especifica los datos de registro específicos del procesador, por lo que la definición de la estructura de Win32 `CONTEXT` depende de la arquitectura del procesador.</span><span class="sxs-lookup"><span data-stu-id="c2c9e-112">The context specifies processor-specific register data, so the definition of the Win32 `CONTEXT` structure depends on the processor's architecture.</span></span> <span data-ttu-id="c2c9e-113">Consulte el archivo de encabezado Winnt. h para ver la definición de la estructura de Win32 `CONTEXT` .</span><span class="sxs-lookup"><span data-stu-id="c2c9e-113">Refer to the WinNT.h header file for the definition of the Win32 `CONTEXT` structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c2c9e-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c2c9e-114">Remarks</span></span>  

 <span data-ttu-id="c2c9e-115">Este método lo implementa el escritor de la aplicación de depuración.</span><span class="sxs-lookup"><span data-stu-id="c2c9e-115">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2c9e-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c2c9e-116">Requirements</span></span>  

 <span data-ttu-id="c2c9e-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c2c9e-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2c9e-118">**Encabezado:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="c2c9e-118">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="c2c9e-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c2c9e-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c2c9e-120">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2c9e-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2c9e-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="c2c9e-121">See also</span></span>

- [<span data-ttu-id="c2c9e-122">ICLRDataTarget (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c2c9e-122">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
