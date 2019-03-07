---
title: IMetaDataEmit::DefineMethod (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineMethod
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineMethod
helpviewer_keywords:
- DefineMethod method [.NET Framework metadata]
- IMetaDataEmit::DefineMethod method [.NET Framework metadata]
ms.assetid: 3e2102c5-48b7-4c0e-b805-7e2b5e156e3d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b2372aac00473786df9b5deefb969fc02abd8daa
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57496111"
---
# <a name="imetadataemitdefinemethod-method"></a><span data-ttu-id="1979f-102">IMetaDataEmit::DefineMethod (Método)</span><span class="sxs-lookup"><span data-stu-id="1979f-102">IMetaDataEmit::DefineMethod Method</span></span>
<span data-ttu-id="1979f-103">Crea una definición para un método o una función global con la firma especificada y devuelve un token para esa definición de método.</span><span class="sxs-lookup"><span data-stu-id="1979f-103">Creates a definition for a method or global function with the specified signature, and returns a token to that method definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1979f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1979f-104">Syntax</span></span>  
  
```  
HRESULT DefineMethod (      
    [in]  mdTypeDef         td,   
    [in]  LPCWSTR           szName,   
    [in]  DWORD             dwMethodFlags,   
    [in]  PCCOR_SIGNATURE   pvSigBlob,   
    [in]  ULONG             cbSigBlob,   
    [in]  ULONG             ulCodeRVA,   
    [in]  DWORD             dwImplFlags,   
    [out] mdMethodDef      *pmd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1979f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1979f-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="1979f-106">[in] El `mdTypedef` símbolo (token) de la interfaz primaria del método o clase primaria.</span><span class="sxs-lookup"><span data-stu-id="1979f-106">[in] The `mdTypedef` token of the parent class or parent interface of the method.</span></span> <span data-ttu-id="1979f-107">Establecer `td` a `mdTokenNil`, si está definiendo una función global.</span><span class="sxs-lookup"><span data-stu-id="1979f-107">Set `td` to `mdTokenNil`, if you are defining a global function.</span></span>  
  
 `szName`  
 <span data-ttu-id="1979f-108">[in] El nombre del miembro en Unicode.</span><span class="sxs-lookup"><span data-stu-id="1979f-108">[in] The member name in Unicode.</span></span>  
  
 `dwMethodFlags`  
 <span data-ttu-id="1979f-109">[in] Un valor de la [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) enumeración que especifica los atributos del método o función global.</span><span class="sxs-lookup"><span data-stu-id="1979f-109">[in] A value of the [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) enumeration that specifies the attributes of the method or global function.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="1979f-110">[in] La firma del método.</span><span class="sxs-lookup"><span data-stu-id="1979f-110">[in] The method signature.</span></span> <span data-ttu-id="1979f-111">La firma se conserva tal como lo suministró.</span><span class="sxs-lookup"><span data-stu-id="1979f-111">The signature is persisted as supplied.</span></span> <span data-ttu-id="1979f-112">Si tiene que especificar información adicional para los parámetros, use la [SetParamProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setparamprops-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="1979f-112">If you need to specify additional information for any parameters, use the [IMetaDataEmit::SetParamProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setparamprops-method.md) method.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="1979f-113">[in] El recuento de bytes en `pvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="1979f-113">[in] The count of bytes in `pvSigBlob`.</span></span>  
  
 `ulCodeRVA`  
 <span data-ttu-id="1979f-114">[in] La dirección del código.</span><span class="sxs-lookup"><span data-stu-id="1979f-114">[in] The address of the code.</span></span>  
  
 `dwImplFlags`  
 <span data-ttu-id="1979f-115">[in] Un valor de la [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) enumeración que especifica las características de implementación del método.</span><span class="sxs-lookup"><span data-stu-id="1979f-115">[in] A value of the [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) enumeration that specifies the implementation features of the method.</span></span>  
  
 `pmd`  
 <span data-ttu-id="1979f-116">[out] El token de miembro.</span><span class="sxs-lookup"><span data-stu-id="1979f-116">[out] The member token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1979f-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1979f-117">Remarks</span></span>  
 <span data-ttu-id="1979f-118">La API de metadatos garantiza que se conserven los métodos en el mismo orden que los emite el llamador para una determinada clase o interfaz envolvente, que se especifica en el `td` parámetro.</span><span class="sxs-lookup"><span data-stu-id="1979f-118">The metadata API guarantees to persist methods in the same order as the caller emits them for a given enclosing class or interface, which is specified in the `td` parameter.</span></span>  
  
 <span data-ttu-id="1979f-119">Información adicional sobre el uso de `DefineMethod` y configuración de los parámetros se indican a continuación.</span><span class="sxs-lookup"><span data-stu-id="1979f-119">Additional information regarding the use of `DefineMethod` and particular parameter settings is given below.</span></span>  
  
## <a name="slots-in-the-v-table"></a><span data-ttu-id="1979f-120">Ranuras de la tabla v.</span><span class="sxs-lookup"><span data-stu-id="1979f-120">Slots in the V-table</span></span>  
 <span data-ttu-id="1979f-121">El tiempo de ejecución usa las definiciones de método para configurar ranuras de v-table.</span><span class="sxs-lookup"><span data-stu-id="1979f-121">The runtime uses method definitions to set up v-table slots.</span></span> <span data-ttu-id="1979f-122">En el caso donde uno o más espacios deben omitirse, tales como para conservar la paridad con un diseño de interfaz COM, se define un método ficticio para ocupar la ranura o ranuras en la tabla v; establecer el `dwMethodFlags` a la `mdRTSpecialName` valor de la [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) enumeración y especifique el nombre como:</span><span class="sxs-lookup"><span data-stu-id="1979f-122">In the case where one or more slots need to be skipped, such as to preserve parity with a COM interface layout, a dummy method is defined to take up the slot or slots in the v-table; set the `dwMethodFlags` to the `mdRTSpecialName` value of the [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) enumeration and specify the name as:</span></span>  
  
 <span data-ttu-id="1979f-123">_VtblGap\<*SequenceNumber*>\<\_*CountOfSlots*></span><span class="sxs-lookup"><span data-stu-id="1979f-123">_VtblGap\<*SequenceNumber*>\<\_*CountOfSlots*></span></span>
  
 <span data-ttu-id="1979f-124">donde *SequenceNumber* es el número de secuencia del método y *recuentoDeRanuras* es el número de ranuras que se omiten en la tabla v.</span><span class="sxs-lookup"><span data-stu-id="1979f-124">where *SequenceNumber* is the sequence number of the method and *CountOfSlots* is the number of slots to skip in the v-table.</span></span> <span data-ttu-id="1979f-125">Si *recuentoDeRanuras* es se omite, se asume 1.</span><span class="sxs-lookup"><span data-stu-id="1979f-125">If *CountOfSlots* is omitted, 1 is assumed.</span></span> <span data-ttu-id="1979f-126">Estos métodos ficticios no son invocables desde código administrado o no administrado y cualquier intento de llamarlas desde código administrado o no administrado, genera una excepción.</span><span class="sxs-lookup"><span data-stu-id="1979f-126">These dummy methods are not callable from either managed or unmanaged code and any attempt to call them, from either managed or unmanaged code, generates an exception.</span></span> <span data-ttu-id="1979f-127">Su único objetivo es ocupan espacio en la tabla v que genera el tiempo de ejecución para la integración de COM.</span><span class="sxs-lookup"><span data-stu-id="1979f-127">Their only purpose is to take up space in the v-table that the runtime generates for COM integration.</span></span>  
  
## <a name="duplicate-methods"></a><span data-ttu-id="1979f-128">Métodos duplicados</span><span class="sxs-lookup"><span data-stu-id="1979f-128">Duplicate Methods</span></span>  
 <span data-ttu-id="1979f-129">No debería definir métodos duplicados.</span><span class="sxs-lookup"><span data-stu-id="1979f-129">You should not define duplicate methods.</span></span> <span data-ttu-id="1979f-130">Es decir, no debería llamar `DefineMethod` con un conjunto duplicado de valores en el `td`, `wzName`, y `pvSig` parámetros.</span><span class="sxs-lookup"><span data-stu-id="1979f-130">That is, you should not call `DefineMethod` with a duplicate set of values in the `td`, `wzName`, and `pvSig` parameters.</span></span> <span data-ttu-id="1979f-131">(Estos tres parámetros juntos definen el método de forma unívoca.).</span><span class="sxs-lookup"><span data-stu-id="1979f-131">(These three parameters together uniquely define the method.).</span></span> <span data-ttu-id="1979f-132">Sin embargo, puede utilizar un triple duplicado siempre que uno de las definiciones de método, Establece el `mdPrivateScope` bit en el `dwMethodFlags` parámetro.</span><span class="sxs-lookup"><span data-stu-id="1979f-132">However, you can use a duplicate triple provided that, for one of the method definitions, you set the `mdPrivateScope` bit in the `dwMethodFlags` parameter.</span></span> <span data-ttu-id="1979f-133">(El `mdPrivateScope` bit significa que el compilador no emitirá una referencia a esta definición de método.)</span><span class="sxs-lookup"><span data-stu-id="1979f-133">(The `mdPrivateScope` bit means that the compiler will not emit a reference to this method definition.)</span></span>  
  
## <a name="method-implementation-information"></a><span data-ttu-id="1979f-134">Información de método de implementación</span><span class="sxs-lookup"><span data-stu-id="1979f-134">Method Implementation Information</span></span>  
 <span data-ttu-id="1979f-135">A menudo no se conoce la información sobre la implementación del método en el momento en que se declara el método.</span><span class="sxs-lookup"><span data-stu-id="1979f-135">Information about the method implementation is often not known at the time the method is declared.</span></span> <span data-ttu-id="1979f-136">Por lo tanto, no es necesario pasar valores en el `ulCodeRVA` y `dwImplFlags` parámetros cuando se llama a `DefineMethod`.</span><span class="sxs-lookup"><span data-stu-id="1979f-136">Therefore, you do not need to pass values in the `ulCodeRVA` and `dwImplFlags` parameters when calling `DefineMethod`.</span></span> <span data-ttu-id="1979f-137">Se pueden proporcionar los valores más adelante a través [SetMethodImplFlags](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmethodimplflags-method.md) o [SetRVA](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setrva-method.md), según corresponda.</span><span class="sxs-lookup"><span data-stu-id="1979f-137">The values can be supplied later through [IMetaDataEmit::SetMethodImplFlags](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmethodimplflags-method.md) or [IMetaDataEmit::SetRVA](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setrva-method.md), as appropriate.</span></span>  
  
 <span data-ttu-id="1979f-138">En algunas situaciones, como la invocación de plataforma (PInvoke) o escenarios de interoperabilidad COM, no se proporcionarán el cuerpo del método, y `ulCodeRVA` debe establecerse en cero.</span><span class="sxs-lookup"><span data-stu-id="1979f-138">In some situations, such as platform invocation (PInvoke) or COM interop scenarios, the method body will not be supplied, and `ulCodeRVA` should be set to zero.</span></span> <span data-ttu-id="1979f-139">En estas situaciones, el método no debe etiquetar como abstracto, porque el tiempo de ejecución buscará la implementación.</span><span class="sxs-lookup"><span data-stu-id="1979f-139">In these situations, the method should not be tagged as abstract, because the runtime will locate the implementation.</span></span>  
  
## <a name="defining-a-method-for-pinvoke"></a><span data-ttu-id="1979f-140">Definir un método para PInvoke</span><span class="sxs-lookup"><span data-stu-id="1979f-140">Defining a Method for PInvoke</span></span>  
 <span data-ttu-id="1979f-141">Para que cada función no administrada que se llame a través de PInvoke, debe definir un método administrado que representa la función no administrada de destino.</span><span class="sxs-lookup"><span data-stu-id="1979f-141">For each unmanaged function to be called through PInvoke, you must define a managed method that represents the target unmanaged function.</span></span> <span data-ttu-id="1979f-142">Para definir el método administrado, utilice `DefineMethod` con algunos de los parámetros establecidos a ciertos valores, dependiendo de la forma en que se utiliza PInvoke:</span><span class="sxs-lookup"><span data-stu-id="1979f-142">To define the managed method, use `DefineMethod` with some of the parameters set to certain values, depending on the way in which PInvoke is used:</span></span>  
  
-   <span data-ttu-id="1979f-143">PInvoke verdadero - implica la invocación de un método no administrado externo que reside en una DLL no administrada.</span><span class="sxs-lookup"><span data-stu-id="1979f-143">True PInvoke - involves invocation of an external unmanaged method that resides in an unmanaged DLL.</span></span>  
  
-   <span data-ttu-id="1979f-144">PInvoke local: implica la invocación de un método nativo no administrado que está incrustado en el módulo administrado actual.</span><span class="sxs-lookup"><span data-stu-id="1979f-144">Local PInvoke - involves invocation of a native unmanaged method that is embedded in the current managed module.</span></span>  
  
 <span data-ttu-id="1979f-145">La configuración de parámetros se proporciona en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="1979f-145">The parameter settings are given in the following table.</span></span>  
  
|<span data-ttu-id="1979f-146">Parámetro</span><span class="sxs-lookup"><span data-stu-id="1979f-146">Parameter</span></span>|<span data-ttu-id="1979f-147">Valores de PInvoke verdadero</span><span class="sxs-lookup"><span data-stu-id="1979f-147">Values for true PInvoke</span></span>|<span data-ttu-id="1979f-148">Valores de PInvoke local</span><span class="sxs-lookup"><span data-stu-id="1979f-148">Values for local PInvoke</span></span>|  
|---------------|-----------------------------|------------------------------|  
|`dwMethodFlags`||<span data-ttu-id="1979f-149">Establecer `mdStatic`; desactive `mdSynchronized` y `mdAbstract`.</span><span class="sxs-lookup"><span data-stu-id="1979f-149">Set `mdStatic`; clear `mdSynchronized` and `mdAbstract`.</span></span>|  
|`pvSigBlob`|<span data-ttu-id="1979f-150">Tipos administrados de una common language runtime (CLR) firma de método válida con parámetros que son válidos.</span><span class="sxs-lookup"><span data-stu-id="1979f-150">A valid common language runtime (CLR) method signature with parameters that are valid managed types.</span></span>|<span data-ttu-id="1979f-151">Una firma de método CLR válida con parámetros que son válidos los tipos administrados.</span><span class="sxs-lookup"><span data-stu-id="1979f-151">A valid CLR method signature with parameters that are valid managed types.</span></span>|  
|`ulCodeRVA`||<span data-ttu-id="1979f-152">0</span><span class="sxs-lookup"><span data-stu-id="1979f-152">0</span></span>|  
|`dwImplFlags`|<span data-ttu-id="1979f-153">Establecer `miCil` y `miManaged`.</span><span class="sxs-lookup"><span data-stu-id="1979f-153">Set `miCil` and `miManaged`.</span></span>|<span data-ttu-id="1979f-154">Establecer `miNative` y `miUnmanaged`.</span><span class="sxs-lookup"><span data-stu-id="1979f-154">Set `miNative` and `miUnmanaged`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1979f-155">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1979f-155">Requirements</span></span>  
 <span data-ttu-id="1979f-156">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1979f-156">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1979f-157">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="1979f-157">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1979f-158">**Biblioteca:** Usar como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1979f-158">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1979f-159">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1979f-159">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1979f-160">Vea también</span><span class="sxs-lookup"><span data-stu-id="1979f-160">See also</span></span>
- [<span data-ttu-id="1979f-161">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1979f-161">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="1979f-162">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1979f-162">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
