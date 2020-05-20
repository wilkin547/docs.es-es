---
title: ISymUnmanagedWriter5::OpenMapTokensToSourceSpans (Método)
ms.date: 03/30/2017
ms.assetid: 93ad2517-b0dc-464c-8688-a58a30eda18d
ms.openlocfilehash: 82b46ea315009b65254735d44e355154b83b22e2
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83609500"
---
# <a name="isymunmanagedwriter5openmaptokenstosourcespans-method"></a><span data-ttu-id="bfb43-102">ISymUnmanagedWriter5::OpenMapTokensToSourceSpans (Método)</span><span class="sxs-lookup"><span data-stu-id="bfb43-102">ISymUnmanagedWriter5::OpenMapTokensToSourceSpans Method</span></span>
<span data-ttu-id="bfb43-103">Abra una sección especial de datos personalizados para emitir información de asignación de intervalos de token a origen en.</span><span class="sxs-lookup"><span data-stu-id="bfb43-103">Open a special custom data section to emit token-to-source span mapping information into.</span></span> <span data-ttu-id="bfb43-104">Abrir esta sección cuando un método ya está abierto, o viceversa, es un error.</span><span class="sxs-lookup"><span data-stu-id="bfb43-104">Opening this section when a method is already open, or vice versa, is an error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bfb43-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bfb43-105">Syntax</span></span>  
  
```idl  
HRESULT OpenMapTokensToSourceSpans();  
```  
  
## <a name="return-value"></a><span data-ttu-id="bfb43-106">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="bfb43-106">Return Value</span></span>  
 <span data-ttu-id="bfb43-107">Devuelve `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="bfb43-107">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bfb43-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bfb43-108">Requirements</span></span>  
 <span data-ttu-id="bfb43-109">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="bfb43-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfb43-110">Consulta también</span><span class="sxs-lookup"><span data-stu-id="bfb43-110">See also</span></span>

- [<span data-ttu-id="bfb43-111">ISymUnmanagedWriter5 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="bfb43-111">ISymUnmanagedWriter5 Interface</span></span>](isymunmanagedwriter5-interface.md)
