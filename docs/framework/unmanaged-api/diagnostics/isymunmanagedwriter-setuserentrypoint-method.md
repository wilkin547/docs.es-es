---
title: ISymUnmanagedWriter::SetUserEntryPoint (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.SetUserEntryPoint
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::SetUserEntryPoint
helpviewer_keywords:
- ISymUnmanagedWriter::SetUserEntryPoint method [.NET Framework debugging]
- SetUserEntryPoint method [.NET Framework debugging]
ms.assetid: d4dcc575-3ac8-4453-9be1-2b24f47363d7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d14d542a8c1d8adeaf56dc1564e8e10121cd4064
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59224226"
---
# <a name="isymunmanagedwritersetuserentrypoint-method"></a><span data-ttu-id="063ee-102">ISymUnmanagedWriter::SetUserEntryPoint (Método)</span><span class="sxs-lookup"><span data-stu-id="063ee-102">ISymUnmanagedWriter::SetUserEntryPoint Method</span></span>
<span data-ttu-id="063ee-103">Especifica el método definido por el usuario que es el punto de entrada para este módulo.</span><span class="sxs-lookup"><span data-stu-id="063ee-103">Specifies the user-defined method that is the entry point for this module.</span></span> <span data-ttu-id="063ee-104">Por ejemplo, este punto de entrada podría ser el método del usuario principal en lugar de código auxiliar generado por el compilador antes de principal.</span><span class="sxs-lookup"><span data-stu-id="063ee-104">For example, this entry point could be the user's main method instead of compiler-generated stubs before main.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="063ee-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="063ee-105">Syntax</span></span>  
  
```  
HRESULT SetUserEntryPoint(  
    [in] mdMethodDef entryMethod);  
```  
  
## <a name="parameters"></a><span data-ttu-id="063ee-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="063ee-106">Parameters</span></span>  
 `entryMethod`  
 <span data-ttu-id="063ee-107">[in] Seleccione el token de metadatos para el método que es la entrada del usuario.</span><span class="sxs-lookup"><span data-stu-id="063ee-107">[in] The metadata token for the method that is the user entry point.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="063ee-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="063ee-108">Return Value</span></span>  
 <span data-ttu-id="063ee-109">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="063ee-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="063ee-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="063ee-110">Requirements</span></span>  
 <span data-ttu-id="063ee-111">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="063ee-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="063ee-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="063ee-112">See also</span></span>

- [<span data-ttu-id="063ee-113">ISymUnmanagedWriter (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="063ee-113">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
