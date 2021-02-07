---
description: 'Más información acerca de: ISymUnmanagedDocument:: GetURL (método)'
title: ISymUnmanagedDocument::GetURL (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetURL
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetURL
helpviewer_keywords:
- GetURL method [.NET Framework debugging]
- ISymUnmanagedDocument::GetURL method [.NET Framework debugging]
ms.assetid: 60600178-c2b5-4cab-b3a5-f0f61acebaf1
topic_type:
- apiref
ms.openlocfilehash: b39b36054d80f9ad2f9dd076e2055ccbc6526973
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99710197"
---
# <a name="isymunmanageddocumentgeturl-method"></a><span data-ttu-id="3874f-103">ISymUnmanagedDocument::GetURL (Método)</span><span class="sxs-lookup"><span data-stu-id="3874f-103">ISymUnmanagedDocument::GetURL Method</span></span>

<span data-ttu-id="3874f-104">Devuelve el localizador uniforme de recursos (URL) para este documento.</span><span class="sxs-lookup"><span data-stu-id="3874f-104">Returns the uniform resource locator (URL) for this document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3874f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3874f-105">Syntax</span></span>  
  
```cpp  
HRESULT GetURL(  
    [in]  ULONG32  cchUrl,  
    [out] ULONG32  *pcchUrl,  
    [out, size_is(cchUrl), length_is(*pcchUrl)] WCHAR szUrl[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3874f-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3874f-106">Parameters</span></span>  

 `cchUrl`  
 <span data-ttu-id="3874f-107">[in] Tamaño, en caracteres, del búfer de `szURL`.</span><span class="sxs-lookup"><span data-stu-id="3874f-107">[in] The size, in characters, of the `szURL` buffer.</span></span>  
  
 `pcchUrl`  
 <span data-ttu-id="3874f-108">enuncia Puntero a una variable que recibe el tamaño de la dirección URL, incluida la terminación null.</span><span class="sxs-lookup"><span data-stu-id="3874f-108">[out] A pointer to a variable that receives the size of the URL, including the null termination.</span></span>  
  
 `szUrl`  
 <span data-ttu-id="3874f-109">enuncia Búfer que contiene la dirección URL.</span><span class="sxs-lookup"><span data-stu-id="3874f-109">[out] The buffer containing the URL.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3874f-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3874f-110">Return Value</span></span>  

 <span data-ttu-id="3874f-111">S_OK si el método se ejecuta correctamente; de lo contrario, un código de error.</span><span class="sxs-lookup"><span data-stu-id="3874f-111">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3874f-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="3874f-112">See also</span></span>

- [<span data-ttu-id="3874f-113">ISymUnmanagedDocument (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3874f-113">ISymUnmanagedDocument Interface</span></span>](isymunmanageddocument-interface.md)
