---
title: IMetaDataImport2::GetVersionString (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.GetVersionString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::GetVersionString
helpviewer_keywords:
- GetVersionString method, IMetaDataImport2 interface [.NET Framework metadata]
- IMetaDataImport2::GetVersionString method [.NET Framework metadata]
ms.assetid: 308183ee-fd44-4432-9d86-ef00d181b49b
topic_type:
- apiref
ms.openlocfilehash: 84cf5ac9eab5749d3bdc63670fe5c31bfb62abcd
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84490412"
---
# <a name="imetadataimport2getversionstring-method"></a><span data-ttu-id="7d35b-102">IMetaDataImport2::GetVersionString (Método)</span><span class="sxs-lookup"><span data-stu-id="7d35b-102">IMetaDataImport2::GetVersionString Method</span></span>
<span data-ttu-id="7d35b-103">Obtiene el número de versión del motor en tiempo de ejecución que se usó para compilar el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="7d35b-103">Gets the version number of the runtime that was used to build the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d35b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7d35b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetVersionString (  
   [out] LPWSTR      pwzBuf,  
   [in]  DWORD       ccBufSize,  
   [out] DWORD       *pccBufSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7d35b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7d35b-105">Parameters</span></span>  
 `pwzBuf`  
 <span data-ttu-id="7d35b-106">enuncia Matriz para almacenar la cadena que especifica la versión.</span><span class="sxs-lookup"><span data-stu-id="7d35b-106">[out] An array to store the string that specifies the version.</span></span>  
  
 `ccBufSize`  
 <span data-ttu-id="7d35b-107">de Tamaño, en caracteres anchos, de la `pwzBuf` matriz.</span><span class="sxs-lookup"><span data-stu-id="7d35b-107">[in] The size, in wide characters, of the `pwzBuf` array.</span></span>  
  
 `pccBufSize`  
 <span data-ttu-id="7d35b-108">enuncia El número de caracteres anchos, incluido un terminador nulo, devuelto en la `pwzBuf` matriz.</span><span class="sxs-lookup"><span data-stu-id="7d35b-108">[out] The number of wide characters, including a null terminator, returned in the `pwzBuf` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7d35b-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7d35b-109">Remarks</span></span>  
 <span data-ttu-id="7d35b-110">El `GetVersionString` método obtiene la versión integrada del ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="7d35b-110">The `GetVersionString` method gets the built-for version of the current metadata scope.</span></span> <span data-ttu-id="7d35b-111">Si el ámbito no se ha guardado nunca, no tendrá una versión integrada y se devolverá una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="7d35b-111">If the scope has never been saved, it will not have a built-for version, and an empty string will be returned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d35b-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7d35b-112">Requirements</span></span>  
 <span data-ttu-id="7d35b-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7d35b-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d35b-114">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="7d35b-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7d35b-115">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="7d35b-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7d35b-116">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d35b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d35b-117">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="7d35b-117">See also</span></span>

- [<span data-ttu-id="7d35b-118">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7d35b-118">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
- [<span data-ttu-id="7d35b-119">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7d35b-119">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
