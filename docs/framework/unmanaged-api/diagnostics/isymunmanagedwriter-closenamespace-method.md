---
title: ISymUnmanagedWriter::CloseNamespace (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.CloseNamespace
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::CloseNamespace
helpviewer_keywords:
- ISymUnmanagedWriter::CloseNamespace method [.NET Framework debugging]
- CloseNamespace method [.NET Framework debugging]
ms.assetid: 7f74d9c5-1377-4958-b842-6306d611cbd5
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4429d49a489871a8993d9f841d9c5e7e37a53b5e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54689684"
---
# <a name="isymunmanagedwriterclosenamespace-method"></a><span data-ttu-id="f699b-102">ISymUnmanagedWriter::CloseNamespace (Método)</span><span class="sxs-lookup"><span data-stu-id="f699b-102">ISymUnmanagedWriter::CloseNamespace Method</span></span>
<span data-ttu-id="f699b-103">Cierra la última abre el espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="f699b-103">Closes the most recently opened namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f699b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f699b-104">Syntax</span></span>  
  
```  
HRESULT CloseNamespace();  
```  
  
## <a name="return-value"></a><span data-ttu-id="f699b-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f699b-105">Return Value</span></span>  
 <span data-ttu-id="f699b-106">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="f699b-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f699b-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f699b-107">Requirements</span></span>  
 <span data-ttu-id="f699b-108">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="f699b-108">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f699b-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="f699b-109">See also</span></span>
- [<span data-ttu-id="f699b-110">ISymUnmanagedWriter (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f699b-110">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="f699b-111">OpenNamespace (método)</span><span class="sxs-lookup"><span data-stu-id="f699b-111">OpenNamespace Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-opennamespace-method.md)
