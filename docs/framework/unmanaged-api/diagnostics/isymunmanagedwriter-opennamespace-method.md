---
title: "ISymUnmanagedWriter::OpenNamespace (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.OpenNamespace
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::OpenNamespace
helpviewer_keywords:
- ISymUnmanagedWriter::OpenNamespace method [.NET Framework debugging]
- OpenNamespace method [.NET Framework debugging]
ms.assetid: 426f4e4f-e60d-4ad1-b546-a10e3c55c283
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: e3dffd9605bd238446156d7a32e8e668ddd80916
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedwriteropennamespace-method"></a><span data-ttu-id="2ea27-102">ISymUnmanagedWriter::OpenNamespace (Método)</span><span class="sxs-lookup"><span data-stu-id="2ea27-102">ISymUnmanagedWriter::OpenNamespace Method</span></span>
<span data-ttu-id="2ea27-103">Abre un nuevo espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="2ea27-103">Opens a new namespace.</span></span> <span data-ttu-id="2ea27-104">Llamar a este método antes de definir métodos o variables que ocupan un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="2ea27-104">Call this method before defining methods or variables that occupy a namespace.</span></span> <span data-ttu-id="2ea27-105">Espacios de nombres se pueden anidar.</span><span class="sxs-lookup"><span data-stu-id="2ea27-105">Namespaces can be nested.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ea27-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2ea27-106">Syntax</span></span>  
  
```  
HRESULT OpenNamespace(  
    [in] const WCHAR *name);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2ea27-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2ea27-107">Parameters</span></span>  
 `name`  
 <span data-ttu-id="2ea27-108">[in] Un puntero al nombre del espacio de nombres nuevo.</span><span class="sxs-lookup"><span data-stu-id="2ea27-108">[in] A pointer to the name of the new namespace.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2ea27-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="2ea27-109">Return Value</span></span>  
 <span data-ttu-id="2ea27-110">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="2ea27-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ea27-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2ea27-111">Requirements</span></span>  
 <span data-ttu-id="2ea27-112">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="2ea27-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ea27-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="2ea27-113">See Also</span></span>  
 [<span data-ttu-id="2ea27-114">ISymUnmanagedWriter (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2ea27-114">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 [<span data-ttu-id="2ea27-115">CloseNamespace (método)</span><span class="sxs-lookup"><span data-stu-id="2ea27-115">CloseNamespace Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closenamespace-method.md)
