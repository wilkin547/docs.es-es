---
title: ISymUnmanagedWriter::CloseMethod (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.CloseMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::CloseMethod
helpviewer_keywords:
- ISymUnmanagedWriter::CloseMethod method [.NET Framework debugging]
- CloseMethod method [.NET Framework debugging]
ms.assetid: b8025e04-f0e5-40c8-849c-8cd51323420e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a6f8c8b522aabfce3b83b6b624bd0ca9757448ad
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54666025"
---
# <a name="isymunmanagedwriterclosemethod-method"></a><span data-ttu-id="3f886-102">ISymUnmanagedWriter::CloseMethod (Método)</span><span class="sxs-lookup"><span data-stu-id="3f886-102">ISymUnmanagedWriter::CloseMethod Method</span></span>
<span data-ttu-id="3f886-103">Cierra el método actual.</span><span class="sxs-lookup"><span data-stu-id="3f886-103">Closes the current method.</span></span> <span data-ttu-id="3f886-104">Una vez cerrado un método, no hay más símbolos se pueden definir dentro de él.</span><span class="sxs-lookup"><span data-stu-id="3f886-104">Once a method is closed, no more symbols can be defined within it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f886-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3f886-105">Syntax</span></span>  
  
```  
HRESULT CloseMethod();  
```  
  
## <a name="return-value"></a><span data-ttu-id="3f886-106">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3f886-106">Return Value</span></span>  
 <span data-ttu-id="3f886-107">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="3f886-107">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f886-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3f886-108">Requirements</span></span>  
 <span data-ttu-id="3f886-109">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="3f886-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f886-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="3f886-110">See also</span></span>
- [<span data-ttu-id="3f886-111">ISymUnmanagedWriter (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3f886-111">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="3f886-112">OpenMethod (método)</span><span class="sxs-lookup"><span data-stu-id="3f886-112">OpenMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)
