---
title: ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo (Método)
ms.date: 03/30/2017
ms.assetid: f738a6ed-7cd9-4106-a5cd-355481e5771c
ms.openlocfilehash: 5a501cca16f06e7ccd5da9f65a213c6b24c1092c
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441791"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefineasyncstepinfo-method"></a><span data-ttu-id="aa4d8-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo (Método)</span><span class="sxs-lookup"><span data-stu-id="aa4d8-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo Method</span></span>
<span data-ttu-id="aa4d8-103">Defina un grupo de operaciones de espera asincrónica en el método actual.</span><span class="sxs-lookup"><span data-stu-id="aa4d8-103">Define a group of async await operations in the current method.</span></span>  
  
 <span data-ttu-id="aa4d8-104">Cada desplazamiento yield coincide con una instrucción return de Await, que identifica un posible rendimiento.</span><span class="sxs-lookup"><span data-stu-id="aa4d8-104">Each yield offset matches an await's return instruction, identifying a potential yield.</span></span> <span data-ttu-id="aa4d8-105">Cada `breakpointMethod` / `breakpointOffset` par nos indica dónde se reanudará la operación asincrónica, que podría estar en un método diferente.</span><span class="sxs-lookup"><span data-stu-id="aa4d8-105">Each `breakpointMethod`/`breakpointOffset` pair tells us where the asynchronous operation will resume which could be in a different method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa4d8-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="aa4d8-106">Syntax</span></span>  
  
```idl  
HRESULT DefineAsyncStepInfo(    [in] ULONG32 count,    [in, size_is(count)] ULONG32 yieldOffsets[],    [in, size_is(count)] ULONG32 breakpointOffset[],     [in, size_is(count)] mdToken breakpointMethod[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aa4d8-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="aa4d8-107">Parameters</span></span>  
  
|<span data-ttu-id="aa4d8-108">Parámetro</span><span class="sxs-lookup"><span data-stu-id="aa4d8-108">Parameter</span></span>|<span data-ttu-id="aa4d8-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="aa4d8-109">Description</span></span>|  
|---------------|-----------------|  
|`count`||  
|`yieldOffsets`||  
|`breakpointOffset`||  
|`breakpointMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="aa4d8-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="aa4d8-110">Return Value</span></span>  
 <span data-ttu-id="aa4d8-111">Devuelve `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="aa4d8-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aa4d8-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="aa4d8-112">Requirements</span></span>  
 <span data-ttu-id="aa4d8-113">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="aa4d8-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa4d8-114">Consulta también</span><span class="sxs-lookup"><span data-stu-id="aa4d8-114">See also</span></span>

- [<span data-ttu-id="aa4d8-115">ISymUnmanagedAsyncMethodPropertiesWriter (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="aa4d8-115">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](isymunmanagedasyncmethodpropertieswriter-interface.md)
