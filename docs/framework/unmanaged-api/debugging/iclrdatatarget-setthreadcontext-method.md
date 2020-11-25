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
ms.openlocfilehash: c135c051637858682c22db58d562e1d50eea562b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723706"
---
# <a name="iclrdatatargetsetthreadcontext-method"></a><span data-ttu-id="fea13-102">ICLRDataTarget::SetThreadContext (Método)</span><span class="sxs-lookup"><span data-stu-id="fea13-102">ICLRDataTarget::SetThreadContext Method</span></span>

<span data-ttu-id="fea13-103">Establece el contexto actual del subproceso especificado en el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="fea13-103">Sets the current context of the specified thread in the target process.</span></span> <span data-ttu-id="fea13-104">Los servicios de acceso a datos de Common Language Runtime (CLR) llaman a este método.</span><span class="sxs-lookup"><span data-stu-id="fea13-104">This method is called by the common language runtime (CLR) data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fea13-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fea13-105">Syntax</span></span>  
  
```cpp  
HRESULT SetThreadContext (  
    [in] ULONG32            threadID,  
    [in] ULONG32            contextSize,  
    [in, size_is(contextSize)]
         BYTE               *context  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fea13-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fea13-106">Parameters</span></span>  

 `threadID`  
 <span data-ttu-id="fea13-107">de Identificador del sistema operativo de un subproceso en el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="fea13-107">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="fea13-108">de Tamaño del contexto.</span><span class="sxs-lookup"><span data-stu-id="fea13-108">[in] The size of the context.</span></span>  
  
 `context`  
 <span data-ttu-id="fea13-109">de Puntero a un búfer que contiene el contexto.</span><span class="sxs-lookup"><span data-stu-id="fea13-109">[in] Pointer to a buffer containing the context.</span></span>  
  
 <span data-ttu-id="fea13-110">Los datos del `context` búfer estarán en el formato de la estructura de Win32 `CONTEXT` .</span><span class="sxs-lookup"><span data-stu-id="fea13-110">The data in the `context` buffer will be in the format of the Win32 `CONTEXT` structure.</span></span> <span data-ttu-id="fea13-111">El contexto especifica los datos de registro específicos del procesador, por lo que la definición de la estructura de Win32 `CONTEXT` depende de la arquitectura del procesador.</span><span class="sxs-lookup"><span data-stu-id="fea13-111">The context specifies processor-specific register data, so the definition of the Win32 `CONTEXT` structure depends on the processor's architecture.</span></span> <span data-ttu-id="fea13-112">Consulte el archivo de encabezado Winnt. h para ver la definición de la estructura de Win32 `CONTEXT` .</span><span class="sxs-lookup"><span data-stu-id="fea13-112">Refer to the WinNT.h header file for the definition of the Win32 `CONTEXT` structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fea13-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fea13-113">Remarks</span></span>  

 <span data-ttu-id="fea13-114">Este método lo implementa el escritor de la aplicación de depuración.</span><span class="sxs-lookup"><span data-stu-id="fea13-114">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fea13-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fea13-115">Requirements</span></span>  

 <span data-ttu-id="fea13-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fea13-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fea13-117">**Encabezado:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="fea13-117">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="fea13-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fea13-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fea13-119">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fea13-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fea13-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fea13-120">See also</span></span>

- [<span data-ttu-id="fea13-121">ICLRDataTarget (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="fea13-121">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
