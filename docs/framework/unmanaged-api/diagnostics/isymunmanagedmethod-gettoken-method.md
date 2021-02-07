---
description: 'Más información sobre: ISymUnmanagedMethod:: GetToken (método)'
title: ISymUnmanagedMethod::GetToken (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetToken
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetToken
helpviewer_keywords:
- ISymUnmanagedMethod::GetToken method [.NET Framework debugging]
- GetToken method, ISymUnmanagedMethod interface [.NET Framework debugging]
ms.assetid: 4effbe95-c36e-4a45-8b2a-ee21339415fb
topic_type:
- apiref
ms.openlocfilehash: fde9936a6e79b9d1fff5b38ee7242cf5bb71369d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99721312"
---
# <a name="isymunmanagedmethodgettoken-method"></a><span data-ttu-id="ab595-103">ISymUnmanagedMethod::GetToken (Método)</span><span class="sxs-lookup"><span data-stu-id="ab595-103">ISymUnmanagedMethod::GetToken Method</span></span>

<span data-ttu-id="ab595-104">Devuelve el símbolo (token) de metadatos para este método.</span><span class="sxs-lookup"><span data-stu-id="ab595-104">Returns the metadata token for this method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab595-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ab595-105">Syntax</span></span>  
  
```cpp  
HRESULT GetToken(  
   [out, retval]  mdMethodDef  *pToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ab595-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ab595-106">Parameters</span></span>  

 `pToken`  
 <span data-ttu-id="ab595-107">enuncia Un puntero a un `mdMethodDef` que recibe el tamaño, en caracteres, del búfer necesario para contener los metadatos.</span><span class="sxs-lookup"><span data-stu-id="ab595-107">[out] A pointer to a `mdMethodDef` that receives the size, in characters, of the buffer required to contain the metadata.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ab595-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ab595-108">Return Value</span></span>  

 <span data-ttu-id="ab595-109">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="ab595-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ab595-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ab595-110">Requirements</span></span>  

 <span data-ttu-id="ab595-111">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="ab595-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab595-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="ab595-112">See also</span></span>

- [<span data-ttu-id="ab595-113">ISymUnmanagedMethod (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ab595-113">ISymUnmanagedMethod Interface</span></span>](isymunmanagedmethod-interface.md)
