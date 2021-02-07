---
description: 'Más información acerca de: ISymUnmanagedReader:: GetSymAttribute ((método)'
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
ms.openlocfilehash: cd1c453e9f2ef68799fc5eccf1288a7665c5cfdf
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99763974"
---
# <a name="isymunmanagedreadergetsymattribute-method"></a><span data-ttu-id="be2f0-103">ISymUnmanagedReader::GetSymAttribute (Método)</span><span class="sxs-lookup"><span data-stu-id="be2f0-103">ISymUnmanagedReader::GetSymAttribute Method</span></span>

<span data-ttu-id="be2f0-104">Obtiene un atributo personalizado basado en su nombre.</span><span class="sxs-lookup"><span data-stu-id="be2f0-104">Gets a custom attribute based upon its name.</span></span> <span data-ttu-id="be2f0-105">A diferencia de los atributos personalizados de metadatos, estos atributos personalizados se mantienen en el almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="be2f0-105">Unlike metadata custom attributes, these custom attributes are held in the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be2f0-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="be2f0-106">Syntax</span></span>  
  
```cpp  
HRESULT GetSymAttribute (  
    [in]  mdToken  parent,  
    [in]  WCHAR    *name,  
    [in]  ULONG32  cBuffer,  
    [out] ULONG32  *pcBuffer,  
    [out, size_is (cBuffer),  
        length_is (*pcBuffer)] BYTE buffer[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="be2f0-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="be2f0-107">Parameters</span></span>  

 `parent`  
 <span data-ttu-id="be2f0-108">de Símbolo (token) de metadatos del objeto para el que se solicita el atributo.</span><span class="sxs-lookup"><span data-stu-id="be2f0-108">[in] The metadata token for the object for which the attribute is requested.</span></span>  
  
 `name`  
 <span data-ttu-id="be2f0-109">de Puntero a la variable que indica el atributo que se va a recuperar.</span><span class="sxs-lookup"><span data-stu-id="be2f0-109">[in] A pointer to the variable that indicates the attribute to retrieve.</span></span>  
  
 `cBuffer`  
 <span data-ttu-id="be2f0-110">[in] Tamaño de la matriz `buffer`.</span><span class="sxs-lookup"><span data-stu-id="be2f0-110">[in] The size of the `buffer` array.</span></span>  
  
 `pcBuffer`  
 <span data-ttu-id="be2f0-111">enuncia Puntero a la variable que recibe la longitud de los datos del atributo.</span><span class="sxs-lookup"><span data-stu-id="be2f0-111">[out] A pointer to the variable that receives the length of the attribute data.</span></span>  
  
 `buffer`  
 <span data-ttu-id="be2f0-112">enuncia Puntero a la variable que recibe los datos del atributo.</span><span class="sxs-lookup"><span data-stu-id="be2f0-112">[out] A pointer to the variable that receives the attribute data.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="be2f0-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="be2f0-113">Return Value</span></span>  

 <span data-ttu-id="be2f0-114">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="be2f0-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="be2f0-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="be2f0-115">Requirements</span></span>  

 <span data-ttu-id="be2f0-116">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="be2f0-116">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be2f0-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="be2f0-117">See also</span></span>

- [<span data-ttu-id="be2f0-118">ISymUnmanagedReader (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="be2f0-118">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
