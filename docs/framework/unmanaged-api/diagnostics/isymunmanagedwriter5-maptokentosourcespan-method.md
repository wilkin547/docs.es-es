---
title: ISymUnmanagedWriter5::MapTokenToSourceSpan (Método)
ms.date: 03/30/2017
ms.assetid: d0fbbf61-71c6-4fb1-8c9f-d619ca5d7d68
ms.openlocfilehash: 876804e7b825443116b1f44a02a685a73153915c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121624"
---
# <a name="isymunmanagedwriter5maptokentosourcespan-method"></a><span data-ttu-id="38a59-102">ISymUnmanagedWriter5::MapTokenToSourceSpan (Método)</span><span class="sxs-lookup"><span data-stu-id="38a59-102">ISymUnmanagedWriter5::MapTokenToSourceSpan Method</span></span>
<span data-ttu-id="38a59-103">Asigna el token de metadatos especificado al intervalo de la línea de código fuente especificado en el archivo de código fuente especificado.</span><span class="sxs-lookup"><span data-stu-id="38a59-103">Maps the given metadata token to the given source line span in the specified source file.</span></span>  
  
 <span data-ttu-id="38a59-104">Se debe llamar entre las llamadas al [método openmaptokenstosourcespans (](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md) y al [método closemaptokenstosourcespans (](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md).</span><span class="sxs-lookup"><span data-stu-id="38a59-104">Must be called between calls to [OpenMapTokensToSourceSpans Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md) and [CloseMapTokensToSourceSpans Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38a59-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="38a59-105">Syntax</span></span>  
  
```idl  
HRESULT MapTokenToSourceSpan(    [in] mdToken token,    [in] ISymUnmanagedDocumentWriter* document,    [in] ULONG32 line,    [in] ULONG32 column,    [in] ULONG32 endLine,    [in] ULONG32 endColumn);  
```  
  
## <a name="parameters"></a><span data-ttu-id="38a59-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="38a59-106">Parameters</span></span>  
  
|<span data-ttu-id="38a59-107">Parámetro</span><span class="sxs-lookup"><span data-stu-id="38a59-107">Parameter</span></span>|<span data-ttu-id="38a59-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="38a59-108">Description</span></span>|  
|---------------|-----------------|  
|`token`||  
|`document`||  
|`line`||  
|`column`||  
|`endLine`||  
|`endColumn`||  
  
## <a name="return-value"></a><span data-ttu-id="38a59-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="38a59-109">Return Value</span></span>  
 <span data-ttu-id="38a59-110">Devuelve `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="38a59-110">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="38a59-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="38a59-111">Requirements</span></span>  
 <span data-ttu-id="38a59-112">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="38a59-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38a59-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="38a59-113">See also</span></span>

- [<span data-ttu-id="38a59-114">ISymUnmanagedWriter5 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="38a59-114">ISymUnmanagedWriter5 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-interface.md)
