---
title: "ISymUnmanagedWriter5::OpenMapTokensToSourceSpans (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 93ad2517-b0dc-464c-8688-a58a30eda18d
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f226a71ac6381c8ca04093beb1d9772d6e6c75e3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedwriter5openmaptokenstosourcespans-method"></a><span data-ttu-id="61da7-102">ISymUnmanagedWriter5::OpenMapTokensToSourceSpans (Método)</span><span class="sxs-lookup"><span data-stu-id="61da7-102">ISymUnmanagedWriter5::OpenMapTokensToSourceSpans Method</span></span>
<span data-ttu-id="61da7-103">Abra una sección especial de datos personalizados para emitir información de asignación de intervalos de origen de token en.</span><span class="sxs-lookup"><span data-stu-id="61da7-103">Open a special custom data section to emit token-to-source span mapping information into.</span></span> <span data-ttu-id="61da7-104">Apertura de esta sección cuando un método ya está abierto, o viceversa, es un error.</span><span class="sxs-lookup"><span data-stu-id="61da7-104">Opening this section when a method is already open, or vice versa, is an error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61da7-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="61da7-105">Syntax</span></span>  
  
```idl  
HRESULT OpenMapTokensToSourceSpans();  
```  
  
## <a name="return-value"></a><span data-ttu-id="61da7-106">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="61da7-106">Return Value</span></span>  
 <span data-ttu-id="61da7-107">Devuelve `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="61da7-107">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="61da7-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="61da7-108">Requirements</span></span>  
 <span data-ttu-id="61da7-109">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="61da7-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61da7-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="61da7-110">See Also</span></span>  
 [<span data-ttu-id="61da7-111">ISymUnmanagedWriter5 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="61da7-111">ISymUnmanagedWriter5 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-interface.md)
