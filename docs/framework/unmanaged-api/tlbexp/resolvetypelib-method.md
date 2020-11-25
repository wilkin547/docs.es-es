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
ms.openlocfilehash: 84eea78b9c2e73e24238a5ecbc9442f3d63dbd4e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719793"
---
# <a name="resolvetypelib-method"></a><span data-ttu-id="45287-102">ResolveTypeLib (Método)</span><span class="sxs-lookup"><span data-stu-id="45287-102">ResolveTypeLib Method</span></span>

<span data-ttu-id="45287-103">Resuelve el nombre simple de una biblioteca de tipos devolviendo su ruta de acceso completa.</span><span class="sxs-lookup"><span data-stu-id="45287-103">Resolves the simple name of a type library by returning its fully qualified path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45287-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="45287-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="45287-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="45287-105">Parameters</span></span>  

 `bstrSimpleName`  
 <span data-ttu-id="45287-106">de [BSTR](/previous-versions/windows/desktop/automat/bstr) que contiene el nombre simple de la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="45287-106">[in] A [BSTR](/previous-versions/windows/desktop/automat/bstr) that contains the simple name of the type library.</span></span>  
  
 `tlbid`  
 <span data-ttu-id="45287-107">de GUID asignado a la biblioteca de tipos en el registro.</span><span class="sxs-lookup"><span data-stu-id="45287-107">[in] The GUID assigned to the type library in the registry.</span></span>  
  
 `lcid`  
 <span data-ttu-id="45287-108">de IDENTIFICADOR de localización de la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="45287-108">[in] The localization ID of the type library.</span></span>  
  
 `wMajorVersion`  
 <span data-ttu-id="45287-109">de Número de versión principal de la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="45287-109">[in] The major version number of the type library.</span></span> <span data-ttu-id="45287-110">Por ejemplo, para la versión *x. y*, el número de versión principal es *x*.</span><span class="sxs-lookup"><span data-stu-id="45287-110">For example, for version *x.y*, the major version number is *x*.</span></span>  
  
 `wMinorVersion`  
 <span data-ttu-id="45287-111">de Número de versión secundaria de la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="45287-111">[in] The minor version number of the type library.</span></span> <span data-ttu-id="45287-112">Por ejemplo, para la versión *x. y*, el número de versión secundaria es *y*.</span><span class="sxs-lookup"><span data-stu-id="45287-112">For example, for version *x.y*, the minor version number is *y*.</span></span>  
  
 `syskind`  
 <span data-ttu-id="45287-113">de Marca [SYSKIND](/windows/win32/api/oaidl/ne-oaidl-syskind) que identifica el entorno operativo.</span><span class="sxs-lookup"><span data-stu-id="45287-113">[in] A [SYSKIND](/windows/win32/api/oaidl/ne-oaidl-syskind) flag that identifies the operating environment.</span></span> <span data-ttu-id="45287-114">Los valores comunes son SYS_WIN32 y SYS_WIN64.</span><span class="sxs-lookup"><span data-stu-id="45287-114">Common values are SYS_WIN32 and SYS_WIN64.</span></span>  
  
 `pbstrResolvedTlbName`  
 <span data-ttu-id="45287-115">enuncia Un puntero a un [BSTR](/previous-versions/windows/desktop/automat/bstr) que contiene la ruta de acceso completa de la biblioteca de tipos con el nombre en el `bstrSimpleName` parámetro.</span><span class="sxs-lookup"><span data-stu-id="45287-115">[out] A pointer to a [BSTR](/previous-versions/windows/desktop/automat/bstr) that contains the full path of the type library named in the `bstrSimpleName` parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="45287-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="45287-116">Remarks</span></span>  

 <span data-ttu-id="45287-117">`ResolveTypeLib`La [función LoadTypeLibWithResolver (](loadtypelibwithresolver-function.md) llama al método durante el procesamiento de [Tlbexp.exe (exportador de la biblioteca de tipos)](../../tools/tlbexp-exe-type-library-exporter.md) .</span><span class="sxs-lookup"><span data-stu-id="45287-117">The `ResolveTypeLib` method is called by the [LoadTypeLibWithResolver function](loadtypelibwithresolver-function.md) during [Tlbexp.exe (Type Library Exporter)](../../tools/tlbexp-exe-type-library-exporter.md) processing.</span></span>  
  
 <span data-ttu-id="45287-118">Las implementaciones personalizadas de esta interfaz deben devolver un [BSTR](/previous-versions/windows/desktop/automat/bstr) que contenga la ruta de acceso completa de la biblioteca de tipos denominada en el `bstrSimpleName` parámetro.</span><span class="sxs-lookup"><span data-stu-id="45287-118">Custom implementations of this interface must return a [BSTR](/previous-versions/windows/desktop/automat/bstr) that contains the full path of the type library named in the `bstrSimpleName` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="45287-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="45287-119">Requirements</span></span>  

 <span data-ttu-id="45287-120">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="45287-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="45287-121">**Encabezado:** TlbRef. idl, TlbRef. h</span><span class="sxs-lookup"><span data-stu-id="45287-121">**Header:** TlbRef.idl, TlbRef.h</span></span>  
  
 <span data-ttu-id="45287-122">**Biblioteca:** TlbRef. lib</span><span class="sxs-lookup"><span data-stu-id="45287-122">**Library:** TlbRef.lib</span></span>  
  
 <span data-ttu-id="45287-123">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="45287-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45287-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="45287-124">See also</span></span>

- [<span data-ttu-id="45287-125">Funciones del asistente Tlbexp</span><span class="sxs-lookup"><span data-stu-id="45287-125">Tlbexp Helper Functions</span></span>](index.md)
- [<span data-ttu-id="45287-126">LoadTypeLibEx</span><span class="sxs-lookup"><span data-stu-id="45287-126">LoadTypeLibEx</span></span>](/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)
