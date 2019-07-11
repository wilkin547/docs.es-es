---
title: ISymUnmanagedReader2::GetMethodByVersionPreRemap (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader2.GetMethodByVersionPreRemap
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader2::GetMethodByVersionPreRemap
helpviewer_keywords:
- GetMethodByVersionPreRemap method [.NET Framework debugging]
- ISymUnmanagedReader2::GetMethodByVersionPreRemap method [.NET Framework debugging]
ms.assetid: 0d144ed4-bdb0-4cac-960c-cb90f4dca173
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 06b8ebf26794baa1d957cc47d1179283611b62d5
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67736676"
---
# <a name="isymunmanagedreader2getmethodbyversionpreremap-method"></a><span data-ttu-id="916d9-102">ISymUnmanagedReader2::GetMethodByVersionPreRemap (Método)</span><span class="sxs-lookup"><span data-stu-id="916d9-102">ISymUnmanagedReader2::GetMethodByVersionPreRemap Method</span></span>
<span data-ttu-id="916d9-103">Obtiene un método del lector de símbolos, dado un token de método y un número de versión de editar y continuar.</span><span class="sxs-lookup"><span data-stu-id="916d9-103">Gets a symbol reader method, given a method token and an edit-and-continue version number.</span></span> <span data-ttu-id="916d9-104">Números de versión empiezan en 1 y se incrementan cada vez que cambia el método como resultado de una operación de editar y continuar.</span><span class="sxs-lookup"><span data-stu-id="916d9-104">Version numbers start at 1 and are incremented each time the method is changed as a result of an edit-and-continue operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="916d9-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="916d9-105">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodByVersionPreRemap(  
    [in]  mdMethodDef token,  
    [in]  int version,  
    [out, retval] ISymUnmanagedMethod** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="916d9-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="916d9-106">Parameters</span></span>  
 `token`  
 <span data-ttu-id="916d9-107">[in] El token de metadatos del método.</span><span class="sxs-lookup"><span data-stu-id="916d9-107">[in] The method metadata token.</span></span>  
  
 `version`  
 <span data-ttu-id="916d9-108">[in] La versión del método.</span><span class="sxs-lookup"><span data-stu-id="916d9-108">[in] The method version.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="916d9-109">[out] Un puntero a la devuelta [ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) interfaz.</span><span class="sxs-lookup"><span data-stu-id="916d9-109">[out] A pointer to the returned [ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="916d9-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="916d9-110">Return Value</span></span>  
 <span data-ttu-id="916d9-111">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="916d9-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="916d9-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="916d9-112">Requirements</span></span>  
 <span data-ttu-id="916d9-113">**Encabezado**: CorSym.idl.</span><span class="sxs-lookup"><span data-stu-id="916d9-113">**Header:** CorSym.idl.</span></span> <span data-ttu-id="916d9-114">CorSym.h</span><span class="sxs-lookup"><span data-stu-id="916d9-114">CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="916d9-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="916d9-115">See also</span></span>

- [<span data-ttu-id="916d9-116">ISymUnmanagedReader2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="916d9-116">ISymUnmanagedReader2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)
