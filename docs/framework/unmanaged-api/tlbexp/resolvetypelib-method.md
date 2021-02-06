---
description: 'Más información sobre: método Resolvetypelib ('
title: ResolveTypeLib (Método)
ms.date: 03/30/2017
api_name:
- ResolveTypeLib
api_location:
- tlbref.dll
f1_keywords:
- ResolveTypeLib
helpviewer_keywords:
- ITypeLibResolver::ResolveTypeLib method [.NET Framework]
- ResolveTypeLib method [.NET Framework]
ms.assetid: 95d2aa0d-8eeb-4a9f-a216-5249f7e2c167
topic_type:
- apiref
ms.openlocfilehash: ca7f94f630479d30bb9129497b38bcf04e759e5d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99646288"
---
# <a name="resolvetypelib-method"></a><span data-ttu-id="a7b72-103">ResolveTypeLib (Método)</span><span class="sxs-lookup"><span data-stu-id="a7b72-103">ResolveTypeLib Method</span></span>

<span data-ttu-id="a7b72-104">Resuelve el nombre simple de una biblioteca de tipos devolviendo su ruta de acceso completa.</span><span class="sxs-lookup"><span data-stu-id="a7b72-104">Resolves the simple name of a type library by returning its fully qualified path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7b72-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a7b72-105">Syntax</span></span>  
  
```cpp  
HRESULT ResolveTypeLib(  
    [in]  BSTR      bstrSimpleName,  
    [in]  GUID      tlbid,  
    [in]  LCID      lcid,  
    [in]  USHORT    wMajorVersion,  
    [in]  USHORT    wMinorVersion,  
    [in]  SYSKIND   syskind,  
    [out] BSTR     *pbstrResolvedTlbName);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a7b72-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a7b72-106">Parameters</span></span>  

 `bstrSimpleName`  
 <span data-ttu-id="a7b72-107">de [BSTR](/previous-versions/windows/desktop/automat/bstr) que contiene el nombre simple de la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="a7b72-107">[in] A [BSTR](/previous-versions/windows/desktop/automat/bstr) that contains the simple name of the type library.</span></span>  
  
 `tlbid`  
 <span data-ttu-id="a7b72-108">de GUID asignado a la biblioteca de tipos en el registro.</span><span class="sxs-lookup"><span data-stu-id="a7b72-108">[in] The GUID assigned to the type library in the registry.</span></span>  
  
 `lcid`  
 <span data-ttu-id="a7b72-109">de IDENTIFICADOR de localización de la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="a7b72-109">[in] The localization ID of the type library.</span></span>  
  
 `wMajorVersion`  
 <span data-ttu-id="a7b72-110">de Número de versión principal de la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="a7b72-110">[in] The major version number of the type library.</span></span> <span data-ttu-id="a7b72-111">Por ejemplo, para la versión *x. y*, el número de versión principal es *x*.</span><span class="sxs-lookup"><span data-stu-id="a7b72-111">For example, for version *x.y*, the major version number is *x*.</span></span>  
  
 `wMinorVersion`  
 <span data-ttu-id="a7b72-112">de Número de versión secundaria de la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="a7b72-112">[in] The minor version number of the type library.</span></span> <span data-ttu-id="a7b72-113">Por ejemplo, para la versión *x. y*, el número de versión secundaria es *y*.</span><span class="sxs-lookup"><span data-stu-id="a7b72-113">For example, for version *x.y*, the minor version number is *y*.</span></span>  
  
 `syskind`  
 <span data-ttu-id="a7b72-114">de Marca [SYSKIND](/windows/win32/api/oaidl/ne-oaidl-syskind) que identifica el entorno operativo.</span><span class="sxs-lookup"><span data-stu-id="a7b72-114">[in] A [SYSKIND](/windows/win32/api/oaidl/ne-oaidl-syskind) flag that identifies the operating environment.</span></span> <span data-ttu-id="a7b72-115">Los valores comunes son SYS_WIN32 y SYS_WIN64.</span><span class="sxs-lookup"><span data-stu-id="a7b72-115">Common values are SYS_WIN32 and SYS_WIN64.</span></span>  
  
 `pbstrResolvedTlbName`  
 <span data-ttu-id="a7b72-116">enuncia Un puntero a un [BSTR](/previous-versions/windows/desktop/automat/bstr) que contiene la ruta de acceso completa de la biblioteca de tipos con el nombre en el `bstrSimpleName` parámetro.</span><span class="sxs-lookup"><span data-stu-id="a7b72-116">[out] A pointer to a [BSTR](/previous-versions/windows/desktop/automat/bstr) that contains the full path of the type library named in the `bstrSimpleName` parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a7b72-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a7b72-117">Remarks</span></span>  

 <span data-ttu-id="a7b72-118">`ResolveTypeLib`La [función LoadTypeLibWithResolver (](loadtypelibwithresolver-function.md) llama al método durante el procesamiento de [Tlbexp.exe (exportador de la biblioteca de tipos)](../../tools/tlbexp-exe-type-library-exporter.md) .</span><span class="sxs-lookup"><span data-stu-id="a7b72-118">The `ResolveTypeLib` method is called by the [LoadTypeLibWithResolver function](loadtypelibwithresolver-function.md) during [Tlbexp.exe (Type Library Exporter)](../../tools/tlbexp-exe-type-library-exporter.md) processing.</span></span>  
  
 <span data-ttu-id="a7b72-119">Las implementaciones personalizadas de esta interfaz deben devolver un [BSTR](/previous-versions/windows/desktop/automat/bstr) que contenga la ruta de acceso completa de la biblioteca de tipos denominada en el `bstrSimpleName` parámetro.</span><span class="sxs-lookup"><span data-stu-id="a7b72-119">Custom implementations of this interface must return a [BSTR](/previous-versions/windows/desktop/automat/bstr) that contains the full path of the type library named in the `bstrSimpleName` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7b72-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a7b72-120">Requirements</span></span>  

 <span data-ttu-id="a7b72-121">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a7b72-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7b72-122">**Encabezado:** TlbRef. idl, TlbRef. h</span><span class="sxs-lookup"><span data-stu-id="a7b72-122">**Header:** TlbRef.idl, TlbRef.h</span></span>  
  
 <span data-ttu-id="a7b72-123">**Biblioteca:** TlbRef. lib</span><span class="sxs-lookup"><span data-stu-id="a7b72-123">**Library:** TlbRef.lib</span></span>  
  
 <span data-ttu-id="a7b72-124">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7b72-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7b72-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="a7b72-125">See also</span></span>

- [<span data-ttu-id="a7b72-126">Funciones del asistente Tlbexp</span><span class="sxs-lookup"><span data-stu-id="a7b72-126">Tlbexp Helper Functions</span></span>](index.md)
- [<span data-ttu-id="a7b72-127">LoadTypeLibEx</span><span class="sxs-lookup"><span data-stu-id="a7b72-127">LoadTypeLibEx</span></span>](/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)
