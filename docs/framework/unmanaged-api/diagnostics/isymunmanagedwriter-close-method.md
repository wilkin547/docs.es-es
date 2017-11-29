---
title: "ISymUnmanagedWriter::Close (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.Close
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::Close
helpviewer_keywords:
- Close method, ISymUnmanagedWriter interface [.NET Framework debugging]
- ISymUnmanagedWriter::Close method [.NET Framework debugging]
ms.assetid: 4cce59e1-80b9-4fc4-b3aa-126f1c5876bc
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ad0cec59531a7e22d0a4d2220cb2dfcdd8f27596
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedwriterclose-method"></a><span data-ttu-id="1fea3-102">ISymUnmanagedWriter::Close (Método)</span><span class="sxs-lookup"><span data-stu-id="1fea3-102">ISymUnmanagedWriter::Close Method</span></span>
<span data-ttu-id="1fea3-103">Cierra el escritor de símbolos después de confirmar los símbolos al almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="1fea3-103">Closes the symbol writer after committing the symbols to the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1fea3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1fea3-104">Syntax</span></span>  
  
```  
HRESULT Close();  
```  
  
## <a name="return-value"></a><span data-ttu-id="1fea3-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="1fea3-105">Return Value</span></span>  
 <span data-ttu-id="1fea3-106">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="1fea3-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1fea3-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1fea3-107">Remarks</span></span>  
 <span data-ttu-id="1fea3-108">Después de esta llamada, el escritor de símbolos deja de ser válido para futuras actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="1fea3-108">After this call, the symbol writer becomes invalid for further updates.</span></span> <span data-ttu-id="1fea3-109">Para cerrar el escritor de símbolos sin confirmar los símbolos, utilice el [ISymUnmanagedWriter:: Abort](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-abort-method.md) método en su lugar.</span><span class="sxs-lookup"><span data-stu-id="1fea3-109">To close the symbol writer without committing the symbols, use the [ISymUnmanagedWriter::Abort](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-abort-method.md) method instead.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1fea3-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1fea3-110">Requirements</span></span>  
 <span data-ttu-id="1fea3-111">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="1fea3-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1fea3-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="1fea3-112">See Also</span></span>  
 [<span data-ttu-id="1fea3-113">ISymUnmanagedWriter (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1fea3-113">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
