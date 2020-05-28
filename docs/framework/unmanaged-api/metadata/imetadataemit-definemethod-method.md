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
ms.openlocfilehash: 514f227e3c0c385f61090079d2f5214dac9b3924
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84004535"
---
# <a name="imetadataemitdefinemethod-method"></a><span data-ttu-id="bf7f5-102">IMetaDataEmit::DefineMethod (Método)</span><span class="sxs-lookup"><span data-stu-id="bf7f5-102">IMetaDataEmit::DefineMethod Method</span></span>
<span data-ttu-id="bf7f5-103">Crea una definición para un método o una función global con la firma especificada y devuelve un token a esa definición de método.</span><span class="sxs-lookup"><span data-stu-id="bf7f5-103">Creates a definition for a method or global function with the specified signature, and returns a token to that method definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf7f5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bf7f5-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="bf7f5-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bf7f5-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="bf7f5-106">de `mdTypedef`Token de la clase primaria o interfaz primaria del método.</span><span class="sxs-lookup"><span data-stu-id="bf7f5-106">[in] The `mdTypedef` token of the parent class or parent interface of the method.</span></span> <span data-ttu-id="bf7f5-107">`td`Se establece en `mdTokenNil` si se define una función global.</span><span class="sxs-lookup"><span data-stu-id="bf7f5-107">Set `td` to `mdTokenNil`, if you are defining a global function.</span></span>  
  
 `szName`  
 <span data-ttu-id="bf7f5-108">de Nombre del miembro en Unicode.</span><span class="sxs-lookup"><span data-stu-id="bf7f5-108">[in] The member name in Unicode.</span></span>  
  
 `dwMethodFlags`  
 <span data-ttu-id="bf7f5-109">de Un valor de la enumeración [cormethodattr (](cormethodattr-enumeration.md) que especifica los atributos del método o la función global.</span><span class="sxs-lookup"><span data-stu-id="bf7f5-109">[in] A value of the [CorMethodAttr](cormethodattr-enumeration.md) enumeration that specifies the attributes of the method or global function.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="bf7f5-110">de La firma del método.</span><span class="sxs-lookup"><span data-stu-id="bf7f5-110">[in] The method signature.</span></span> <span data-ttu-id="bf7f5-111">La firma se conserva como se proporciona.</span><span class="sxs-lookup"><span data-stu-id="bf7f5-111">The signature is persisted as supplied.</span></span> <span data-ttu-id="bf7f5-112">Si necesita especificar información adicional para cualquier parámetro, use el método [IMetaDataEmit:: setparamprops (](imetadataemit-setparamprops-method.md) .</span><span class="sxs-lookup"><span data-stu-id="bf7f5-112">If you need to specify additional information for any parameters, use the [IMetaDataEmit::SetParamProps](imetadataemit-setparamprops-method.md) method.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="bf7f5-113">de Recuento de bytes de `pvSigBlob` .</span><span class="sxs-lookup"><span data-stu-id="bf7f5-113">[in] The count of bytes in `pvSigBlob`.</span></span>  
  
 `ulCodeRVA`  
 <span data-ttu-id="bf7f5-114">de Dirección del código.</span><span class="sxs-lookup"><span data-stu-id="bf7f5-114">[in] The address of the code.</span></span>  
  
 `dwImplFlags`  
 <span data-ttu-id="bf7f5-115">de Un valor de la enumeración [CorMethodImpl (](cormethodimpl-enumeration.md) que especifica las características de implementación del método.</span><span class="sxs-lookup"><span data-stu-id="bf7f5-115">[in] A value of the [CorMethodImpl](cormethodimpl-enumeration.md) enumeration that specifies the implementation features of the method.</span></span>  
  
 `pmd`  
 <span data-ttu-id="bf7f5-116">enuncia El token de miembro.</span><span class="sxs-lookup"><span data-stu-id="bf7f5-116">[out] The member token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bf7f5-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bf7f5-117">Remarks</span></span>  
 <span data-ttu-id="bf7f5-118">La API de metadatos garantiza la persistencia de los métodos en el mismo orden que el llamador los emite para una clase o interfaz envolvente determinada, que se especifica en el `td` parámetro.</span><span class="sxs-lookup"><span data-stu-id="bf7f5-118">The metadata API guarantees to persist methods in the same order as the caller emits them for a given enclosing class or interface, which is specified in the `td` parameter.</span></span>  
  
 <span data-ttu-id="bf7f5-119">A continuación se proporciona información adicional sobre el uso de `DefineMethod` y los valores de parámetros concretos.</span><span class="sxs-lookup"><span data-stu-id="bf7f5-119">Additional information regarding the use of `DefineMethod` and particular parameter settings is given below.</span></span>  
  
## <a name="slots-in-the-v-table"></a><span data-ttu-id="bf7f5-120">Ranuras de la tabla V</span><span class="sxs-lookup"><span data-stu-id="bf7f5-120">Slots in the V-table</span></span>  
 <span data-ttu-id="bf7f5-121">El motor en tiempo de ejecución utiliza definiciones de método para configurar las ranuras de la tabla v.</span><span class="sxs-lookup"><span data-stu-id="bf7f5-121">The runtime uses method definitions to set up v-table slots.</span></span> <span data-ttu-id="bf7f5-122">En el caso de que sea necesario omitir una o más ranuras, como conservar la paridad con un diseño de interfaz COM, se define un método ficticio para ocupar la ranura o las ranuras de la tabla v. establezca `dwMethodFlags` en el `mdRTSpecialName` valor de la enumeración [cormethodattr (](cormethodattr-enumeration.md) y especifique el nombre como:</span><span class="sxs-lookup"><span data-stu-id="bf7f5-122">In the case where one or more slots need to be skipped, such as to preserve parity with a COM interface layout, a dummy method is defined to take up the slot or slots in the v-table; set the `dwMethodFlags` to the `mdRTSpecialName` value of the [CorMethodAttr](cormethodattr-enumeration.md) enumeration and specify the name as:</span></span>  
  
 <span data-ttu-id="bf7f5-123">_VtblGap\<*SequenceNumber*>\<\_*CountOfSlots*></span><span class="sxs-lookup"><span data-stu-id="bf7f5-123">_VtblGap\<*SequenceNumber*>\<\_*CountOfSlots*></span></span>
  
 <span data-ttu-id="bf7f5-124">donde *SequenceNumber* es el número de secuencia del método y *CountOfSlots* es el número de ranuras que se van a omitir en la tabla v.</span><span class="sxs-lookup"><span data-stu-id="bf7f5-124">where *SequenceNumber* is the sequence number of the method and *CountOfSlots* is the number of slots to skip in the v-table.</span></span> <span data-ttu-id="bf7f5-125">Si se omite *CountOfSlots* , se asume 1.</span><span class="sxs-lookup"><span data-stu-id="bf7f5-125">If *CountOfSlots* is omitted, 1 is assumed.</span></span> <span data-ttu-id="bf7f5-126">Estos métodos ficticios no son Invocables desde código administrado o no administrado, y cualquier intento de llamarlos, desde código administrado o no administrado, genera una excepción.</span><span class="sxs-lookup"><span data-stu-id="bf7f5-126">These dummy methods are not callable from either managed or unmanaged code and any attempt to call them, from either managed or unmanaged code, generates an exception.</span></span> <span data-ttu-id="bf7f5-127">Su única finalidad es ocupar espacio en la tabla v que el Runtime genera para la integración COM.</span><span class="sxs-lookup"><span data-stu-id="bf7f5-127">Their only purpose is to take up space in the v-table that the runtime generates for COM integration.</span></span>  
  
## <a name="duplicate-methods"></a><span data-ttu-id="bf7f5-128">Métodos duplicados</span><span class="sxs-lookup"><span data-stu-id="bf7f5-128">Duplicate Methods</span></span>  
 <span data-ttu-id="bf7f5-129">No debe definir métodos duplicados.</span><span class="sxs-lookup"><span data-stu-id="bf7f5-129">You should not define duplicate methods.</span></span> <span data-ttu-id="bf7f5-130">Es decir, no debe llamar a `DefineMethod` con un conjunto duplicado de valores en `td` los `wzName` parámetros, y `pvSig` .</span><span class="sxs-lookup"><span data-stu-id="bf7f5-130">That is, you should not call `DefineMethod` with a duplicate set of values in the `td`, `wzName`, and `pvSig` parameters.</span></span> <span data-ttu-id="bf7f5-131">(Estos tres parámetros juntos definen de forma única el método).</span><span class="sxs-lookup"><span data-stu-id="bf7f5-131">(These three parameters together uniquely define the method.).</span></span> <span data-ttu-id="bf7f5-132">Sin embargo, puede usar un triple duplicado, siempre y cuando, para una de las definiciones de método, establezca el `mdPrivateScope` bit en el `dwMethodFlags` parámetro.</span><span class="sxs-lookup"><span data-stu-id="bf7f5-132">However, you can use a duplicate triple provided that, for one of the method definitions, you set the `mdPrivateScope` bit in the `dwMethodFlags` parameter.</span></span> <span data-ttu-id="bf7f5-133">(El `mdPrivateScope` bit significa que el compilador no emitirá una referencia a esta definición de método).</span><span class="sxs-lookup"><span data-stu-id="bf7f5-133">(The `mdPrivateScope` bit means that the compiler will not emit a reference to this method definition.)</span></span>  
  
## <a name="method-implementation-information"></a><span data-ttu-id="bf7f5-134">Información de implementación de método</span><span class="sxs-lookup"><span data-stu-id="bf7f5-134">Method Implementation Information</span></span>  
 <span data-ttu-id="bf7f5-135">A menudo, no se conoce la información sobre la implementación del método en el momento en que se declara el método.</span><span class="sxs-lookup"><span data-stu-id="bf7f5-135">Information about the method implementation is often not known at the time the method is declared.</span></span> <span data-ttu-id="bf7f5-136">Por lo tanto, no es necesario pasar valores en los `ulCodeRVA` `dwImplFlags` parámetros y al llamar a `DefineMethod` .</span><span class="sxs-lookup"><span data-stu-id="bf7f5-136">Therefore, you do not need to pass values in the `ulCodeRVA` and `dwImplFlags` parameters when calling `DefineMethod`.</span></span> <span data-ttu-id="bf7f5-137">Los valores se pueden proporcionar más adelante a través de [IMetaDataEmit:: setmethodimplflags (](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmethodimplflags-method.md) o [IMetaDataEmit:: SetRVA (](imetadataemit-setrva-method.md), según corresponda.</span><span class="sxs-lookup"><span data-stu-id="bf7f5-137">The values can be supplied later through [IMetaDataEmit::SetMethodImplFlags](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmethodimplflags-method.md) or [IMetaDataEmit::SetRVA](imetadataemit-setrva-method.md), as appropriate.</span></span>  
  
 <span data-ttu-id="bf7f5-138">En algunas situaciones, como los escenarios de invocación de plataforma (PInvoke) o de interoperabilidad COM, el cuerpo del método no se proporcionará y `ulCodeRVA` debe establecerse en cero.</span><span class="sxs-lookup"><span data-stu-id="bf7f5-138">In some situations, such as platform invocation (PInvoke) or COM interop scenarios, the method body will not be supplied, and `ulCodeRVA` should be set to zero.</span></span> <span data-ttu-id="bf7f5-139">En estas situaciones, el método no debe etiquetarse como abstracto, porque el tiempo de ejecución buscará la implementación.</span><span class="sxs-lookup"><span data-stu-id="bf7f5-139">In these situations, the method should not be tagged as abstract, because the runtime will locate the implementation.</span></span>  
  
## <a name="defining-a-method-for-pinvoke"></a><span data-ttu-id="bf7f5-140">Definir un método para PInvoke</span><span class="sxs-lookup"><span data-stu-id="bf7f5-140">Defining a Method for PInvoke</span></span>  
 <span data-ttu-id="bf7f5-141">Para cada función no administrada a la que se va a llamar a través de PInvoke, debe definir un método administrado que represente la función de destino no administrada.</span><span class="sxs-lookup"><span data-stu-id="bf7f5-141">For each unmanaged function to be called through PInvoke, you must define a managed method that represents the target unmanaged function.</span></span> <span data-ttu-id="bf7f5-142">Para definir el método administrado, use `DefineMethod` con algunos de los parámetros establecidos en ciertos valores, dependiendo de la forma en que se utilice PInvoke:</span><span class="sxs-lookup"><span data-stu-id="bf7f5-142">To define the managed method, use `DefineMethod` with some of the parameters set to certain values, depending on the way in which PInvoke is used:</span></span>  
  
- <span data-ttu-id="bf7f5-143">True PInvoke: implica la invocación de un método externo no administrado que se encuentra en un archivo DLL no administrado.</span><span class="sxs-lookup"><span data-stu-id="bf7f5-143">True PInvoke - involves invocation of an external unmanaged method that resides in an unmanaged DLL.</span></span>  
  
- <span data-ttu-id="bf7f5-144">PInvoke local: implica la invocación de un método nativo no administrado que está incrustado en el módulo administrado actual.</span><span class="sxs-lookup"><span data-stu-id="bf7f5-144">Local PInvoke - involves invocation of a native unmanaged method that is embedded in the current managed module.</span></span>  
  
 <span data-ttu-id="bf7f5-145">La configuración de parámetros se indica en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="bf7f5-145">The parameter settings are given in the following table.</span></span>  
  
|<span data-ttu-id="bf7f5-146">Parámetro</span><span class="sxs-lookup"><span data-stu-id="bf7f5-146">Parameter</span></span>|<span data-ttu-id="bf7f5-147">Valores para PInvoke verdadero</span><span class="sxs-lookup"><span data-stu-id="bf7f5-147">Values for true PInvoke</span></span>|<span data-ttu-id="bf7f5-148">Valores de PInvoke local</span><span class="sxs-lookup"><span data-stu-id="bf7f5-148">Values for local PInvoke</span></span>|  
|---------------|-----------------------------|------------------------------|  
|`dwMethodFlags`||<span data-ttu-id="bf7f5-149">Establezca `mdStatic` ; borre `mdSynchronized` y `mdAbstract` .</span><span class="sxs-lookup"><span data-stu-id="bf7f5-149">Set `mdStatic`; clear `mdSynchronized` and `mdAbstract`.</span></span>|  
|`pvSigBlob`|<span data-ttu-id="bf7f5-150">Una firma de método Common Language Runtime (CLR) válida con parámetros que son tipos administrados válidos.</span><span class="sxs-lookup"><span data-stu-id="bf7f5-150">A valid common language runtime (CLR) method signature with parameters that are valid managed types.</span></span>|<span data-ttu-id="bf7f5-151">Firma de método CLR válida con parámetros que son tipos administrados válidos.</span><span class="sxs-lookup"><span data-stu-id="bf7f5-151">A valid CLR method signature with parameters that are valid managed types.</span></span>|  
|`ulCodeRVA`||<span data-ttu-id="bf7f5-152">0</span><span class="sxs-lookup"><span data-stu-id="bf7f5-152">0</span></span>|  
|`dwImplFlags`|<span data-ttu-id="bf7f5-153">Establezca `miCil` y `miManaged`.</span><span class="sxs-lookup"><span data-stu-id="bf7f5-153">Set `miCil` and `miManaged`.</span></span>|<span data-ttu-id="bf7f5-154">Establezca `miNative` y `miUnmanaged`.</span><span class="sxs-lookup"><span data-stu-id="bf7f5-154">Set `miNative` and `miUnmanaged`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bf7f5-155">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bf7f5-155">Requirements</span></span>  
 <span data-ttu-id="bf7f5-156">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bf7f5-156">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf7f5-157">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="bf7f5-157">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bf7f5-158">**Biblioteca:** Se utiliza como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="bf7f5-158">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bf7f5-159">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bf7f5-159">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf7f5-160">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bf7f5-160">See also</span></span>

- [<span data-ttu-id="bf7f5-161">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="bf7f5-161">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="bf7f5-162">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="bf7f5-162">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
