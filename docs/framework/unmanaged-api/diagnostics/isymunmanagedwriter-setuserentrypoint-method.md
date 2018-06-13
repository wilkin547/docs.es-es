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
ms.openlocfilehash: 9ec44d4c2757555c74fe7fc27c26cc5fc87c4517
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33426692"
---
# <a name="isymunmanagedwritersetuserentrypoint-method"></a><span data-ttu-id="d111e-102">ISymUnmanagedWriter::SetUserEntryPoint (Método)</span><span class="sxs-lookup"><span data-stu-id="d111e-102">ISymUnmanagedWriter::SetUserEntryPoint Method</span></span>
<span data-ttu-id="d111e-103">Especifica el método definido por el usuario que es el punto de entrada para este módulo.</span><span class="sxs-lookup"><span data-stu-id="d111e-103">Specifies the user-defined method that is the entry point for this module.</span></span> <span data-ttu-id="d111e-104">Por ejemplo, este punto de entrada podría ser el método del usuario principal en lugar de código auxiliar generado por el compilador antes de principal.</span><span class="sxs-lookup"><span data-stu-id="d111e-104">For example, this entry point could be the user's main method instead of compiler-generated stubs before main.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d111e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d111e-105">Syntax</span></span>  
  
```  
HRESULT SetUserEntryPoint(  
    [in] mdMethodDef entryMethod);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d111e-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d111e-106">Parameters</span></span>  
 `entryMethod`  
 <span data-ttu-id="d111e-107">[in] Seleccione el símbolo (token) de metadatos del método que es la entrada del usuario.</span><span class="sxs-lookup"><span data-stu-id="d111e-107">[in] The metadata token for the method that is the user entry point.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d111e-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d111e-108">Return Value</span></span>  
 <span data-ttu-id="d111e-109">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="d111e-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d111e-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d111e-110">Requirements</span></span>  
 <span data-ttu-id="d111e-111">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="d111e-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d111e-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="d111e-112">See Also</span></span>  
 [<span data-ttu-id="d111e-113">ISymUnmanagedWriter (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d111e-113">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
