---
description: 'Más información acerca de: ISymUnmanagedDocument:: getChecksum ((método)'
title: ISymUnmanagedDocument::GetCheckSum (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetCheckSum
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetCheckSum
helpviewer_keywords:
- ISymUnmanagedDocument::GetCheckSum method [.NET Framework debugging]
- GetCheckSum method [.NET Framework debugging]
ms.assetid: 9bc881b3-e2ce-48a7-ad69-17eaaa304120
topic_type:
- apiref
ms.openlocfilehash: 9f9a42e58b22661a2233fcb457b9b42b0d6a3d1a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99737693"
---
# <a name="isymunmanageddocumentgetchecksum-method"></a><span data-ttu-id="3dfa1-103">ISymUnmanagedDocument::GetCheckSum (Método)</span><span class="sxs-lookup"><span data-stu-id="3dfa1-103">ISymUnmanagedDocument::GetCheckSum Method</span></span>

<span data-ttu-id="3dfa1-104">Obtiene la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="3dfa1-104">Gets the checksum.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3dfa1-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3dfa1-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCheckSum(  
    [in]  ULONG32  cData,  
    [out] ULONG32  *pcData,  
    [out, size_is(cData), length_is(*pcData)] BYTE data[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3dfa1-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3dfa1-106">Parameters</span></span>  

 `cData`  
 <span data-ttu-id="3dfa1-107">de Longitud del búfer proporcionado por el parámetro. `data`</span><span class="sxs-lookup"><span data-stu-id="3dfa1-107">[in] The length of the buffer provided by the `data` parameter</span></span>  
  
 `pcData`  
 <span data-ttu-id="3dfa1-108">enuncia Tamaño y longitud de la suma de comprobación, en bytes.</span><span class="sxs-lookup"><span data-stu-id="3dfa1-108">[out] The size and length of the checksum, in bytes.</span></span>  
  
 `data`  
 <span data-ttu-id="3dfa1-109">enuncia Búfer que recibe la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="3dfa1-109">[out] The buffer that receives the checksum.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3dfa1-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3dfa1-110">Return Value</span></span>  

 <span data-ttu-id="3dfa1-111">S_OK si el método se ejecuta correctamente; de lo contrario, un código de error.</span><span class="sxs-lookup"><span data-stu-id="3dfa1-111">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3dfa1-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="3dfa1-112">See also</span></span>

- [<span data-ttu-id="3dfa1-113">ISymUnmanagedDocument (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3dfa1-113">ISymUnmanagedDocument Interface</span></span>](isymunmanageddocument-interface.md)
