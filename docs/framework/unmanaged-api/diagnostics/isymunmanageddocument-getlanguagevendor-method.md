---
title: ISymUnmanagedDocument::GetLanguageVendor (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetLanguageVendor
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetLanguageVendor
helpviewer_keywords:
- GetLanguageVendor method [.NET Framework debugging]
- ISymUnmanagedDocument::GetLanguageVendor method [.NET Framework debugging]
ms.assetid: 1d4b702e-4922-441d-8b44-03804284f70b
topic_type:
- apiref
ms.openlocfilehash: e0a4c190f0f8e91886563477500c0e57e3516dfa
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614570"
---
# <a name="isymunmanageddocumentgetlanguagevendor-method"></a><span data-ttu-id="79fbb-102">ISymUnmanagedDocument::GetLanguageVendor (Método)</span><span class="sxs-lookup"><span data-stu-id="79fbb-102">ISymUnmanagedDocument::GetLanguageVendor Method</span></span>
<span data-ttu-id="79fbb-103">Obtiene el proveedor de lenguaje de este documento.</span><span class="sxs-lookup"><span data-stu-id="79fbb-103">Gets the language vendor of this document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79fbb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="79fbb-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLanguageVendor(  
    [out, retval]  GUID*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="79fbb-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="79fbb-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="79fbb-106">enuncia Puntero a una variable que recibe el proveedor de idioma.</span><span class="sxs-lookup"><span data-stu-id="79fbb-106">[out] A pointer to a variable that receives the language vendor.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="79fbb-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="79fbb-107">Return Value</span></span>  
 <span data-ttu-id="79fbb-108">S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="79fbb-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79fbb-109">Consulta también</span><span class="sxs-lookup"><span data-stu-id="79fbb-109">See also</span></span>

- [<span data-ttu-id="79fbb-110">ISymUnmanagedDocument (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="79fbb-110">ISymUnmanagedDocument Interface</span></span>](isymunmanageddocument-interface.md)
