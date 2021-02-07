---
description: 'Más información sobre: ISymUnmanagedVariable:: Getsignature ((método)'
title: ISymUnmanagedVariable::GetSignature (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetSignature
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetSignature
helpviewer_keywords:
- GetSignature method, ISymUnmanagedVariable interface [.NET Framework debugging]
- ISymUnmanagedVariable::GetSignature method [.NET Framework debugging]
ms.assetid: 78c1ba28-a410-4360-805c-23a95408964a
topic_type:
- apiref
ms.openlocfilehash: 6e8242581cf2d59563b6193ed7c7686292cbf775
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99762739"
---
# <a name="isymunmanagedvariablegetsignature-method"></a><span data-ttu-id="445e9-103">ISymUnmanagedVariable::GetSignature (Método)</span><span class="sxs-lookup"><span data-stu-id="445e9-103">ISymUnmanagedVariable::GetSignature Method</span></span>

<span data-ttu-id="445e9-104">Obtiene la firma de esta variable.</span><span class="sxs-lookup"><span data-stu-id="445e9-104">Gets the signature of this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="445e9-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="445e9-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSignature(  
    [in]  ULONG32  cSig,  
    [out] ULONG32  *pcSig,  
    [out, size_is(cSig),  
        length_is(*pcSig)] BYTE sig[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="445e9-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="445e9-106">Parameters</span></span>  

 `cSig`  
 <span data-ttu-id="445e9-107">de Longitud del búfer al que apunta el `sig` parámetro.</span><span class="sxs-lookup"><span data-stu-id="445e9-107">[in] The length of the buffer pointed to by the `sig` parameter.</span></span>  
  
 `pcSig`  
 <span data-ttu-id="445e9-108">enuncia Un puntero a un `ULONG32` que recibe el tamaño, en caracteres, del búfer necesario para contener la firma.</span><span class="sxs-lookup"><span data-stu-id="445e9-108">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the signature.</span></span>  
  
 `sig`  
 <span data-ttu-id="445e9-109">enuncia Búfer que almacena la firma.</span><span class="sxs-lookup"><span data-stu-id="445e9-109">[out] The buffer that stores the signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="445e9-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="445e9-110">Return Value</span></span>  

 <span data-ttu-id="445e9-111">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="445e9-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="445e9-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="445e9-112">Requirements</span></span>  

 <span data-ttu-id="445e9-113">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="445e9-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="445e9-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="445e9-114">See also</span></span>

- [<span data-ttu-id="445e9-115">ISymUnmanagedVariable (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="445e9-115">ISymUnmanagedVariable Interface</span></span>](isymunmanagedvariable-interface.md)
