---
title: "ISymUnmanagedWriter::CloseMethod (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.CloseMethod
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::CloseMethod
helpviewer_keywords:
- ISymUnmanagedWriter::CloseMethod method [.NET Framework debugging]
- CloseMethod method [.NET Framework debugging]
ms.assetid: b8025e04-f0e5-40c8-849c-8cd51323420e
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 21c4cdd42613f5e8b60c39426b4f169a034ce7a6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedwriterclosemethod-method"></a><span data-ttu-id="84058-102">ISymUnmanagedWriter::CloseMethod (Método)</span><span class="sxs-lookup"><span data-stu-id="84058-102">ISymUnmanagedWriter::CloseMethod Method</span></span>
<span data-ttu-id="84058-103">Cierra el método actual.</span><span class="sxs-lookup"><span data-stu-id="84058-103">Closes the current method.</span></span> <span data-ttu-id="84058-104">Una vez que se cierra un método, no se puede definir ningún símbolo más dentro de él.</span><span class="sxs-lookup"><span data-stu-id="84058-104">Once a method is closed, no more symbols can be defined within it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84058-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="84058-105">Syntax</span></span>  
  
```  
HRESULT CloseMethod();  
```  
  
## <a name="return-value"></a><span data-ttu-id="84058-106">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="84058-106">Return Value</span></span>  
 <span data-ttu-id="84058-107">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="84058-107">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84058-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="84058-108">Requirements</span></span>  
 <span data-ttu-id="84058-109">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="84058-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84058-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="84058-110">See Also</span></span>  
 [<span data-ttu-id="84058-111">ISymUnmanagedWriter (interfaz)</span><span class="sxs-lookup"><span data-stu-id="84058-111">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 [<span data-ttu-id="84058-112">OpenMethod (método)</span><span class="sxs-lookup"><span data-stu-id="84058-112">OpenMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)
