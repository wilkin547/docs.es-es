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
ms.openlocfilehash: 8ee4c1bffccb44d15fa53eb3d4d6c0fcdc3e7697
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614973"
---
# <a name="isymunmanagedreadergetmethodversion-method"></a><span data-ttu-id="0658c-102">ISymUnmanagedReader::GetMethodVersion (Método)</span><span class="sxs-lookup"><span data-stu-id="0658c-102">ISymUnmanagedReader::GetMethodVersion Method</span></span>
<span data-ttu-id="0658c-103">Obtiene la versión del método.</span><span class="sxs-lookup"><span data-stu-id="0658c-103">Gets the method version.</span></span> <span data-ttu-id="0658c-104">La versión del método comienza en 1 y se incrementa cada vez que se vuelve a compilar el método.</span><span class="sxs-lookup"><span data-stu-id="0658c-104">The method version starts at 1 and is incremented each time the method is recompiled.</span></span> <span data-ttu-id="0658c-105">La recompilación puede producirse sin realizar cambios en el método.</span><span class="sxs-lookup"><span data-stu-id="0658c-105">Recompilation can happen without changes to the method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0658c-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0658c-106">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodVersion (  
    [in]  ISymUnmanagedMethod* pMethod,  
    [out] int* version);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0658c-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0658c-107">Parameters</span></span>  
 `pMethod`  
 <span data-ttu-id="0658c-108">de Método para el que se va a obtener la versión.</span><span class="sxs-lookup"><span data-stu-id="0658c-108">[in] The method for which to get the version.</span></span>  
  
 `version`  
 <span data-ttu-id="0658c-109">enuncia Puntero a una variable que recibe la versión del método.</span><span class="sxs-lookup"><span data-stu-id="0658c-109">[out] A pointer to a variable that receives the method version.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0658c-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="0658c-110">Return Value</span></span>  
 <span data-ttu-id="0658c-111">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="0658c-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0658c-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0658c-112">Requirements</span></span>  
 <span data-ttu-id="0658c-113">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="0658c-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0658c-114">Consulta también</span><span class="sxs-lookup"><span data-stu-id="0658c-114">See also</span></span>

- [<span data-ttu-id="0658c-115">ISymUnmanagedReader (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0658c-115">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
