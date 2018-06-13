---
title: ISymUnmanagedWriter5::MapTokenToSourceSpan (Método)
ms.date: 03/30/2017
ms.assetid: d0fbbf61-71c6-4fb1-8c9f-d619ca5d7d68
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7751ed951c213c52c68125543622ed110124f5b1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33427948"
---
# <a name="isymunmanagedwriter5maptokentosourcespan-method"></a><span data-ttu-id="ae66c-102">ISymUnmanagedWriter5::MapTokenToSourceSpan (Método)</span><span class="sxs-lookup"><span data-stu-id="ae66c-102">ISymUnmanagedWriter5::MapTokenToSourceSpan Method</span></span>
<span data-ttu-id="ae66c-103">Mapas que abarcan el token de metadatos especificado en la línea de código fuente en el archivo de origen especificado.</span><span class="sxs-lookup"><span data-stu-id="ae66c-103">Maps the given metadata token to the given source line span in the specified source file.</span></span>  
  
 <span data-ttu-id="ae66c-104">Debe llamarse entre las llamadas a [OpenMapTokensToSourceSpans (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md) y [CloseMapTokensToSourceSpans (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md).</span><span class="sxs-lookup"><span data-stu-id="ae66c-104">Must be called between calls to [OpenMapTokensToSourceSpans Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md) and [CloseMapTokensToSourceSpans Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae66c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ae66c-105">Syntax</span></span>  
  
```idl  
HRESULT MapTokenToSourceSpan(    [in] mdToken token,    [in] ISymUnmanagedDocumentWriter* document,    [in] ULONG32 line,    [in] ULONG32 column,    [in] ULONG32 endLine,    [in] ULONG32 endColumn);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ae66c-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ae66c-106">Parameters</span></span>  
  
|<span data-ttu-id="ae66c-107">Parámetro</span><span class="sxs-lookup"><span data-stu-id="ae66c-107">Parameter</span></span>|<span data-ttu-id="ae66c-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="ae66c-108">Description</span></span>|  
|---------------|-----------------|  
|`token`||  
|`document`||  
|`line`||  
|`column`||  
|`endLine`||  
|`endColumn`||  
  
## <a name="return-value"></a><span data-ttu-id="ae66c-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ae66c-109">Return Value</span></span>  
 <span data-ttu-id="ae66c-110">Devuelve `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="ae66c-110">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae66c-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ae66c-111">Requirements</span></span>  
 <span data-ttu-id="ae66c-112">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="ae66c-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae66c-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="ae66c-113">See Also</span></span>  
 [<span data-ttu-id="ae66c-114">ISymUnmanagedWriter5 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ae66c-114">ISymUnmanagedWriter5 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-interface.md)
