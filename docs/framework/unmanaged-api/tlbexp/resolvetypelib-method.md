---
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6558d27f10e5b93dfe2c8053bb96434d49fd3c4a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54537219"
---
# <a name="resolvetypelib-method"></a><span data-ttu-id="fd0fb-102">ResolveTypeLib (Método)</span><span class="sxs-lookup"><span data-stu-id="fd0fb-102">ResolveTypeLib Method</span></span>
<span data-ttu-id="fd0fb-103">Resuelve el nombre de una biblioteca de tipos simple devolviendo su ruta de acceso completa.</span><span class="sxs-lookup"><span data-stu-id="fd0fb-103">Resolves the simple name of a type library by returning its fully qualified path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd0fb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fd0fb-104">Syntax</span></span>  
  
```  
HRESULT ResolveTypeLib(  
    [in]  BSTR      bstrSimpleName,  
    [in]  GUID      tlbid,  
    [in]  LCID      lcid,  
    [in]  USHORT    wMajorVersion,  
    [in]  USHORT    wMinorVersion,  
    [in]  SYSKIND   syskind,  
    [out] BSTR     *pbstrResolvedTlbName);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fd0fb-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fd0fb-105">Parameters</span></span>  
 `bstrSimpleName`  
 <span data-ttu-id="fd0fb-106">[in] Un [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) que contiene el nombre de la biblioteca de tipos simple.</span><span class="sxs-lookup"><span data-stu-id="fd0fb-106">[in] A [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) that contains the simple name of the type library.</span></span>  
  
 `tlbid`  
 <span data-ttu-id="fd0fb-107">[in] El GUID asignado a la biblioteca de tipos en el registro.</span><span class="sxs-lookup"><span data-stu-id="fd0fb-107">[in] The GUID assigned to the type library in the registry.</span></span>  
  
 `lcid`  
 <span data-ttu-id="fd0fb-108">[in] El identificador de localización de la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="fd0fb-108">[in] The localization ID of the type library.</span></span>  
  
 `wMajorVersion`  
 <span data-ttu-id="fd0fb-109">[in] El número de versión principal de la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="fd0fb-109">[in] The major version number of the type library.</span></span> <span data-ttu-id="fd0fb-110">Por ejemplo, para la versión *x.y*, el número de versión principal es *x*.</span><span class="sxs-lookup"><span data-stu-id="fd0fb-110">For example, for version *x.y*, the major version number is *x*.</span></span>  
  
 `wMinorVersion`  
 <span data-ttu-id="fd0fb-111">[in] El número de versión secundaria de la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="fd0fb-111">[in] The minor version number of the type library.</span></span> <span data-ttu-id="fd0fb-112">Por ejemplo, para la versión *x.y*, el número de versión secundaria es *y*.</span><span class="sxs-lookup"><span data-stu-id="fd0fb-112">For example, for version *x.y*, the minor version number is *y*.</span></span>  
  
 `syskind`  
 <span data-ttu-id="fd0fb-113">[in] Un [SYSKIND](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/ne-oaidl-tagsyskind) marca que identifica el entorno operativo.</span><span class="sxs-lookup"><span data-stu-id="fd0fb-113">[in] A [SYSKIND](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/ne-oaidl-tagsyskind) flag that identifies the operating environment.</span></span> <span data-ttu-id="fd0fb-114">Los valores habituales son SYS_WIN32 y SYS_WIN64.</span><span class="sxs-lookup"><span data-stu-id="fd0fb-114">Common values are SYS_WIN32 and SYS_WIN64.</span></span>  
  
 `pbstrResolvedTlbName`  
 <span data-ttu-id="fd0fb-115">[out] Un puntero a un [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) que contiene la ruta de acceso completa de la biblioteca de tipos con nombre en el `bstrSimpleName` parámetro.</span><span class="sxs-lookup"><span data-stu-id="fd0fb-115">[out] A pointer to a [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) that contains the full path of the type library named in the `bstrSimpleName` parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fd0fb-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fd0fb-116">Remarks</span></span>  
 <span data-ttu-id="fd0fb-117">El `ResolveTypeLib` llama al método el [LoadTypeLibWithResolver (función)](../../../../docs/framework/unmanaged-api/tlbexp/loadtypelibwithresolver-function.md) durante [Tlbexp.exe (exportador de biblioteca)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="fd0fb-117">The `ResolveTypeLib` method is called by the [LoadTypeLibWithResolver function](../../../../docs/framework/unmanaged-api/tlbexp/loadtypelibwithresolver-function.md) during [Tlbexp.exe (Type Library Exporter)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) processing.</span></span>  
  
 <span data-ttu-id="fd0fb-118">Las implementaciones personalizadas de esta interfaz deben devolver un [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) que contiene la ruta de acceso completa de la biblioteca de tipos con nombre en el `bstrSimpleName` parámetro.</span><span class="sxs-lookup"><span data-stu-id="fd0fb-118">Custom implementations of this interface must return a [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) that contains the full path of the type library named in the `bstrSimpleName` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd0fb-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fd0fb-119">Requirements</span></span>  
 <span data-ttu-id="fd0fb-120">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fd0fb-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd0fb-121">**Encabezado**: TlbRef.idl, TlbRef.h</span><span class="sxs-lookup"><span data-stu-id="fd0fb-121">**Header:** TlbRef.idl, TlbRef.h</span></span>  
  
 <span data-ttu-id="fd0fb-122">**Biblioteca:** TlbRef.lib</span><span class="sxs-lookup"><span data-stu-id="fd0fb-122">**Library:** TlbRef.lib</span></span>  
  
 <span data-ttu-id="fd0fb-123">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fd0fb-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd0fb-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="fd0fb-124">See also</span></span>
- [<span data-ttu-id="fd0fb-125">Funciones del asistente Tlbexp</span><span class="sxs-lookup"><span data-stu-id="fd0fb-125">Tlbexp Helper Functions</span></span>](../../../../docs/framework/unmanaged-api/tlbexp/index.md)
- [<span data-ttu-id="fd0fb-126">LoadTypeLibEx</span><span class="sxs-lookup"><span data-stu-id="fd0fb-126">LoadTypeLibEx</span></span>](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)
