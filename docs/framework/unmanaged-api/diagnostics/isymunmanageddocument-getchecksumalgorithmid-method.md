---
description: 'Más información acerca de: ISymUnmanagedDocument:: Getchecksumalgorithmid ((método)'
title: ISymUnmanagedDocument::GetCheckSumAlgorithmId (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetCheckSumAlgorithmId
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetCheckSumAlgorithmId
helpviewer_keywords:
- ISymUnmanagedDocument::GetCheckSumAlgorithmId method [.NET Framework debugging]
- GetCheckSumAlgorithmId method [.NET Framework debugging]
ms.assetid: c7f941cd-e25b-4b85-b1ce-5f77c9208fa9
topic_type:
- apiref
ms.openlocfilehash: 835f56875a1adc3a3b6617a5a0b280f60f918236
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99772125"
---
# <a name="isymunmanageddocumentgetchecksumalgorithmid-method"></a><span data-ttu-id="0849f-103">ISymUnmanagedDocument::GetCheckSumAlgorithmId (Método)</span><span class="sxs-lookup"><span data-stu-id="0849f-103">ISymUnmanagedDocument::GetCheckSumAlgorithmId Method</span></span>

<span data-ttu-id="0849f-104">Obtiene el identificador del algoritmo de suma de comprobación o devuelve un GUID de todos los ceros si no hay ninguna suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="0849f-104">Gets the checksum algorithm identifier, or returns a GUID of all zeros if there is no checksum.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0849f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0849f-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCheckSumAlgorithmId(  
    [out, retval] GUID*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0849f-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0849f-106">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="0849f-107">enuncia Puntero a una variable que recibe el identificador del algoritmo de suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="0849f-107">[out] A pointer to a variable that receives the checksum algorithm identifier.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0849f-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="0849f-108">Return Value</span></span>  

 <span data-ttu-id="0849f-109">S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="0849f-109">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0849f-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="0849f-110">See also</span></span>

- [<span data-ttu-id="0849f-111">ISymUnmanagedDocument (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0849f-111">ISymUnmanagedDocument Interface</span></span>](isymunmanageddocument-interface.md)
