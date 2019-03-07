---
title: ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo (Método)
ms.date: 03/30/2017
ms.assetid: f738a6ed-7cd9-4106-a5cd-355481e5771c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6bac541909e07aadff06006fba8c3cfcf4dc5465
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57486230"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefineasyncstepinfo-method"></a><span data-ttu-id="af52c-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo (Método)</span><span class="sxs-lookup"><span data-stu-id="af52c-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo Method</span></span>
<span data-ttu-id="af52c-103">Definir un grupo de async await operaciones en el método actual.</span><span class="sxs-lookup"><span data-stu-id="af52c-103">Define a group of async await operations in the current method.</span></span>  
  
 <span data-ttu-id="af52c-104">Cada desplazamiento yield coincide con la instrucción de devolución de una instrucción await, que identifica un rendimiento potencial.</span><span class="sxs-lookup"><span data-stu-id="af52c-104">Each yield offset matches an await's return instruction, identifying a potential yield.</span></span> <span data-ttu-id="af52c-105">Cada `breakpointMethod` / `breakpointOffset` par nos indica que la operación asincrónica reanudará que podría estar en un método diferente.</span><span class="sxs-lookup"><span data-stu-id="af52c-105">Each `breakpointMethod`/`breakpointOffset` pair tells us where the asynchronous operation will resume which could be in a different method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af52c-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="af52c-106">Syntax</span></span>  
  
```idl  
HRESULT DefineAsyncStepInfo(    [in] ULONG32 count,    [in, size_is(count)] ULONG32 yieldOffsets[],    [in, size_is(count)] ULONG32 breakpointOffset[],     [in, size_is(count)] mdToken breakpointMethod[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="af52c-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="af52c-107">Parameters</span></span>  
  
|<span data-ttu-id="af52c-108">Parámetro</span><span class="sxs-lookup"><span data-stu-id="af52c-108">Parameter</span></span>|<span data-ttu-id="af52c-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="af52c-109">Description</span></span>|  
|---------------|-----------------|  
|`count`||  
|`yieldOffsets`||  
|`breakpointOffset`||  
|`breakpointMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="af52c-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="af52c-110">Return Value</span></span>  
 <span data-ttu-id="af52c-111">Devuelve `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="af52c-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af52c-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="af52c-112">Requirements</span></span>  
 <span data-ttu-id="af52c-113">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="af52c-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af52c-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="af52c-114">See also</span></span>
- [<span data-ttu-id="af52c-115">ISymUnmanagedAsyncMethodPropertiesWriter (interfaz)</span><span class="sxs-lookup"><span data-stu-id="af52c-115">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)
