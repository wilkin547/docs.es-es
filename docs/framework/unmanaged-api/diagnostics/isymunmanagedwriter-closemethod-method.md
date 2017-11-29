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
ms.openlocfilehash: ea4f917a5e553eb2541f20ce08d403adc7d86d44
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedwriterclosemethod-method"></a><span data-ttu-id="cd129-102">ISymUnmanagedWriter::CloseMethod (Método)</span><span class="sxs-lookup"><span data-stu-id="cd129-102">ISymUnmanagedWriter::CloseMethod Method</span></span>
<span data-ttu-id="cd129-103">Cierra el método actual.</span><span class="sxs-lookup"><span data-stu-id="cd129-103">Closes the current method.</span></span> <span data-ttu-id="cd129-104">Una vez que se cierra un método, no se puede definir ningún símbolo más dentro de él.</span><span class="sxs-lookup"><span data-stu-id="cd129-104">Once a method is closed, no more symbols can be defined within it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd129-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cd129-105">Syntax</span></span>  
  
```  
HRESULT CloseMethod();  
```  
  
## <a name="return-value"></a><span data-ttu-id="cd129-106">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="cd129-106">Return Value</span></span>  
 <span data-ttu-id="cd129-107">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="cd129-107">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd129-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cd129-108">Requirements</span></span>  
 <span data-ttu-id="cd129-109">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="cd129-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd129-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="cd129-110">See Also</span></span>  
 [<span data-ttu-id="cd129-111">ISymUnmanagedWriter (interfaz)</span><span class="sxs-lookup"><span data-stu-id="cd129-111">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 [<span data-ttu-id="cd129-112">OpenMethod (método)</span><span class="sxs-lookup"><span data-stu-id="cd129-112">OpenMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)
