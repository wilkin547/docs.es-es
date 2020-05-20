---
title: ISymUnmanagedConstant::GetName (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedConstant.GetName
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedConstant::GetName
helpviewer_keywords:
- ISymUnmanagedConstant::GetName method [.NET Framework debugging]
- GetName method, ISymUnmanagedConstant interface [.NET Framework debugging]
ms.assetid: cbaca4e1-4473-459b-ba34-f1f59ce7c0ba
topic_type:
- apiref
ms.openlocfilehash: 2dd70693528904459a34689dbad944c65c971254
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441648"
---
# <a name="isymunmanagedconstantgetname-method"></a><span data-ttu-id="6a9e4-102">ISymUnmanagedConstant::GetName (Método)</span><span class="sxs-lookup"><span data-stu-id="6a9e4-102">ISymUnmanagedConstant::GetName Method</span></span>
<span data-ttu-id="6a9e4-103">Obtiene el nombre de la constante.</span><span class="sxs-lookup"><span data-stu-id="6a9e4-103">Gets the name of the constant.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a9e4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6a9e4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
        length_is(*pcchName)] WCHAR szName[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6a9e4-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6a9e4-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="6a9e4-106">de Longitud del búfer al que apunta el `szName` parámetro.</span><span class="sxs-lookup"><span data-stu-id="6a9e4-106">[in] The length of the buffer that the `szName` parameter points to.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="6a9e4-107">enuncia Un puntero a un `ULONG32` que recibe el tamaño, en caracteres, del búfer necesario para contener el nombre, incluida la terminación null.</span><span class="sxs-lookup"><span data-stu-id="6a9e4-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the name, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="6a9e4-108">enuncia Búfer que almacena el nombre.</span><span class="sxs-lookup"><span data-stu-id="6a9e4-108">[out] The buffer that stores the name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6a9e4-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="6a9e4-109">Return Value</span></span>  
 <span data-ttu-id="6a9e4-110">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="6a9e4-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6a9e4-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6a9e4-111">Requirements</span></span>  
 <span data-ttu-id="6a9e4-112">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="6a9e4-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a9e4-113">Consulta también</span><span class="sxs-lookup"><span data-stu-id="6a9e4-113">See also</span></span>

- [<span data-ttu-id="6a9e4-114">ISymUnmanagedConstant (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="6a9e4-114">ISymUnmanagedConstant Interface</span></span>](isymunmanagedconstant-interface.md)
- [<span data-ttu-id="6a9e4-115">GetSignature (Método)</span><span class="sxs-lookup"><span data-stu-id="6a9e4-115">GetSignature Method</span></span>](isymunmanagedconstant-getsignature-method.md)
- [<span data-ttu-id="6a9e4-116">Método GetValue</span><span class="sxs-lookup"><span data-stu-id="6a9e4-116">GetValue Method</span></span>](isymunmanagedconstant-getvalue-method.md)
