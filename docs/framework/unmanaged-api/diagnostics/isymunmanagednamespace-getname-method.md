---
title: ISymUnmanagedNamespace::GetName (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedNamespace.GetName
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedNamespace::GetName
helpviewer_keywords:
- ISymUnmanagedNamespace::GetName method [.NET Framework debugging]
- GetName method, ISymUnmanagedNamespace interface [.NET Framework debugging]
ms.assetid: 657bf91d-005a-4ea4-9298-04d1291c0bc3
topic_type:
- apiref
ms.openlocfilehash: eca1137fb607d64e8645de5b0afc7ca391eac763
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699266"
---
# <a name="isymunmanagednamespacegetname-method"></a><span data-ttu-id="1267e-102">ISymUnmanagedNamespace::GetName (Método)</span><span class="sxs-lookup"><span data-stu-id="1267e-102">ISymUnmanagedNamespace::GetName Method</span></span>

<span data-ttu-id="1267e-103">Obtiene el nombre de este espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="1267e-103">Gets the name of this namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1267e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1267e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
        length_is(*pcchName)] WCHAR szName[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1267e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1267e-105">Parameters</span></span>  

 `cchName`  
 <span data-ttu-id="1267e-106">de `ULONG32` Que indica el tamaño del `szName` búfer.</span><span class="sxs-lookup"><span data-stu-id="1267e-106">[in] A `ULONG32` that indicates the size of the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="1267e-107">enuncia Un puntero a un `ULONG32` que recibe el tamaño, en caracteres, del búfer necesario para contener el nombre del espacio de nombres, incluida la terminación null.</span><span class="sxs-lookup"><span data-stu-id="1267e-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the namespace name, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="1267e-108">enuncia Un puntero a un búfer que contiene el nombre del espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="1267e-108">[out] A pointer to a buffer that contains the namespace name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1267e-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="1267e-109">Return Value</span></span>  

 <span data-ttu-id="1267e-110">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="1267e-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1267e-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1267e-111">Requirements</span></span>  

 <span data-ttu-id="1267e-112">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="1267e-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1267e-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1267e-113">See also</span></span>

- [<span data-ttu-id="1267e-114">ISymUnmanagedNamespace (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1267e-114">ISymUnmanagedNamespace Interface</span></span>](isymunmanagednamespace-interface.md)
