---
title: ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo (Método)
ms.date: 03/30/2017
ms.assetid: f738a6ed-7cd9-4106-a5cd-355481e5771c
ms.openlocfilehash: 59e3a95a4d2573263600da60b4f852caa361138e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129192"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefineasyncstepinfo-method"></a><span data-ttu-id="dfc1e-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo (Método)</span><span class="sxs-lookup"><span data-stu-id="dfc1e-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo Method</span></span>
<span data-ttu-id="dfc1e-103">Defina un grupo de operaciones de espera asincrónica en el método actual.</span><span class="sxs-lookup"><span data-stu-id="dfc1e-103">Define a group of async await operations in the current method.</span></span>  
  
 <span data-ttu-id="dfc1e-104">Cada desplazamiento yield coincide con una instrucción return de Await, que identifica un posible rendimiento.</span><span class="sxs-lookup"><span data-stu-id="dfc1e-104">Each yield offset matches an await's return instruction, identifying a potential yield.</span></span> <span data-ttu-id="dfc1e-105">Cada `breakpointMethod`/par de `breakpointOffset` nos indica dónde se reanudará la operación asincrónica, que podría estar en un método diferente.</span><span class="sxs-lookup"><span data-stu-id="dfc1e-105">Each `breakpointMethod`/`breakpointOffset` pair tells us where the asynchronous operation will resume which could be in a different method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dfc1e-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dfc1e-106">Syntax</span></span>  
  
```idl  
HRESULT DefineAsyncStepInfo(    [in] ULONG32 count,    [in, size_is(count)] ULONG32 yieldOffsets[],    [in, size_is(count)] ULONG32 breakpointOffset[],     [in, size_is(count)] mdToken breakpointMethod[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dfc1e-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="dfc1e-107">Parameters</span></span>  
  
|<span data-ttu-id="dfc1e-108">Parámetro</span><span class="sxs-lookup"><span data-stu-id="dfc1e-108">Parameter</span></span>|<span data-ttu-id="dfc1e-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="dfc1e-109">Description</span></span>|  
|---------------|-----------------|  
|`count`||  
|`yieldOffsets`||  
|`breakpointOffset`||  
|`breakpointMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="dfc1e-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="dfc1e-110">Return Value</span></span>  
 <span data-ttu-id="dfc1e-111">Devuelve `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="dfc1e-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dfc1e-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dfc1e-112">Requirements</span></span>  
 <span data-ttu-id="dfc1e-113">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="dfc1e-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfc1e-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="dfc1e-114">See also</span></span>

- [<span data-ttu-id="dfc1e-115">ISymUnmanagedAsyncMethodPropertiesWriter (interfaz)</span><span class="sxs-lookup"><span data-stu-id="dfc1e-115">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)
