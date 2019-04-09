---
title: ISymUnmanagedReader::GetSymAttribute (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetSymAttribute
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetSymAttribute
helpviewer_keywords:
- GetSymAttribute method [.NET Framework debugging]
- ISymUnmanagedReader::GetSymAttribute method [.NET Framework debugging]
ms.assetid: c675ce7e-76e7-45ff-8273-3b6489a2767c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 89831261c5da156343cb098ace715495ddafccaf
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59086096"
---
# <a name="isymunmanagedreadergetsymattribute-method"></a><span data-ttu-id="9e921-102">ISymUnmanagedReader::GetSymAttribute (Método)</span><span class="sxs-lookup"><span data-stu-id="9e921-102">ISymUnmanagedReader::GetSymAttribute Method</span></span>
<span data-ttu-id="9e921-103">Obtiene un atributo personalizado basándose en su nombre.</span><span class="sxs-lookup"><span data-stu-id="9e921-103">Gets a custom attribute based upon its name.</span></span> <span data-ttu-id="9e921-104">A diferencia de los atributos personalizados de los metadatos, estos atributos personalizados se encuentran en el almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="9e921-104">Unlike metadata custom attributes, these custom attributes are held in the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e921-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9e921-105">Syntax</span></span>  
  
```  
HRESULT GetSymAttribute (  
    [in]  mdToken  parent,  
    [in]  WCHAR    *name,  
    [in]  ULONG32  cBuffer,  
    [out] ULONG32  *pcBuffer,  
    [out, size_is (cBuffer),  
        length_is (*pcBuffer)] BYTE buffer[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9e921-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9e921-106">Parameters</span></span>  
 `parent`  
 <span data-ttu-id="9e921-107">[in] El token de metadatos para el objeto que se solicita el atributo.</span><span class="sxs-lookup"><span data-stu-id="9e921-107">[in] The metadata token for the object for which the attribute is requested.</span></span>  
  
 `name`  
 <span data-ttu-id="9e921-108">[in] Un puntero a la variable que indica el atributo para recuperar.</span><span class="sxs-lookup"><span data-stu-id="9e921-108">[in] A pointer to the variable that indicates the attribute to retrieve.</span></span>  
  
 `cBuffer`  
 <span data-ttu-id="9e921-109">[in] Tamaño de la matriz `buffer`.</span><span class="sxs-lookup"><span data-stu-id="9e921-109">[in] The size of the `buffer` array.</span></span>  
  
 `pcBuffer`  
 <span data-ttu-id="9e921-110">[out] Un puntero a la variable que recibe la longitud de los datos del atributo.</span><span class="sxs-lookup"><span data-stu-id="9e921-110">[out] A pointer to the variable that receives the length of the attribute data.</span></span>  
  
 `buffer`  
 <span data-ttu-id="9e921-111">[out] Un puntero a la variable que recibe los datos del atributo.</span><span class="sxs-lookup"><span data-stu-id="9e921-111">[out] A pointer to the variable that receives the attribute data.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9e921-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="9e921-112">Return Value</span></span>  
 <span data-ttu-id="9e921-113">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="9e921-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e921-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9e921-114">Requirements</span></span>  
 <span data-ttu-id="9e921-115">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="9e921-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e921-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="9e921-116">See also</span></span>

- [<span data-ttu-id="9e921-117">ISymUnmanagedReader (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9e921-117">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
