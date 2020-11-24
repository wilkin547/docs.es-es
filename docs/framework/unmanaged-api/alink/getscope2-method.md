---
title: GetScope2 (Método)
ms.date: 03/30/2017
api_name:
- IALink2.GetScope2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetScope2
helpviewer_keywords:
- GetScope2 method
ms.assetid: 49435665-6f5a-4acd-9034-8c9244a04a63
topic_type:
- apiref
ms.openlocfilehash: e8c6fd7dca13afe7504e447caca9a217c8136c27
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684530"
---
# <a name="getscope2-method"></a><span data-ttu-id="f10ab-102">GetScope2 (Método)</span><span class="sxs-lookup"><span data-stu-id="f10ab-102">GetScope2 Method</span></span>

<span data-ttu-id="f10ab-103">Obtiene un ámbito de importación.</span><span class="sxs-lookup"><span data-stu-id="f10ab-103">Gets an import scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f10ab-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f10ab-104">Syntax</span></span>  
  
```cpp  
HRESULT GetScope2(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    IMetaDataImport2** ppImportScope  
) PURE;
```  
  
## <a name="parameters"></a><span data-ttu-id="f10ab-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f10ab-105">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="f10ab-106">IDENTIFICADOR del ensamblado de destino.</span><span class="sxs-lookup"><span data-stu-id="f10ab-106">ID of target assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="f10ab-107">IDENTIFICADOR del archivo desde el que se va a importar.</span><span class="sxs-lookup"><span data-stu-id="f10ab-107">ID of file from which to import.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="f10ab-108">Ámbito de base cero que se va a importar.</span><span class="sxs-lookup"><span data-stu-id="f10ab-108">Zero-based scope to import.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="f10ab-109">Recibe un puntero a la interfaz de [interfaz IMetaDataImport2](../metadata/imetadataimport2-interface.md) para el ámbito indicado.</span><span class="sxs-lookup"><span data-stu-id="f10ab-109">Receives pointer to [IMetaDataImport2 Interface](../metadata/imetadataimport2-interface.md) interface for indicated scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f10ab-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f10ab-110">Return Value</span></span>  

 <span data-ttu-id="f10ab-111">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="f10ab-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f10ab-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f10ab-112">Requirements</span></span>  

 <span data-ttu-id="f10ab-113">Requiere ALink. h.</span><span class="sxs-lookup"><span data-stu-id="f10ab-113">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f10ab-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f10ab-114">See also</span></span>

- [<span data-ttu-id="f10ab-115">IALink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f10ab-115">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="f10ab-116">IALink (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f10ab-116">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="f10ab-117">API de ALink</span><span class="sxs-lookup"><span data-stu-id="f10ab-117">ALink API</span></span>](index.md)
