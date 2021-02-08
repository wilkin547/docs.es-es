---
description: 'Más información acerca de: ISymUnmanagedAsyncMethodPropertiesWriter::D efineAsyncStepInfo (método)'
title: ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo (Método)
ms.date: 03/30/2017
ms.assetid: f738a6ed-7cd9-4106-a5cd-355481e5771c
ms.openlocfilehash: f95436b10041ae5bfd56ca080a9b8ce70748022c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790248"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefineasyncstepinfo-method"></a><span data-ttu-id="40508-103">ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo (Método)</span><span class="sxs-lookup"><span data-stu-id="40508-103">ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo Method</span></span>

<span data-ttu-id="40508-104">Defina un grupo de operaciones de espera asincrónica en el método actual.</span><span class="sxs-lookup"><span data-stu-id="40508-104">Define a group of async await operations in the current method.</span></span>  
  
 <span data-ttu-id="40508-105">Cada desplazamiento yield coincide con una instrucción return de Await, que identifica un posible rendimiento.</span><span class="sxs-lookup"><span data-stu-id="40508-105">Each yield offset matches an await's return instruction, identifying a potential yield.</span></span> <span data-ttu-id="40508-106">Cada `breakpointMethod` / `breakpointOffset` par nos indica dónde se reanudará la operación asincrónica, que podría estar en un método diferente.</span><span class="sxs-lookup"><span data-stu-id="40508-106">Each `breakpointMethod`/`breakpointOffset` pair tells us where the asynchronous operation will resume which could be in a different method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40508-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="40508-107">Syntax</span></span>  
  
```idl  
HRESULT DefineAsyncStepInfo(    [in] ULONG32 count,    [in, size_is(count)] ULONG32 yieldOffsets[],    [in, size_is(count)] ULONG32 breakpointOffset[],     [in, size_is(count)] mdToken breakpointMethod[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="40508-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="40508-108">Parameters</span></span>  
  
|<span data-ttu-id="40508-109">Parámetro</span><span class="sxs-lookup"><span data-stu-id="40508-109">Parameter</span></span>|<span data-ttu-id="40508-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="40508-110">Description</span></span>|  
|---------------|-----------------|  
|`count`||  
|`yieldOffsets`||  
|`breakpointOffset`||  
|`breakpointMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="40508-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="40508-111">Return Value</span></span>  

 <span data-ttu-id="40508-112">Devuelve `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="40508-112">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="40508-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="40508-113">Requirements</span></span>  

 <span data-ttu-id="40508-114">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="40508-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40508-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="40508-115">See also</span></span>

- [<span data-ttu-id="40508-116">ISymUnmanagedAsyncMethodPropertiesWriter (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="40508-116">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](isymunmanagedasyncmethodpropertieswriter-interface.md)
