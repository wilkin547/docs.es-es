---
description: 'Más información sobre: ISymUnmanagedWriter5:: Maptokentosourcespan ((método)'
title: ISymUnmanagedWriter5::MapTokenToSourceSpan (Método)
ms.date: 03/30/2017
ms.assetid: d0fbbf61-71c6-4fb1-8c9f-d619ca5d7d68
ms.openlocfilehash: b30d8051f5d2872488639ce999cccd4248af367f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99761621"
---
# <a name="isymunmanagedwriter5maptokentosourcespan-method"></a><span data-ttu-id="fe869-103">ISymUnmanagedWriter5::MapTokenToSourceSpan (Método)</span><span class="sxs-lookup"><span data-stu-id="fe869-103">ISymUnmanagedWriter5::MapTokenToSourceSpan Method</span></span>

<span data-ttu-id="fe869-104">Asigna el token de metadatos especificado al intervalo de la línea de código fuente especificado en el archivo de código fuente especificado.</span><span class="sxs-lookup"><span data-stu-id="fe869-104">Maps the given metadata token to the given source line span in the specified source file.</span></span>  
  
 <span data-ttu-id="fe869-105">Se debe llamar entre las llamadas al [método openmaptokenstosourcespans (](isymunmanagedwriter5-openmaptokenstosourcespans-method.md) y al [método closemaptokenstosourcespans (](isymunmanagedwriter5-closemaptokenstosourcespans-method.md).</span><span class="sxs-lookup"><span data-stu-id="fe869-105">Must be called between calls to [OpenMapTokensToSourceSpans Method](isymunmanagedwriter5-openmaptokenstosourcespans-method.md) and [CloseMapTokensToSourceSpans Method](isymunmanagedwriter5-closemaptokenstosourcespans-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe869-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fe869-106">Syntax</span></span>  
  
```idl  
HRESULT MapTokenToSourceSpan(    [in] mdToken token,    [in] ISymUnmanagedDocumentWriter* document,    [in] ULONG32 line,    [in] ULONG32 column,    [in] ULONG32 endLine,    [in] ULONG32 endColumn);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fe869-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fe869-107">Parameters</span></span>  
  
|<span data-ttu-id="fe869-108">Parámetro</span><span class="sxs-lookup"><span data-stu-id="fe869-108">Parameter</span></span>|<span data-ttu-id="fe869-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="fe869-109">Description</span></span>|  
|---------------|-----------------|  
|`token`||  
|`document`||  
|`line`||  
|`column`||  
|`endLine`||  
|`endColumn`||  
  
## <a name="return-value"></a><span data-ttu-id="fe869-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="fe869-110">Return Value</span></span>  

 <span data-ttu-id="fe869-111">Devuelve `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="fe869-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe869-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fe869-112">Requirements</span></span>  

 <span data-ttu-id="fe869-113">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="fe869-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe869-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="fe869-114">See also</span></span>

- [<span data-ttu-id="fe869-115">ISymUnmanagedWriter5 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="fe869-115">ISymUnmanagedWriter5 Interface</span></span>](isymunmanagedwriter5-interface.md)
