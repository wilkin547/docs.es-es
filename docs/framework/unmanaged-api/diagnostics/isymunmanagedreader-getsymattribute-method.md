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
ms.openlocfilehash: b7e2814e56765037b69c6ef7ca0ba610dd7d3c95
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614934"
---
# <a name="isymunmanagedreadergetsymattribute-method"></a><span data-ttu-id="a7b28-102">ISymUnmanagedReader::GetSymAttribute (Método)</span><span class="sxs-lookup"><span data-stu-id="a7b28-102">ISymUnmanagedReader::GetSymAttribute Method</span></span>
<span data-ttu-id="a7b28-103">Obtiene un atributo personalizado basado en su nombre.</span><span class="sxs-lookup"><span data-stu-id="a7b28-103">Gets a custom attribute based upon its name.</span></span> <span data-ttu-id="a7b28-104">A diferencia de los atributos personalizados de metadatos, estos atributos personalizados se mantienen en el almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="a7b28-104">Unlike metadata custom attributes, these custom attributes are held in the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7b28-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a7b28-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSymAttribute (  
    [in]  mdToken  parent,  
    [in]  WCHAR    *name,  
    [in]  ULONG32  cBuffer,  
    [out] ULONG32  *pcBuffer,  
    [out, size_is (cBuffer),  
        length_is (*pcBuffer)] BYTE buffer[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a7b28-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a7b28-106">Parameters</span></span>  
 `parent`  
 <span data-ttu-id="a7b28-107">de Símbolo (token) de metadatos del objeto para el que se solicita el atributo.</span><span class="sxs-lookup"><span data-stu-id="a7b28-107">[in] The metadata token for the object for which the attribute is requested.</span></span>  
  
 `name`  
 <span data-ttu-id="a7b28-108">de Puntero a la variable que indica el atributo que se va a recuperar.</span><span class="sxs-lookup"><span data-stu-id="a7b28-108">[in] A pointer to the variable that indicates the attribute to retrieve.</span></span>  
  
 `cBuffer`  
 <span data-ttu-id="a7b28-109">[in] Tamaño de la matriz `buffer`.</span><span class="sxs-lookup"><span data-stu-id="a7b28-109">[in] The size of the `buffer` array.</span></span>  
  
 `pcBuffer`  
 <span data-ttu-id="a7b28-110">enuncia Puntero a la variable que recibe la longitud de los datos del atributo.</span><span class="sxs-lookup"><span data-stu-id="a7b28-110">[out] A pointer to the variable that receives the length of the attribute data.</span></span>  
  
 `buffer`  
 <span data-ttu-id="a7b28-111">enuncia Puntero a la variable que recibe los datos del atributo.</span><span class="sxs-lookup"><span data-stu-id="a7b28-111">[out] A pointer to the variable that receives the attribute data.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a7b28-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a7b28-112">Return Value</span></span>  
 <span data-ttu-id="a7b28-113">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="a7b28-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7b28-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a7b28-114">Requirements</span></span>  
 <span data-ttu-id="a7b28-115">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="a7b28-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7b28-116">Consulta también</span><span class="sxs-lookup"><span data-stu-id="a7b28-116">See also</span></span>

- [<span data-ttu-id="a7b28-117">ISymUnmanagedReader (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a7b28-117">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
