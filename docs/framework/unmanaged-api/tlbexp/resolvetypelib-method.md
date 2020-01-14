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
ms.openlocfilehash: f0f6fe321f4d38129b6d70ce94a7ea8de8fff6c8
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2020
ms.locfileid: "75935668"
---
# <a name="resolvetypelib-method"></a><span data-ttu-id="0d46b-102">ResolveTypeLib (Método)</span><span class="sxs-lookup"><span data-stu-id="0d46b-102">ResolveTypeLib Method</span></span>
<span data-ttu-id="0d46b-103">Resuelve el nombre simple de una biblioteca de tipos devolviendo su ruta de acceso completa.</span><span class="sxs-lookup"><span data-stu-id="0d46b-103">Resolves the simple name of a type library by returning its fully qualified path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d46b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0d46b-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="0d46b-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="0d46b-105">Parameters</span></span>  
 `bstrSimpleName`  
 <span data-ttu-id="0d46b-106">de [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) que contiene el nombre simple de la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="0d46b-106">[in] A [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) that contains the simple name of the type library.</span></span>  
  
 `tlbid`  
 <span data-ttu-id="0d46b-107">de GUID asignado a la biblioteca de tipos en el registro.</span><span class="sxs-lookup"><span data-stu-id="0d46b-107">[in] The GUID assigned to the type library in the registry.</span></span>  
  
 `lcid`  
 <span data-ttu-id="0d46b-108">de IDENTIFICADOR de localización de la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="0d46b-108">[in] The localization ID of the type library.</span></span>  
  
 `wMajorVersion`  
 <span data-ttu-id="0d46b-109">de Número de versión principal de la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="0d46b-109">[in] The major version number of the type library.</span></span> <span data-ttu-id="0d46b-110">Por ejemplo, para la versión *x. y*, el número de versión principal es *x*.</span><span class="sxs-lookup"><span data-stu-id="0d46b-110">For example, for version *x.y*, the major version number is *x*.</span></span>  
  
 `wMinorVersion`  
 <span data-ttu-id="0d46b-111">de Número de versión secundaria de la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="0d46b-111">[in] The minor version number of the type library.</span></span> <span data-ttu-id="0d46b-112">Por ejemplo, para la versión *x. y*, el número de versión secundaria es *y*.</span><span class="sxs-lookup"><span data-stu-id="0d46b-112">For example, for version *x.y*, the minor version number is *y*.</span></span>  
  
 `syskind`  
 <span data-ttu-id="0d46b-113">de Marca [SYSKIND](/windows/win32/api/oaidl/ne-oaidl-syskind) que identifica el entorno operativo.</span><span class="sxs-lookup"><span data-stu-id="0d46b-113">[in] A [SYSKIND](/windows/win32/api/oaidl/ne-oaidl-syskind) flag that identifies the operating environment.</span></span> <span data-ttu-id="0d46b-114">Los valores comunes son SYS_WIN32 y SYS_WIN64.</span><span class="sxs-lookup"><span data-stu-id="0d46b-114">Common values are SYS_WIN32 and SYS_WIN64.</span></span>  
  
 `pbstrResolvedTlbName`  
 <span data-ttu-id="0d46b-115">enuncia Un puntero a un [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) que contiene la ruta de acceso completa de la biblioteca de tipos denominada en el parámetro `bstrSimpleName`.</span><span class="sxs-lookup"><span data-stu-id="0d46b-115">[out] A pointer to a [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) that contains the full path of the type library named in the `bstrSimpleName` parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0d46b-116">Notas</span><span class="sxs-lookup"><span data-stu-id="0d46b-116">Remarks</span></span>  
 <span data-ttu-id="0d46b-117">La [función LoadTypeLibWithResolver (](loadtypelibwithresolver-function.md) llama al método `ResolveTypeLib` durante el procesamiento de [Tlbexp. exe (exportador de la biblioteca de tipos)](../../tools/tlbexp-exe-type-library-exporter.md) .</span><span class="sxs-lookup"><span data-stu-id="0d46b-117">The `ResolveTypeLib` method is called by the [LoadTypeLibWithResolver function](loadtypelibwithresolver-function.md) during [Tlbexp.exe (Type Library Exporter)](../../tools/tlbexp-exe-type-library-exporter.md) processing.</span></span>  
  
 <span data-ttu-id="0d46b-118">Las implementaciones personalizadas de esta interfaz deben devolver un [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) que contenga la ruta de acceso completa de la biblioteca de tipos denominada en el parámetro `bstrSimpleName`.</span><span class="sxs-lookup"><span data-stu-id="0d46b-118">Custom implementations of this interface must return a [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) that contains the full path of the type library named in the `bstrSimpleName` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d46b-119">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="0d46b-119">Requirements</span></span>  
 <span data-ttu-id="0d46b-120">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0d46b-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d46b-121">**Encabezado:** TlbRef. idl, TlbRef. h</span><span class="sxs-lookup"><span data-stu-id="0d46b-121">**Header:** TlbRef.idl, TlbRef.h</span></span>  
  
 <span data-ttu-id="0d46b-122">**Biblioteca:** TlbRef. lib</span><span class="sxs-lookup"><span data-stu-id="0d46b-122">**Library:** TlbRef.lib</span></span>  
  
 <span data-ttu-id="0d46b-123">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0d46b-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d46b-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="0d46b-124">See also</span></span>

- [<span data-ttu-id="0d46b-125">Funciones del asistente Tlbexp</span><span class="sxs-lookup"><span data-stu-id="0d46b-125">Tlbexp Helper Functions</span></span>](index.md)
- [<span data-ttu-id="0d46b-126">LoadTypeLibEx</span><span class="sxs-lookup"><span data-stu-id="0d46b-126">LoadTypeLibEx</span></span>](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)
