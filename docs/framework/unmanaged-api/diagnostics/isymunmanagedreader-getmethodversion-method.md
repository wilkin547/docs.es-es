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
ms.openlocfilehash: 76d850363940ff53135fc66ec057ee67822fa40d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33424669"
---
# <a name="isymunmanagedreadergetmethodversion-method"></a><span data-ttu-id="15d1b-102">ISymUnmanagedReader::GetMethodVersion (Método)</span><span class="sxs-lookup"><span data-stu-id="15d1b-102">ISymUnmanagedReader::GetMethodVersion Method</span></span>
<span data-ttu-id="15d1b-103">Obtiene la versión del método.</span><span class="sxs-lookup"><span data-stu-id="15d1b-103">Gets the method version.</span></span> <span data-ttu-id="15d1b-104">La versión del método comienza en 1 y se incrementa cada vez que se vuelve a compilar el método.</span><span class="sxs-lookup"><span data-stu-id="15d1b-104">The method version starts at 1 and is incremented each time the method is recompiled.</span></span> <span data-ttu-id="15d1b-105">Recompilación puede realizarse sin cambios en el método.</span><span class="sxs-lookup"><span data-stu-id="15d1b-105">Recompilation can happen without changes to the method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15d1b-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="15d1b-106">Syntax</span></span>  
  
```  
HRESULT GetMethodVersion (  
    [in]  ISymUnmanagedMethod* pMethod,  
    [out] int* version);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="15d1b-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="15d1b-107">Parameters</span></span>  
 `pMethod`  
 <span data-ttu-id="15d1b-108">[in] El método para el que se va a obtener la versión.</span><span class="sxs-lookup"><span data-stu-id="15d1b-108">[in] The method for which to get the version.</span></span>  
  
 `version`  
 <span data-ttu-id="15d1b-109">[out] Un puntero a una variable que recibe la versión del método.</span><span class="sxs-lookup"><span data-stu-id="15d1b-109">[out] A pointer to a variable that receives the method version.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="15d1b-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="15d1b-110">Return Value</span></span>  
 <span data-ttu-id="15d1b-111">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="15d1b-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15d1b-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="15d1b-112">Requirements</span></span>  
 <span data-ttu-id="15d1b-113">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="15d1b-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15d1b-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="15d1b-114">See Also</span></span>  
 [<span data-ttu-id="15d1b-115">ISymUnmanagedReader (interfaz)</span><span class="sxs-lookup"><span data-stu-id="15d1b-115">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
