---
title: ISymUnmanagedReader::GetMethodByVersion (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetMethodByVersion
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetMethodByVersion
helpviewer_keywords:
- ISymUnmanagedReader::GetMethodByVersion method [.NET Framework debugging]
- GetMethodByVersion method [.NET Framework debugging]
ms.assetid: 6ddb0631-4569-41b3-93e4-50fdfaa486dc
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f3210f0186401729a5bc95369e88b290ae49a634
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776995"
---
# <a name="isymunmanagedreadergetmethodbyversion-method"></a><span data-ttu-id="13b96-102">ISymUnmanagedReader::GetMethodByVersion (Método)</span><span class="sxs-lookup"><span data-stu-id="13b96-102">ISymUnmanagedReader::GetMethodByVersion Method</span></span>
<span data-ttu-id="13b96-103">Obtiene un método del lector de símbolos, dado un token de método y un número de versión de editar y copiar.</span><span class="sxs-lookup"><span data-stu-id="13b96-103">Gets a symbol reader method, given a method token and an edit-and-copy version number.</span></span> <span data-ttu-id="13b96-104">Números de versión empiezan en 1 y se incrementan cada vez que cambia el método como resultado de una operación de copia y edición.</span><span class="sxs-lookup"><span data-stu-id="13b96-104">Version numbers start at 1 and are incremented each time the method is changed as a result of an edit-and-copy operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13b96-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="13b96-105">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodByVersion (  
    [in]  mdMethodDef  token,  
    [in]  int  version,  
    [out, retval] ISymUnmanagedMethod** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="13b96-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="13b96-106">Parameters</span></span>  
 `token`  
 <span data-ttu-id="13b96-107">[in] El token del método.</span><span class="sxs-lookup"><span data-stu-id="13b96-107">[in] The method token.</span></span>  
  
 `version`  
 <span data-ttu-id="13b96-108">[in] La versión del método.</span><span class="sxs-lookup"><span data-stu-id="13b96-108">[in] The method version.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="13b96-109">[out] Un puntero a la interfaz devuelta.</span><span class="sxs-lookup"><span data-stu-id="13b96-109">[out] A pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="13b96-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="13b96-110">Return Value</span></span>  
 <span data-ttu-id="13b96-111">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="13b96-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13b96-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="13b96-112">Requirements</span></span>  
 <span data-ttu-id="13b96-113">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="13b96-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13b96-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="13b96-114">See also</span></span>

- [<span data-ttu-id="13b96-115">ISymUnmanagedReader (interfaz)</span><span class="sxs-lookup"><span data-stu-id="13b96-115">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
