---
title: LoadTypeLibWithResolver (Función)
ms.date: 03/30/2017
api_name:
- LoadTypeLibWithResolver
api_location:
- TlbRef.dll
api_type:
- DLLExport
f1_keywords:
- LoadTypeLibWithResolver
helpviewer_keywords:
- LoadTypeLibWithResolver function [.NET Framework]
ms.assetid: 7123a89b-eb9b-463a-a552-a081e33b0a3a
topic_type:
- apiref
ms.openlocfilehash: adbb5eca3b7ffa36d0c963d0dacc3b2afdb664d4
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2020
ms.locfileid: "75935558"
---
# <a name="loadtypelibwithresolver-function"></a><span data-ttu-id="80056-102">LoadTypeLibWithResolver (Función)</span><span class="sxs-lookup"><span data-stu-id="80056-102">LoadTypeLibWithResolver Function</span></span>
<span data-ttu-id="80056-103">Carga una biblioteca de tipos y usa la [interfaz ITypeLibResolver (](itypelibresolver-interface.md) proporcionada para resolver cualquier biblioteca de tipos a la que se hace referencia internamente.</span><span class="sxs-lookup"><span data-stu-id="80056-103">Loads a type library and uses the supplied [ITypeLibResolver interface](itypelibresolver-interface.md) to resolve any internally referenced type libraries.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80056-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="80056-104">Syntax</span></span>  
  
```cpp  
HRESULT LoadTypeLibWithResolver(  
    [in]  LPCOLESTR           szFile,  
    [in]  REGKIND             regkind,  
    [in]  ITypeLibResolver   *pTlbResolver,  
    [out] ITypeLib          **pptlib);  
```  
  
## <a name="parameters"></a><span data-ttu-id="80056-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="80056-105">Parameters</span></span>  
 `szFile`  
 <span data-ttu-id="80056-106">de Ruta de acceso del archivo de la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="80056-106">[in] The file path of the type library.</span></span>  
  
 `regkind`  
 <span data-ttu-id="80056-107">de Marca de [enumeración REGKIND](/windows/win32/api/oleauto/ne-oleauto-regkind) que controla cómo se registra la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="80056-107">[in] A [REGKIND enumeration](/windows/win32/api/oleauto/ne-oleauto-regkind) flag that controls how the type library is registered.</span></span> <span data-ttu-id="80056-108">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="80056-108">Its possible values are:</span></span>  
  
- <span data-ttu-id="80056-109">`REGKIND_DEFAULT`: usar el comportamiento de registro predeterminado.</span><span class="sxs-lookup"><span data-stu-id="80056-109">`REGKIND_DEFAULT`: Use default registration behavior.</span></span>  
  
- <span data-ttu-id="80056-110">`REGKIND_REGISTER`: Registre esta biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="80056-110">`REGKIND_REGISTER`: Register this type library.</span></span>  
  
- <span data-ttu-id="80056-111">`REGKIND_NONE`: no registrar esta biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="80056-111">`REGKIND_NONE`: Do not register this type library.</span></span>  
  
 `pTlbResolver`  
 <span data-ttu-id="80056-112">de Puntero a la implementación de la [interfaz ITypeLibResolver (](itypelibresolver-interface.md).</span><span class="sxs-lookup"><span data-stu-id="80056-112">[in] A pointer to the implementation of the [ITypeLibResolver interface](itypelibresolver-interface.md).</span></span>  
  
 `pptlib`  
 <span data-ttu-id="80056-113">enuncia Referencia a la biblioteca de tipos que se está cargando.</span><span class="sxs-lookup"><span data-stu-id="80056-113">[out] A reference to the type library that is being loaded.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="80056-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="80056-114">Return Value</span></span>  
 <span data-ttu-id="80056-115">Uno de los valores HRESULT que se muestran en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="80056-115">One of the HRESULT values listed in the following table.</span></span>  
  
|<span data-ttu-id="80056-116">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="80056-116">Return value</span></span>|<span data-ttu-id="80056-117">Significado</span><span class="sxs-lookup"><span data-stu-id="80056-117">Meaning</span></span>|  
|------------------|-------------|  
|`S_OK`|<span data-ttu-id="80056-118">Correcto.</span><span class="sxs-lookup"><span data-stu-id="80056-118">Success.</span></span>|  
|`E_OUTOFMEMORY`|<span data-ttu-id="80056-119">Memoria insuficiente</span><span class="sxs-lookup"><span data-stu-id="80056-119">Out of memory.</span></span>|  
|`E_POINTER`|<span data-ttu-id="80056-120">Uno o varios de los punteros no son válidos.</span><span class="sxs-lookup"><span data-stu-id="80056-120">One or more of the pointers are invalid.</span></span>|  
|`E_INVALIDARG`|<span data-ttu-id="80056-121">Uno o varios argumentos no son válidos.</span><span class="sxs-lookup"><span data-stu-id="80056-121">One or more of the arguments are invalid.</span></span>|  
|`TYPE_E_IOERROR`|<span data-ttu-id="80056-122">La función no pudo escribir en el archivo.</span><span class="sxs-lookup"><span data-stu-id="80056-122">The function could not write to the file.</span></span>|  
|`TYPE_E_REGISTRYACCESS`|<span data-ttu-id="80056-123">No se pudo abrir la base de datos de registro del sistema.</span><span class="sxs-lookup"><span data-stu-id="80056-123">The system registration database could not be opened.</span></span>|  
|`TYPE_E_INVALIDSTATE`|<span data-ttu-id="80056-124">No se pudo abrir la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="80056-124">The type library could not be opened.</span></span>|  
|`TYPE_E_CANTLOADLIBRARY`|<span data-ttu-id="80056-125">No se pudo cargar la biblioteca de tipos o DLL.</span><span class="sxs-lookup"><span data-stu-id="80056-125">The type library or DLL could not be loaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="80056-126">Notas</span><span class="sxs-lookup"><span data-stu-id="80056-126">Remarks</span></span>  
 <span data-ttu-id="80056-127">[Tlbexp. exe (exportador de la biblioteca de tipos)](../../tools/tlbexp-exe-type-library-exporter.md) llama a la función `LoadTypeLibWithResolver` durante el proceso de conversión de ensamblado a biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="80056-127">The [Tlbexp.exe (Type Library Exporter)](../../tools/tlbexp-exe-type-library-exporter.md) calls the `LoadTypeLibWithResolver` function during the assembly-to-type-library conversion process.</span></span>  
  
 <span data-ttu-id="80056-128">Esta función carga la biblioteca de tipos especificada con acceso mínimo al registro.</span><span class="sxs-lookup"><span data-stu-id="80056-128">This function loads the specified type library with minimal access to the registry.</span></span> <span data-ttu-id="80056-129">A continuación, la función examina la biblioteca de tipos para las bibliotecas de tipos a las que se hace referencia internamente, cada una de las cuales se debe cargar y agregar a la biblioteca de tipos primaria.</span><span class="sxs-lookup"><span data-stu-id="80056-129">The function then examines the type library for internally referenced type libraries, each of which must be loaded and added to the parent type library.</span></span>  
  
 <span data-ttu-id="80056-130">Antes de que se pueda cargar una biblioteca de tipos a la que se hace referencia, su ruta de acceso al archivo de referencia debe resolverse en una ruta de acceso completa.</span><span class="sxs-lookup"><span data-stu-id="80056-130">Before a referenced type library can be loaded, its reference file path must be resolved to a full file path.</span></span> <span data-ttu-id="80056-131">Esto se logra mediante el [método resolvetypelib (](resolvetypelib-method.md) que proporciona la [interfaz ITypeLibResolver (](itypelibresolver-interface.md), que se pasa en el parámetro `pTlbResolver`.</span><span class="sxs-lookup"><span data-stu-id="80056-131">This is accomplished through the [ResolveTypeLib method](resolvetypelib-method.md) that is provided by the [ITypeLibResolver interface](itypelibresolver-interface.md), which is passed in the `pTlbResolver` parameter.</span></span>  
  
 <span data-ttu-id="80056-132">Cuando se conoce la ruta de acceso completa del archivo de la biblioteca de tipos a la que se hace referencia, la función `LoadTypeLibWithResolver` carga y agrega la biblioteca de tipos a la biblioteca de tipos primaria, y crea una biblioteca de tipos maestra combinada.</span><span class="sxs-lookup"><span data-stu-id="80056-132">When the full file path of the referenced type library is known, the `LoadTypeLibWithResolver` function loads and adds the referenced type library to the parent type library, creating a combined master type library.</span></span>  
  
 <span data-ttu-id="80056-133">Después de que la función resuelva y cargue todas las bibliotecas de tipos a las que se hace referencia internamente, devuelve una referencia a la biblioteca de tipos principal resuelta en el parámetro `pptlib`.</span><span class="sxs-lookup"><span data-stu-id="80056-133">After the function resolves and loads all internally referenced type libraries, it returns a reference to the master resolved type library in the `pptlib` parameter.</span></span>  
  
 <span data-ttu-id="80056-134">La función `LoadTypeLibWithResolver` suele llamarse mediante [Tlbexp. exe (exportador de la biblioteca de tipos)](../../tools/tlbexp-exe-type-library-exporter.md), que proporciona su propia implementación interna de la [interfaz ITypeLibResolver (](itypelibresolver-interface.md) en el parámetro `pTlbResolver`.</span><span class="sxs-lookup"><span data-stu-id="80056-134">The `LoadTypeLibWithResolver` function is generally called by the [Tlbexp.exe (Type Library Exporter)](../../tools/tlbexp-exe-type-library-exporter.md), which supplies its own internal [ITypeLibResolver interface](itypelibresolver-interface.md) implementation in the `pTlbResolver` parameter.</span></span>  
  
 <span data-ttu-id="80056-135">Si llama a `LoadTypeLibWithResolver` directamente, debe proporcionar su propia implementación de la [interfaz ITypeLibResolver (](itypelibresolver-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="80056-135">If you call `LoadTypeLibWithResolver` directly, you must supply your own [ITypeLibResolver interface](itypelibresolver-interface.md) implementation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="80056-136">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="80056-136">Requirements</span></span>  
 <span data-ttu-id="80056-137">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="80056-137">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="80056-138">**Encabezado:** TlbRef. h</span><span class="sxs-lookup"><span data-stu-id="80056-138">**Header:** TlbRef.h</span></span>  
  
 <span data-ttu-id="80056-139">**Biblioteca:** TlbRef. lib</span><span class="sxs-lookup"><span data-stu-id="80056-139">**Library:** TlbRef.lib</span></span>  
  
 <span data-ttu-id="80056-140">**.NET Framework versión:** 3,5, 3,0, 2,0</span><span class="sxs-lookup"><span data-stu-id="80056-140">**.NET Framework Version:** 3.5, 3.0, 2.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80056-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="80056-141">See also</span></span>

- [<span data-ttu-id="80056-142">Funciones del asistente Tlbexp</span><span class="sxs-lookup"><span data-stu-id="80056-142">Tlbexp Helper Functions</span></span>](index.md)
- [<span data-ttu-id="80056-143">LoadTypeLibEx función)</span><span class="sxs-lookup"><span data-stu-id="80056-143">LoadTypeLibEx Function</span></span>](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)
