---
title: ImportTypes2 (Método)
ms.date: 03/30/2017
api_name:
- IALink2.ImportTypes2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportTypes2
helpviewer_keywords:
- ImportTypes2 method
ms.assetid: 32f3ba58-9695-41e9-ba58-fd19e45ed396
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f14822a58f3982d6f9fee1328c10b960657c056f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59098473"
---
# <a name="importtypes2-method"></a><span data-ttu-id="0ac46-102">ImportTypes2 (Método)</span><span class="sxs-lookup"><span data-stu-id="0ac46-102">ImportTypes2 Method</span></span>
<span data-ttu-id="0ac46-103">Inicia la importación de tipos.</span><span class="sxs-lookup"><span data-stu-id="0ac46-103">Initiates the import of types.</span></span> <span data-ttu-id="0ac46-104">Llame a este método para comenzar a importar los tipos de cada ámbito importado a través de [ImportFile (método)](../../../../docs/framework/unmanaged-api/alink/importfile-method.md).</span><span class="sxs-lookup"><span data-stu-id="0ac46-104">Call this method to begin importing types from each scope imported via [ImportFile Method](../../../../docs/framework/unmanaged-api/alink/importfile-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ac46-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0ac46-105">Syntax</span></span>  
  
```  
HRESULT ImportTypes2(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    HALINKENUM* phEnum,  
    IMetaDataImport2** ppImportScope,  
    DWORD* pdwCountOfTypes  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="0ac46-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0ac46-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="0ac46-107">Identificador del ensamblado al que desea importar.</span><span class="sxs-lookup"><span data-stu-id="0ac46-107">ID of assembly into which to import.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="0ac46-108">Id. del archivo desde el que se va a importar.</span><span class="sxs-lookup"><span data-stu-id="0ac46-108">ID of file to from which to import.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="0ac46-109">Ámbito de base cero de la que se va a importar.</span><span class="sxs-lookup"><span data-stu-id="0ac46-109">Zero-based scope from which to import.</span></span>  
  
 `phEnum`  
 <span data-ttu-id="0ac46-110">Recibe el identificador de enumerador para los tipos en el ámbito especificado.</span><span class="sxs-lookup"><span data-stu-id="0ac46-110">Receives enumerator handle for the types in the given scope.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="0ac46-111">Si lo desea recibe [IMetaDataImport2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md) interfaz.</span><span class="sxs-lookup"><span data-stu-id="0ac46-111">Optionally receives [IMetaDataImport2 Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md) interface.</span></span>  
  
 `pdwCountOfTypes`  
 <span data-ttu-id="0ac46-112">Opcionalmente, recibe el recuento de tipos en el ámbito especificado.</span><span class="sxs-lookup"><span data-stu-id="0ac46-112">Optionally receives count of types in the specified scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0ac46-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="0ac46-113">Return Value</span></span>  
 <span data-ttu-id="0ac46-114">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="0ac46-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ac46-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0ac46-115">Requirements</span></span>  
 <span data-ttu-id="0ac46-116">Requiere alink.h</span><span class="sxs-lookup"><span data-stu-id="0ac46-116">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ac46-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="0ac46-117">See also</span></span>

- [<span data-ttu-id="0ac46-118">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0ac46-118">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="0ac46-119">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0ac46-119">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="0ac46-120">API de ALink</span><span class="sxs-lookup"><span data-stu-id="0ac46-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
