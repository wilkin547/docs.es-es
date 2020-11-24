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
ms.openlocfilehash: 64e6b9a1942e9a69e43de3d2f09564814328ec08
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95689620"
---
# <a name="isymunmanagedreadergetmethodbyversion-method"></a><span data-ttu-id="e0a24-102">ISymUnmanagedReader::GetMethodByVersion (Método)</span><span class="sxs-lookup"><span data-stu-id="e0a24-102">ISymUnmanagedReader::GetMethodByVersion Method</span></span>

<span data-ttu-id="e0a24-103">Obtiene un método del lector de símbolos, dado un token de método y un número de versión de edición y copia.</span><span class="sxs-lookup"><span data-stu-id="e0a24-103">Gets a symbol reader method, given a method token and an edit-and-copy version number.</span></span> <span data-ttu-id="e0a24-104">Los números de versión se inician en 1 y se incrementan cada vez que se cambia el método como resultado de una operación de edición y copia.</span><span class="sxs-lookup"><span data-stu-id="e0a24-104">Version numbers start at 1 and are incremented each time the method is changed as a result of an edit-and-copy operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0a24-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e0a24-105">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodByVersion (  
    [in]  mdMethodDef  token,  
    [in]  int  version,  
    [out, retval] ISymUnmanagedMethod** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e0a24-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e0a24-106">Parameters</span></span>  

 `token`  
 <span data-ttu-id="e0a24-107">de Token del método.</span><span class="sxs-lookup"><span data-stu-id="e0a24-107">[in] The method token.</span></span>  
  
 `version`  
 <span data-ttu-id="e0a24-108">de Versión del método.</span><span class="sxs-lookup"><span data-stu-id="e0a24-108">[in] The method version.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="e0a24-109">enuncia Puntero a la interfaz devuelta.</span><span class="sxs-lookup"><span data-stu-id="e0a24-109">[out] A pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e0a24-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e0a24-110">Return Value</span></span>  

 <span data-ttu-id="e0a24-111">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="e0a24-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0a24-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e0a24-112">Requirements</span></span>  

 <span data-ttu-id="e0a24-113">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="e0a24-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0a24-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e0a24-114">See also</span></span>

- [<span data-ttu-id="e0a24-115">ISymUnmanagedReader (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e0a24-115">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
