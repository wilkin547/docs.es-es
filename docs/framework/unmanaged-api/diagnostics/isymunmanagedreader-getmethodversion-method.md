---
description: 'Más información acerca de: ISymUnmanagedReader:: Getmethodversion ((método)'
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
ms.openlocfilehash: 027f65f858aab3e4ad0bc0bfbffd91f6118b80b2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99764026"
---
# <a name="isymunmanagedreadergetmethodversion-method"></a><span data-ttu-id="0d270-103">ISymUnmanagedReader::GetMethodVersion (Método)</span><span class="sxs-lookup"><span data-stu-id="0d270-103">ISymUnmanagedReader::GetMethodVersion Method</span></span>

<span data-ttu-id="0d270-104">Obtiene la versión del método.</span><span class="sxs-lookup"><span data-stu-id="0d270-104">Gets the method version.</span></span> <span data-ttu-id="0d270-105">La versión del método comienza en 1 y se incrementa cada vez que se vuelve a compilar el método.</span><span class="sxs-lookup"><span data-stu-id="0d270-105">The method version starts at 1 and is incremented each time the method is recompiled.</span></span> <span data-ttu-id="0d270-106">La recompilación puede producirse sin realizar cambios en el método.</span><span class="sxs-lookup"><span data-stu-id="0d270-106">Recompilation can happen without changes to the method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d270-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0d270-107">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodVersion (  
    [in]  ISymUnmanagedMethod* pMethod,  
    [out] int* version);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0d270-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0d270-108">Parameters</span></span>  

 `pMethod`  
 <span data-ttu-id="0d270-109">de Método para el que se va a obtener la versión.</span><span class="sxs-lookup"><span data-stu-id="0d270-109">[in] The method for which to get the version.</span></span>  
  
 `version`  
 <span data-ttu-id="0d270-110">enuncia Puntero a una variable que recibe la versión del método.</span><span class="sxs-lookup"><span data-stu-id="0d270-110">[out] A pointer to a variable that receives the method version.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0d270-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="0d270-111">Return Value</span></span>  

 <span data-ttu-id="0d270-112">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="0d270-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d270-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0d270-113">Requirements</span></span>  

 <span data-ttu-id="0d270-114">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="0d270-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d270-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="0d270-115">See also</span></span>

- [<span data-ttu-id="0d270-116">ISymUnmanagedReader (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0d270-116">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
