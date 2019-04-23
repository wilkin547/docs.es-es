---
title: ISymUnmanagedWriter5::MapTokenToSourceSpan (Método)
ms.date: 03/30/2017
ms.assetid: d0fbbf61-71c6-4fb1-8c9f-d619ca5d7d68
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 08c219dd033b39fc07159875b184cdf70e3aa3ed
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59181524"
---
# <a name="isymunmanagedwriter5maptokentosourcespan-method"></a><span data-ttu-id="0ec68-102">ISymUnmanagedWriter5::MapTokenToSourceSpan (Método)</span><span class="sxs-lookup"><span data-stu-id="0ec68-102">ISymUnmanagedWriter5::MapTokenToSourceSpan Method</span></span>
<span data-ttu-id="0ec68-103">Asignaciones que abarcan el token de metadatos especificado a la línea de origen especificado en el archivo de origen especificado.</span><span class="sxs-lookup"><span data-stu-id="0ec68-103">Maps the given metadata token to the given source line span in the specified source file.</span></span>  
  
 <span data-ttu-id="0ec68-104">Debe llamarse entre las llamadas a [OpenMapTokensToSourceSpans (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md) y [CloseMapTokensToSourceSpans (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md).</span><span class="sxs-lookup"><span data-stu-id="0ec68-104">Must be called between calls to [OpenMapTokensToSourceSpans Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md) and [CloseMapTokensToSourceSpans Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ec68-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0ec68-105">Syntax</span></span>  
  
```idl  
HRESULT MapTokenToSourceSpan(    [in] mdToken token,    [in] ISymUnmanagedDocumentWriter* document,    [in] ULONG32 line,    [in] ULONG32 column,    [in] ULONG32 endLine,    [in] ULONG32 endColumn);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0ec68-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0ec68-106">Parameters</span></span>  
  
|<span data-ttu-id="0ec68-107">Parámetro</span><span class="sxs-lookup"><span data-stu-id="0ec68-107">Parameter</span></span>|<span data-ttu-id="0ec68-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="0ec68-108">Description</span></span>|  
|---------------|-----------------|  
|`token`||  
|`document`||  
|`line`||  
|`column`||  
|`endLine`||  
|`endColumn`||  
  
## <a name="return-value"></a><span data-ttu-id="0ec68-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="0ec68-109">Return Value</span></span>  
 <span data-ttu-id="0ec68-110">Devuelve `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="0ec68-110">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ec68-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0ec68-111">Requirements</span></span>  
 <span data-ttu-id="0ec68-112">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="0ec68-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ec68-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="0ec68-113">See also</span></span>

- [<span data-ttu-id="0ec68-114">ISymUnmanagedWriter5 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0ec68-114">ISymUnmanagedWriter5 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-interface.md)
