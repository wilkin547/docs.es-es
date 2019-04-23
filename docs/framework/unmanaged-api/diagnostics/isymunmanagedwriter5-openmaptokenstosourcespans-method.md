---
title: ISymUnmanagedWriter5::OpenMapTokensToSourceSpans (Método)
ms.date: 03/30/2017
ms.assetid: 93ad2517-b0dc-464c-8688-a58a30eda18d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 82dc2ced988f7277c994eb9449e7c26efa5450b7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59222684"
---
# <a name="isymunmanagedwriter5openmaptokenstosourcespans-method"></a><span data-ttu-id="b2a83-102">ISymUnmanagedWriter5::OpenMapTokensToSourceSpans (Método)</span><span class="sxs-lookup"><span data-stu-id="b2a83-102">ISymUnmanagedWriter5::OpenMapTokensToSourceSpans Method</span></span>
<span data-ttu-id="b2a83-103">Abra una sección especial de datos personalizados para emitir la información de asignación de intervalo de origen de token en.</span><span class="sxs-lookup"><span data-stu-id="b2a83-103">Open a special custom data section to emit token-to-source span mapping information into.</span></span> <span data-ttu-id="b2a83-104">Apertura de esta sección cuando un método ya está abierto, o viceversa, es un error.</span><span class="sxs-lookup"><span data-stu-id="b2a83-104">Opening this section when a method is already open, or vice versa, is an error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2a83-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b2a83-105">Syntax</span></span>  
  
```idl  
HRESULT OpenMapTokensToSourceSpans();  
```  
  
## <a name="return-value"></a><span data-ttu-id="b2a83-106">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b2a83-106">Return Value</span></span>  
 <span data-ttu-id="b2a83-107">Devuelve `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="b2a83-107">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2a83-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b2a83-108">Requirements</span></span>  
 <span data-ttu-id="b2a83-109">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="b2a83-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2a83-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="b2a83-110">See also</span></span>

- [<span data-ttu-id="b2a83-111">ISymUnmanagedWriter5 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b2a83-111">ISymUnmanagedWriter5 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-interface.md)
