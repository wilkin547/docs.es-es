---
title: ISymUnmanagedReader::GetMethodVersion (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetMethodVersion
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetMethodVersion
helpviewer_keywords:
- GetMethodVersion method [.NET Framework debugging]
- ISymUnmanagedReader::GetMethodVersion method [.NET Framework debugging]
ms.assetid: d6f9ac84-302a-4f5e-b990-e76f4269fceb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 364742957d16f12508d2df6f4cd7f50d7956d4cb
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57479459"
---
# <a name="isymunmanagedreadergetmethodversion-method"></a><span data-ttu-id="269f5-102">ISymUnmanagedReader::GetMethodVersion (Método)</span><span class="sxs-lookup"><span data-stu-id="269f5-102">ISymUnmanagedReader::GetMethodVersion Method</span></span>
<span data-ttu-id="269f5-103">Obtiene la versión del método.</span><span class="sxs-lookup"><span data-stu-id="269f5-103">Gets the method version.</span></span> <span data-ttu-id="269f5-104">La versión del método comienza en 1 y se incrementa cada vez que se vuelve a compilar el método.</span><span class="sxs-lookup"><span data-stu-id="269f5-104">The method version starts at 1 and is incremented each time the method is recompiled.</span></span> <span data-ttu-id="269f5-105">Recompilación puede realizarse sin cambios en el método.</span><span class="sxs-lookup"><span data-stu-id="269f5-105">Recompilation can happen without changes to the method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="269f5-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="269f5-106">Syntax</span></span>  
  
```  
HRESULT GetMethodVersion (  
    [in]  ISymUnmanagedMethod* pMethod,  
    [out] int* version);  
```  
  
## <a name="parameters"></a><span data-ttu-id="269f5-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="269f5-107">Parameters</span></span>  
 `pMethod`  
 <span data-ttu-id="269f5-108">[in] El método que se va a obtener la versión.</span><span class="sxs-lookup"><span data-stu-id="269f5-108">[in] The method for which to get the version.</span></span>  
  
 `version`  
 <span data-ttu-id="269f5-109">[out] Un puntero a una variable que recibe la versión del método.</span><span class="sxs-lookup"><span data-stu-id="269f5-109">[out] A pointer to a variable that receives the method version.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="269f5-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="269f5-110">Return Value</span></span>  
 <span data-ttu-id="269f5-111">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="269f5-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="269f5-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="269f5-112">Requirements</span></span>  
 <span data-ttu-id="269f5-113">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="269f5-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="269f5-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="269f5-114">See also</span></span>
- [<span data-ttu-id="269f5-115">ISymUnmanagedReader (interfaz)</span><span class="sxs-lookup"><span data-stu-id="269f5-115">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
