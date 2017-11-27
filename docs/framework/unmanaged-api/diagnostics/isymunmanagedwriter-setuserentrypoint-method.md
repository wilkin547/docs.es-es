---
title: "ISymUnmanagedWriter::SetUserEntryPoint (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.SetUserEntryPoint
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::SetUserEntryPoint
helpviewer_keywords:
- ISymUnmanagedWriter::SetUserEntryPoint method [.NET Framework debugging]
- SetUserEntryPoint method [.NET Framework debugging]
ms.assetid: d4dcc575-3ac8-4453-9be1-2b24f47363d7
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: be7f348237fdcf0a136d34ce3b6b8548c16d5547
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedwritersetuserentrypoint-method"></a><span data-ttu-id="5f2f2-102">ISymUnmanagedWriter::SetUserEntryPoint (Método)</span><span class="sxs-lookup"><span data-stu-id="5f2f2-102">ISymUnmanagedWriter::SetUserEntryPoint Method</span></span>
<span data-ttu-id="5f2f2-103">Especifica el método definido por el usuario que es el punto de entrada para este módulo.</span><span class="sxs-lookup"><span data-stu-id="5f2f2-103">Specifies the user-defined method that is the entry point for this module.</span></span> <span data-ttu-id="5f2f2-104">Por ejemplo, este punto de entrada podría ser el método del usuario principal en lugar de código auxiliar generado por el compilador antes de principal.</span><span class="sxs-lookup"><span data-stu-id="5f2f2-104">For example, this entry point could be the user's main method instead of compiler-generated stubs before main.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f2f2-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5f2f2-105">Syntax</span></span>  
  
```  
HRESULT SetUserEntryPoint(  
    [in] mdMethodDef entryMethod);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5f2f2-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5f2f2-106">Parameters</span></span>  
 `entryMethod`  
 <span data-ttu-id="5f2f2-107">[in] Seleccione el símbolo (token) de metadatos del método que es la entrada del usuario.</span><span class="sxs-lookup"><span data-stu-id="5f2f2-107">[in] The metadata token for the method that is the user entry point.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5f2f2-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="5f2f2-108">Return Value</span></span>  
 <span data-ttu-id="5f2f2-109">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="5f2f2-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f2f2-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5f2f2-110">Requirements</span></span>  
 <span data-ttu-id="5f2f2-111">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="5f2f2-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f2f2-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="5f2f2-112">See Also</span></span>  
 [<span data-ttu-id="5f2f2-113">ISymUnmanagedWriter (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5f2f2-113">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
