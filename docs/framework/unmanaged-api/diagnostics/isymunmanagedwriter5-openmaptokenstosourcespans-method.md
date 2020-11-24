---
title: ISymUnmanagedWriter5::OpenMapTokensToSourceSpans (Método)
ms.date: 03/30/2017
ms.assetid: 93ad2517-b0dc-464c-8688-a58a30eda18d
ms.openlocfilehash: 95976e2f331252c88eab717e184abc284842e3b3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683269"
---
# <a name="isymunmanagedwriter5openmaptokenstosourcespans-method"></a><span data-ttu-id="dbcce-102">ISymUnmanagedWriter5::OpenMapTokensToSourceSpans (Método)</span><span class="sxs-lookup"><span data-stu-id="dbcce-102">ISymUnmanagedWriter5::OpenMapTokensToSourceSpans Method</span></span>

<span data-ttu-id="dbcce-103">Abra una sección especial de datos personalizados para emitir información de asignación de intervalos de token a origen en.</span><span class="sxs-lookup"><span data-stu-id="dbcce-103">Open a special custom data section to emit token-to-source span mapping information into.</span></span> <span data-ttu-id="dbcce-104">Abrir esta sección cuando un método ya está abierto, o viceversa, es un error.</span><span class="sxs-lookup"><span data-stu-id="dbcce-104">Opening this section when a method is already open, or vice versa, is an error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dbcce-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dbcce-105">Syntax</span></span>  
  
```idl  
HRESULT OpenMapTokensToSourceSpans();  
```  
  
## <a name="return-value"></a><span data-ttu-id="dbcce-106">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="dbcce-106">Return Value</span></span>  

 <span data-ttu-id="dbcce-107">Devuelve `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="dbcce-107">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dbcce-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dbcce-108">Requirements</span></span>  

 <span data-ttu-id="dbcce-109">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="dbcce-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbcce-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dbcce-110">See also</span></span>

- [<span data-ttu-id="dbcce-111">ISymUnmanagedWriter5 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="dbcce-111">ISymUnmanagedWriter5 Interface</span></span>](isymunmanagedwriter5-interface.md)
