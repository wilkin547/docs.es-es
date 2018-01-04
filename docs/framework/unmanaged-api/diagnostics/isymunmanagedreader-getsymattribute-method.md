---
title: "ISymUnmanagedReader::GetSymAttribute (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReader.GetSymAttribute
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReader::GetSymAttribute
helpviewer_keywords:
- GetSymAttribute method [.NET Framework debugging]
- ISymUnmanagedReader::GetSymAttribute method [.NET Framework debugging]
ms.assetid: c675ce7e-76e7-45ff-8273-3b6489a2767c
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9795d5c7937f3c66c799665ba0e07e70c2be0b66
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedreadergetsymattribute-method"></a><span data-ttu-id="53228-102">ISymUnmanagedReader::GetSymAttribute (Método)</span><span class="sxs-lookup"><span data-stu-id="53228-102">ISymUnmanagedReader::GetSymAttribute Method</span></span>
<span data-ttu-id="53228-103">Obtiene un atributo personalizado basándose en su nombre.</span><span class="sxs-lookup"><span data-stu-id="53228-103">Gets a custom attribute based upon its name.</span></span> <span data-ttu-id="53228-104">A diferencia de los atributos personalizados de metadatos, estos atributos personalizados se encuentran en el almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="53228-104">Unlike metadata custom attributes, these custom attributes are held in the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53228-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="53228-105">Syntax</span></span>  
  
```  
HRESULT GetSymAttribute (  
    [in]  mdToken  parent,  
    [in]  WCHAR    *name,  
    [in]  ULONG32  cBuffer,  
    [out] ULONG32  *pcBuffer,  
    [out, size_is (cBuffer),  
        length_is (*pcBuffer)] BYTE buffer[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="53228-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="53228-106">Parameters</span></span>  
 `parent`  
 <span data-ttu-id="53228-107">[in] El token de metadatos para el objeto para el que se solicita el atributo.</span><span class="sxs-lookup"><span data-stu-id="53228-107">[in] The metadata token for the object for which the attribute is requested.</span></span>  
  
 `name`  
 <span data-ttu-id="53228-108">[in] Un puntero a la variable que indica el atributo para recuperar.</span><span class="sxs-lookup"><span data-stu-id="53228-108">[in] A pointer to the variable that indicates the attribute to retrieve.</span></span>  
  
 `cBuffer`  
 <span data-ttu-id="53228-109">[in] Tamaño de la matriz `buffer`.</span><span class="sxs-lookup"><span data-stu-id="53228-109">[in] The size of the `buffer` array.</span></span>  
  
 `pcBuffer`  
 <span data-ttu-id="53228-110">[out] Un puntero a la variable que recibe la longitud de los datos del atributo.</span><span class="sxs-lookup"><span data-stu-id="53228-110">[out] A pointer to the variable that receives the length of the attribute data.</span></span>  
  
 `buffer`  
 <span data-ttu-id="53228-111">[out] Un puntero a la variable que recibe los datos del atributo.</span><span class="sxs-lookup"><span data-stu-id="53228-111">[out] A pointer to the variable that receives the attribute data.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="53228-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="53228-112">Return Value</span></span>  
 <span data-ttu-id="53228-113">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error...</span><span class="sxs-lookup"><span data-stu-id="53228-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code..</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="53228-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="53228-114">Requirements</span></span>  
 <span data-ttu-id="53228-115">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="53228-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53228-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="53228-116">See Also</span></span>  
 [<span data-ttu-id="53228-117">ISymUnmanagedReader (interfaz)</span><span class="sxs-lookup"><span data-stu-id="53228-117">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
