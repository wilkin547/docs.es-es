---
title: ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo (Método)
ms.date: 03/30/2017
ms.assetid: f738a6ed-7cd9-4106-a5cd-355481e5771c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3ebd4bb1d674a27785ccbe5460a65fed764638ea
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33435882"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefineasyncstepinfo-method"></a><span data-ttu-id="75c6f-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo (Método)</span><span class="sxs-lookup"><span data-stu-id="75c6f-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo Method</span></span>
<span data-ttu-id="75c6f-103">Definir un grupo de la asincronía await operaciones en el método actual.</span><span class="sxs-lookup"><span data-stu-id="75c6f-103">Define a group of async await operations in the current method.</span></span>  
  
 <span data-ttu-id="75c6f-104">Cada desplazamiento yield coincide con la instrucción de devolución de una instrucción await, identificar un rendimiento potencial.</span><span class="sxs-lookup"><span data-stu-id="75c6f-104">Each yield offset matches an await's return instruction, identifying a potential yield.</span></span> <span data-ttu-id="75c6f-105">Cada `breakpointMethod` / `breakpointOffset` par nos indica dónde se reanudará la operación asincrónica, (que puede ser en un método diferente.</span><span class="sxs-lookup"><span data-stu-id="75c6f-105">Each `breakpointMethod`/`breakpointOffset` pair tells us where the asynchronous operation will resume,(which could be in a different method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75c6f-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="75c6f-106">Syntax</span></span>  
  
```idl  
HRESULT DefineAsyncStepInfo(    [in] ULONG32 count,    [in, size_is(count)] ULONG32 yieldOffsets[],    [in, size_is(count)] ULONG32 breakpointOffset[],     [in, size_is(count)] mdToken breakpointMethod[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="75c6f-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="75c6f-107">Parameters</span></span>  
  
|<span data-ttu-id="75c6f-108">Parámetro</span><span class="sxs-lookup"><span data-stu-id="75c6f-108">Parameter</span></span>|<span data-ttu-id="75c6f-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="75c6f-109">Description</span></span>|  
|---------------|-----------------|  
|`count`||  
|`yieldOffsets`||  
|`breakpointOffset`||  
|`breakpointMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="75c6f-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="75c6f-110">Return Value</span></span>  
 <span data-ttu-id="75c6f-111">Devuelve `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="75c6f-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="75c6f-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="75c6f-112">Requirements</span></span>  
 <span data-ttu-id="75c6f-113">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="75c6f-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75c6f-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="75c6f-114">See Also</span></span>  
 [<span data-ttu-id="75c6f-115">ISymUnmanagedAsyncMethodPropertiesWriter (interfaz)</span><span class="sxs-lookup"><span data-stu-id="75c6f-115">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)
