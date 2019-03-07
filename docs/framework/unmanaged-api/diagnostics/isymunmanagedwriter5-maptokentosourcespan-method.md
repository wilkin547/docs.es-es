---
title: ISymUnmanagedWriter5::MapTokenToSourceSpan (Método)
ms.date: 03/30/2017
ms.assetid: d0fbbf61-71c6-4fb1-8c9f-d619ca5d7d68
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cf061de3e75550e33ba67c1d624279b1673c5382
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57465341"
---
# <a name="isymunmanagedwriter5maptokentosourcespan-method"></a><span data-ttu-id="6627c-102">ISymUnmanagedWriter5::MapTokenToSourceSpan (Método)</span><span class="sxs-lookup"><span data-stu-id="6627c-102">ISymUnmanagedWriter5::MapTokenToSourceSpan Method</span></span>
<span data-ttu-id="6627c-103">Asignaciones que abarcan el token de metadatos especificado a la línea de origen especificado en el archivo de origen especificado.</span><span class="sxs-lookup"><span data-stu-id="6627c-103">Maps the given metadata token to the given source line span in the specified source file.</span></span>  
  
 <span data-ttu-id="6627c-104">Debe llamarse entre las llamadas a [OpenMapTokensToSourceSpans (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md) y [CloseMapTokensToSourceSpans (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md).</span><span class="sxs-lookup"><span data-stu-id="6627c-104">Must be called between calls to [OpenMapTokensToSourceSpans Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md) and [CloseMapTokensToSourceSpans Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6627c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6627c-105">Syntax</span></span>  
  
```idl  
HRESULT MapTokenToSourceSpan(    [in] mdToken token,    [in] ISymUnmanagedDocumentWriter* document,    [in] ULONG32 line,    [in] ULONG32 column,    [in] ULONG32 endLine,    [in] ULONG32 endColumn);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6627c-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6627c-106">Parameters</span></span>  
  
|<span data-ttu-id="6627c-107">Parámetro</span><span class="sxs-lookup"><span data-stu-id="6627c-107">Parameter</span></span>|<span data-ttu-id="6627c-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="6627c-108">Description</span></span>|  
|---------------|-----------------|  
|`token`||  
|`document`||  
|`line`||  
|`column`||  
|`endLine`||  
|`endColumn`||  
  
## <a name="return-value"></a><span data-ttu-id="6627c-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="6627c-109">Return Value</span></span>  
 <span data-ttu-id="6627c-110">Devuelve `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="6627c-110">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6627c-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6627c-111">Requirements</span></span>  
 <span data-ttu-id="6627c-112">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="6627c-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6627c-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="6627c-113">See also</span></span>
- [<span data-ttu-id="6627c-114">ISymUnmanagedWriter5 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6627c-114">ISymUnmanagedWriter5 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-interface.md)
