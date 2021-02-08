---
description: 'Más información acerca de: ISymUnmanagedReader:: Getmethodbyversion ((método)'
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
ms.openlocfilehash: 6b2fa3ff3af91d59bb79029d039e5656610bebff
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99772073"
---
# <a name="isymunmanagedreadergetmethodbyversion-method"></a><span data-ttu-id="4f003-103">ISymUnmanagedReader::GetMethodByVersion (Método)</span><span class="sxs-lookup"><span data-stu-id="4f003-103">ISymUnmanagedReader::GetMethodByVersion Method</span></span>

<span data-ttu-id="4f003-104">Obtiene un método del lector de símbolos, dado un token de método y un número de versión de edición y copia.</span><span class="sxs-lookup"><span data-stu-id="4f003-104">Gets a symbol reader method, given a method token and an edit-and-copy version number.</span></span> <span data-ttu-id="4f003-105">Los números de versión se inician en 1 y se incrementan cada vez que se cambia el método como resultado de una operación de edición y copia.</span><span class="sxs-lookup"><span data-stu-id="4f003-105">Version numbers start at 1 and are incremented each time the method is changed as a result of an edit-and-copy operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f003-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4f003-106">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodByVersion (  
    [in]  mdMethodDef  token,  
    [in]  int  version,  
    [out, retval] ISymUnmanagedMethod** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4f003-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4f003-107">Parameters</span></span>  

 `token`  
 <span data-ttu-id="4f003-108">de Token del método.</span><span class="sxs-lookup"><span data-stu-id="4f003-108">[in] The method token.</span></span>  
  
 `version`  
 <span data-ttu-id="4f003-109">de Versión del método.</span><span class="sxs-lookup"><span data-stu-id="4f003-109">[in] The method version.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="4f003-110">enuncia Puntero a la interfaz devuelta.</span><span class="sxs-lookup"><span data-stu-id="4f003-110">[out] A pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4f003-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="4f003-111">Return Value</span></span>  

 <span data-ttu-id="4f003-112">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="4f003-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f003-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4f003-113">Requirements</span></span>  

 <span data-ttu-id="4f003-114">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="4f003-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f003-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="4f003-115">See also</span></span>

- [<span data-ttu-id="4f003-116">ISymUnmanagedReader (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4f003-116">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
