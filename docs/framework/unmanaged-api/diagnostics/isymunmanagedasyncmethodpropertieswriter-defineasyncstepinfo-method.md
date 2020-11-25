---
title: ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo (Método)
ms.date: 03/30/2017
ms.assetid: f738a6ed-7cd9-4106-a5cd-355481e5771c
ms.openlocfilehash: f8c77e44183fd92704aa91ca1cfd7e3fa68aa27f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719624"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefineasyncstepinfo-method"></a><span data-ttu-id="7f814-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo (Método)</span><span class="sxs-lookup"><span data-stu-id="7f814-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo Method</span></span>

<span data-ttu-id="7f814-103">Defina un grupo de operaciones de espera asincrónica en el método actual.</span><span class="sxs-lookup"><span data-stu-id="7f814-103">Define a group of async await operations in the current method.</span></span>  
  
 <span data-ttu-id="7f814-104">Cada desplazamiento yield coincide con una instrucción return de Await, que identifica un posible rendimiento.</span><span class="sxs-lookup"><span data-stu-id="7f814-104">Each yield offset matches an await's return instruction, identifying a potential yield.</span></span> <span data-ttu-id="7f814-105">Cada `breakpointMethod` / `breakpointOffset` par nos indica dónde se reanudará la operación asincrónica, que podría estar en un método diferente.</span><span class="sxs-lookup"><span data-stu-id="7f814-105">Each `breakpointMethod`/`breakpointOffset` pair tells us where the asynchronous operation will resume which could be in a different method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f814-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7f814-106">Syntax</span></span>  
  
```idl  
HRESULT DefineAsyncStepInfo(    [in] ULONG32 count,    [in, size_is(count)] ULONG32 yieldOffsets[],    [in, size_is(count)] ULONG32 breakpointOffset[],     [in, size_is(count)] mdToken breakpointMethod[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7f814-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7f814-107">Parameters</span></span>  
  
|<span data-ttu-id="7f814-108">Parámetro</span><span class="sxs-lookup"><span data-stu-id="7f814-108">Parameter</span></span>|<span data-ttu-id="7f814-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="7f814-109">Description</span></span>|  
|---------------|-----------------|  
|`count`||  
|`yieldOffsets`||  
|`breakpointOffset`||  
|`breakpointMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="7f814-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="7f814-110">Return Value</span></span>  

 <span data-ttu-id="7f814-111">Devuelve `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="7f814-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7f814-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7f814-112">Requirements</span></span>  

 <span data-ttu-id="7f814-113">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="7f814-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f814-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7f814-114">See also</span></span>

- [<span data-ttu-id="7f814-115">ISymUnmanagedAsyncMethodPropertiesWriter (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7f814-115">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](isymunmanagedasyncmethodpropertieswriter-interface.md)
