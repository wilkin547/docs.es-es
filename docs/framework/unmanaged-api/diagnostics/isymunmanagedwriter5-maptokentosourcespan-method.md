---
title: ISymUnmanagedWriter5::MapTokenToSourceSpan (Método)
ms.date: 03/30/2017
ms.assetid: d0fbbf61-71c6-4fb1-8c9f-d619ca5d7d68
ms.openlocfilehash: 0f00dd34ffbdd58a46260132d8d7ace74ec2f294
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501682"
---
# <a name="isymunmanagedwriter5maptokentosourcespan-method"></a><span data-ttu-id="33880-102">ISymUnmanagedWriter5::MapTokenToSourceSpan (Método)</span><span class="sxs-lookup"><span data-stu-id="33880-102">ISymUnmanagedWriter5::MapTokenToSourceSpan Method</span></span>
<span data-ttu-id="33880-103">Asigna el token de metadatos especificado al intervalo de la línea de código fuente especificado en el archivo de código fuente especificado.</span><span class="sxs-lookup"><span data-stu-id="33880-103">Maps the given metadata token to the given source line span in the specified source file.</span></span>  
  
 <span data-ttu-id="33880-104">Se debe llamar entre las llamadas al [método openmaptokenstosourcespans (](isymunmanagedwriter5-openmaptokenstosourcespans-method.md) y al [método closemaptokenstosourcespans (](isymunmanagedwriter5-closemaptokenstosourcespans-method.md).</span><span class="sxs-lookup"><span data-stu-id="33880-104">Must be called between calls to [OpenMapTokensToSourceSpans Method](isymunmanagedwriter5-openmaptokenstosourcespans-method.md) and [CloseMapTokensToSourceSpans Method](isymunmanagedwriter5-closemaptokenstosourcespans-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33880-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="33880-105">Syntax</span></span>  
  
```idl  
HRESULT MapTokenToSourceSpan(    [in] mdToken token,    [in] ISymUnmanagedDocumentWriter* document,    [in] ULONG32 line,    [in] ULONG32 column,    [in] ULONG32 endLine,    [in] ULONG32 endColumn);  
```  
  
## <a name="parameters"></a><span data-ttu-id="33880-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="33880-106">Parameters</span></span>  
  
|<span data-ttu-id="33880-107">Parámetro</span><span class="sxs-lookup"><span data-stu-id="33880-107">Parameter</span></span>|<span data-ttu-id="33880-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="33880-108">Description</span></span>|  
|---------------|-----------------|  
|`token`||  
|`document`||  
|`line`||  
|`column`||  
|`endLine`||  
|`endColumn`||  
  
## <a name="return-value"></a><span data-ttu-id="33880-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="33880-109">Return Value</span></span>  
 <span data-ttu-id="33880-110">Devuelve `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="33880-110">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33880-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="33880-111">Requirements</span></span>  
 <span data-ttu-id="33880-112">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="33880-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33880-113">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="33880-113">See also</span></span>

- [<span data-ttu-id="33880-114">ISymUnmanagedWriter5 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="33880-114">ISymUnmanagedWriter5 Interface</span></span>](isymunmanagedwriter5-interface.md)
