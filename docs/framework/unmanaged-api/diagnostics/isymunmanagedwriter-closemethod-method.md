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
ms.openlocfilehash: 71be697a8a1decd9b5f780d047c3dbb397e351d0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33426898"
---
# <a name="isymunmanagedwriterclosemethod-method"></a><span data-ttu-id="6b7e7-102">ISymUnmanagedWriter::CloseMethod (Método)</span><span class="sxs-lookup"><span data-stu-id="6b7e7-102">ISymUnmanagedWriter::CloseMethod Method</span></span>
<span data-ttu-id="6b7e7-103">Cierra el método actual.</span><span class="sxs-lookup"><span data-stu-id="6b7e7-103">Closes the current method.</span></span> <span data-ttu-id="6b7e7-104">Una vez que se cierra un método, no se puede definir ningún símbolo más dentro de él.</span><span class="sxs-lookup"><span data-stu-id="6b7e7-104">Once a method is closed, no more symbols can be defined within it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b7e7-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6b7e7-105">Syntax</span></span>  
  
```  
HRESULT CloseMethod();  
```  
  
## <a name="return-value"></a><span data-ttu-id="6b7e7-106">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="6b7e7-106">Return Value</span></span>  
 <span data-ttu-id="6b7e7-107">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="6b7e7-107">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b7e7-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6b7e7-108">Requirements</span></span>  
 <span data-ttu-id="6b7e7-109">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="6b7e7-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b7e7-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="6b7e7-110">See Also</span></span>  
 [<span data-ttu-id="6b7e7-111">ISymUnmanagedWriter (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6b7e7-111">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 [<span data-ttu-id="6b7e7-112">OpenMethod (método)</span><span class="sxs-lookup"><span data-stu-id="6b7e7-112">OpenMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)
