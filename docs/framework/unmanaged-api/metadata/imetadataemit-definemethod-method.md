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
ms.openlocfilehash: c46b075341742aac605537a08b762b3cf47ef35b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431803"
---
# <a name="imetadataemitdefinemethod-method"></a><span data-ttu-id="032f3-102">IMetaDataEmit::DefineMethod (Método)</span><span class="sxs-lookup"><span data-stu-id="032f3-102">IMetaDataEmit::DefineMethod Method</span></span>
<span data-ttu-id="032f3-103">Creates a definition for a method or global function with the specified signature, and returns a token to that method definition.</span><span class="sxs-lookup"><span data-stu-id="032f3-103">Creates a definition for a method or global function with the specified signature, and returns a token to that method definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="032f3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="032f3-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="032f3-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="032f3-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="032f3-106">[in] The `mdTypedef` token of the parent class or parent interface of the method.</span><span class="sxs-lookup"><span data-stu-id="032f3-106">[in] The `mdTypedef` token of the parent class or parent interface of the method.</span></span> <span data-ttu-id="032f3-107">Set `td` to `mdTokenNil`, if you are defining a global function.</span><span class="sxs-lookup"><span data-stu-id="032f3-107">Set `td` to `mdTokenNil`, if you are defining a global function.</span></span>  
  
 `szName`  
 <span data-ttu-id="032f3-108">[in] The member name in Unicode.</span><span class="sxs-lookup"><span data-stu-id="032f3-108">[in] The member name in Unicode.</span></span>  
  
 `dwMethodFlags`  
 <span data-ttu-id="032f3-109">[in] A value of the [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) enumeration that specifies the attributes of the method or global function.</span><span class="sxs-lookup"><span data-stu-id="032f3-109">[in] A value of the [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) enumeration that specifies the attributes of the method or global function.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="032f3-110">[in] The method signature.</span><span class="sxs-lookup"><span data-stu-id="032f3-110">[in] The method signature.</span></span> <span data-ttu-id="032f3-111">The signature is persisted as supplied.</span><span class="sxs-lookup"><span data-stu-id="032f3-111">The signature is persisted as supplied.</span></span> <span data-ttu-id="032f3-112">If you need to specify additional information for any parameters, use the [IMetaDataEmit::SetParamProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setparamprops-method.md) method.</span><span class="sxs-lookup"><span data-stu-id="032f3-112">If you need to specify additional information for any parameters, use the [IMetaDataEmit::SetParamProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setparamprops-method.md) method.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="032f3-113">[in] The count of bytes in `pvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="032f3-113">[in] The count of bytes in `pvSigBlob`.</span></span>  
  
 `ulCodeRVA`  
 <span data-ttu-id="032f3-114">[in] The address of the code.</span><span class="sxs-lookup"><span data-stu-id="032f3-114">[in] The address of the code.</span></span>  
  
 `dwImplFlags`  
 <span data-ttu-id="032f3-115">[in] A value of the [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) enumeration that specifies the implementation features of the method.</span><span class="sxs-lookup"><span data-stu-id="032f3-115">[in] A value of the [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) enumeration that specifies the implementation features of the method.</span></span>  
  
 `pmd`  
 <span data-ttu-id="032f3-116">[out] The member token.</span><span class="sxs-lookup"><span data-stu-id="032f3-116">[out] The member token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="032f3-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="032f3-117">Remarks</span></span>  
 <span data-ttu-id="032f3-118">The metadata API guarantees to persist methods in the same order as the caller emits them for a given enclosing class or interface, which is specified in the `td` parameter.</span><span class="sxs-lookup"><span data-stu-id="032f3-118">The metadata API guarantees to persist methods in the same order as the caller emits them for a given enclosing class or interface, which is specified in the `td` parameter.</span></span>  
  
 <span data-ttu-id="032f3-119">Additional information regarding the use of `DefineMethod` and particular parameter settings is given below.</span><span class="sxs-lookup"><span data-stu-id="032f3-119">Additional information regarding the use of `DefineMethod` and particular parameter settings is given below.</span></span>  
  
## <a name="slots-in-the-v-table"></a><span data-ttu-id="032f3-120">Slots in the V-table</span><span class="sxs-lookup"><span data-stu-id="032f3-120">Slots in the V-table</span></span>  
 <span data-ttu-id="032f3-121">The runtime uses method definitions to set up v-table slots.</span><span class="sxs-lookup"><span data-stu-id="032f3-121">The runtime uses method definitions to set up v-table slots.</span></span> <span data-ttu-id="032f3-122">In the case where one or more slots need to be skipped, such as to preserve parity with a COM interface layout, a dummy method is defined to take up the slot or slots in the v-table; set the `dwMethodFlags` to the `mdRTSpecialName` value of the [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) enumeration and specify the name as:</span><span class="sxs-lookup"><span data-stu-id="032f3-122">In the case where one or more slots need to be skipped, such as to preserve parity with a COM interface layout, a dummy method is defined to take up the slot or slots in the v-table; set the `dwMethodFlags` to the `mdRTSpecialName` value of the [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) enumeration and specify the name as:</span></span>  
  
 <span data-ttu-id="032f3-123">_VtblGap\<*SequenceNumber*>\<\_*CountOfSlots*></span><span class="sxs-lookup"><span data-stu-id="032f3-123">_VtblGap\<*SequenceNumber*>\<\_*CountOfSlots*></span></span>
  
 <span data-ttu-id="032f3-124">where *SequenceNumber* is the sequence number of the method and *CountOfSlots* is the number of slots to skip in the v-table.</span><span class="sxs-lookup"><span data-stu-id="032f3-124">where *SequenceNumber* is the sequence number of the method and *CountOfSlots* is the number of slots to skip in the v-table.</span></span> <span data-ttu-id="032f3-125">If *CountOfSlots* is omitted, 1 is assumed.</span><span class="sxs-lookup"><span data-stu-id="032f3-125">If *CountOfSlots* is omitted, 1 is assumed.</span></span> <span data-ttu-id="032f3-126">These dummy methods are not callable from either managed or unmanaged code and any attempt to call them, from either managed or unmanaged code, generates an exception.</span><span class="sxs-lookup"><span data-stu-id="032f3-126">These dummy methods are not callable from either managed or unmanaged code and any attempt to call them, from either managed or unmanaged code, generates an exception.</span></span> <span data-ttu-id="032f3-127">Their only purpose is to take up space in the v-table that the runtime generates for COM integration.</span><span class="sxs-lookup"><span data-stu-id="032f3-127">Their only purpose is to take up space in the v-table that the runtime generates for COM integration.</span></span>  
  
## <a name="duplicate-methods"></a><span data-ttu-id="032f3-128">Duplicate Methods</span><span class="sxs-lookup"><span data-stu-id="032f3-128">Duplicate Methods</span></span>  
 <span data-ttu-id="032f3-129">You should not define duplicate methods.</span><span class="sxs-lookup"><span data-stu-id="032f3-129">You should not define duplicate methods.</span></span> <span data-ttu-id="032f3-130">That is, you should not call `DefineMethod` with a duplicate set of values in the `td`, `wzName`, and `pvSig` parameters.</span><span class="sxs-lookup"><span data-stu-id="032f3-130">That is, you should not call `DefineMethod` with a duplicate set of values in the `td`, `wzName`, and `pvSig` parameters.</span></span> <span data-ttu-id="032f3-131">(These three parameters together uniquely define the method.).</span><span class="sxs-lookup"><span data-stu-id="032f3-131">(These three parameters together uniquely define the method.).</span></span> <span data-ttu-id="032f3-132">However, you can use a duplicate triple provided that, for one of the method definitions, you set the `mdPrivateScope` bit in the `dwMethodFlags` parameter.</span><span class="sxs-lookup"><span data-stu-id="032f3-132">However, you can use a duplicate triple provided that, for one of the method definitions, you set the `mdPrivateScope` bit in the `dwMethodFlags` parameter.</span></span> <span data-ttu-id="032f3-133">(The `mdPrivateScope` bit means that the compiler will not emit a reference to this method definition.)</span><span class="sxs-lookup"><span data-stu-id="032f3-133">(The `mdPrivateScope` bit means that the compiler will not emit a reference to this method definition.)</span></span>  
  
## <a name="method-implementation-information"></a><span data-ttu-id="032f3-134">Method Implementation Information</span><span class="sxs-lookup"><span data-stu-id="032f3-134">Method Implementation Information</span></span>  
 <span data-ttu-id="032f3-135">Information about the method implementation is often not known at the time the method is declared.</span><span class="sxs-lookup"><span data-stu-id="032f3-135">Information about the method implementation is often not known at the time the method is declared.</span></span> <span data-ttu-id="032f3-136">Therefore, you do not need to pass values in the `ulCodeRVA` and `dwImplFlags` parameters when calling `DefineMethod`.</span><span class="sxs-lookup"><span data-stu-id="032f3-136">Therefore, you do not need to pass values in the `ulCodeRVA` and `dwImplFlags` parameters when calling `DefineMethod`.</span></span> <span data-ttu-id="032f3-137">The values can be supplied later through [IMetaDataEmit::SetMethodImplFlags](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmethodimplflags-method.md) or [IMetaDataEmit::SetRVA](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setrva-method.md), as appropriate.</span><span class="sxs-lookup"><span data-stu-id="032f3-137">The values can be supplied later through [IMetaDataEmit::SetMethodImplFlags](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmethodimplflags-method.md) or [IMetaDataEmit::SetRVA](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setrva-method.md), as appropriate.</span></span>  
  
 <span data-ttu-id="032f3-138">In some situations, such as platform invocation (PInvoke) or COM interop scenarios, the method body will not be supplied, and `ulCodeRVA` should be set to zero.</span><span class="sxs-lookup"><span data-stu-id="032f3-138">In some situations, such as platform invocation (PInvoke) or COM interop scenarios, the method body will not be supplied, and `ulCodeRVA` should be set to zero.</span></span> <span data-ttu-id="032f3-139">In these situations, the method should not be tagged as abstract, because the runtime will locate the implementation.</span><span class="sxs-lookup"><span data-stu-id="032f3-139">In these situations, the method should not be tagged as abstract, because the runtime will locate the implementation.</span></span>  
  
## <a name="defining-a-method-for-pinvoke"></a><span data-ttu-id="032f3-140">Defining a Method for PInvoke</span><span class="sxs-lookup"><span data-stu-id="032f3-140">Defining a Method for PInvoke</span></span>  
 <span data-ttu-id="032f3-141">For each unmanaged function to be called through PInvoke, you must define a managed method that represents the target unmanaged function.</span><span class="sxs-lookup"><span data-stu-id="032f3-141">For each unmanaged function to be called through PInvoke, you must define a managed method that represents the target unmanaged function.</span></span> <span data-ttu-id="032f3-142">To define the managed method, use `DefineMethod` with some of the parameters set to certain values, depending on the way in which PInvoke is used:</span><span class="sxs-lookup"><span data-stu-id="032f3-142">To define the managed method, use `DefineMethod` with some of the parameters set to certain values, depending on the way in which PInvoke is used:</span></span>  
  
- <span data-ttu-id="032f3-143">True PInvoke - involves invocation of an external unmanaged method that resides in an unmanaged DLL.</span><span class="sxs-lookup"><span data-stu-id="032f3-143">True PInvoke - involves invocation of an external unmanaged method that resides in an unmanaged DLL.</span></span>  
  
- <span data-ttu-id="032f3-144">Local PInvoke - involves invocation of a native unmanaged method that is embedded in the current managed module.</span><span class="sxs-lookup"><span data-stu-id="032f3-144">Local PInvoke - involves invocation of a native unmanaged method that is embedded in the current managed module.</span></span>  
  
 <span data-ttu-id="032f3-145">The parameter settings are given in the following table.</span><span class="sxs-lookup"><span data-stu-id="032f3-145">The parameter settings are given in the following table.</span></span>  
  
|<span data-ttu-id="032f3-146">Parámetro</span><span class="sxs-lookup"><span data-stu-id="032f3-146">Parameter</span></span>|<span data-ttu-id="032f3-147">Values for true PInvoke</span><span class="sxs-lookup"><span data-stu-id="032f3-147">Values for true PInvoke</span></span>|<span data-ttu-id="032f3-148">Values for local PInvoke</span><span class="sxs-lookup"><span data-stu-id="032f3-148">Values for local PInvoke</span></span>|  
|---------------|-----------------------------|------------------------------|  
|`dwMethodFlags`||<span data-ttu-id="032f3-149">Set `mdStatic`; clear `mdSynchronized` and `mdAbstract`.</span><span class="sxs-lookup"><span data-stu-id="032f3-149">Set `mdStatic`; clear `mdSynchronized` and `mdAbstract`.</span></span>|  
|`pvSigBlob`|<span data-ttu-id="032f3-150">A valid common language runtime (CLR) method signature with parameters that are valid managed types.</span><span class="sxs-lookup"><span data-stu-id="032f3-150">A valid common language runtime (CLR) method signature with parameters that are valid managed types.</span></span>|<span data-ttu-id="032f3-151">A valid CLR method signature with parameters that are valid managed types.</span><span class="sxs-lookup"><span data-stu-id="032f3-151">A valid CLR method signature with parameters that are valid managed types.</span></span>|  
|`ulCodeRVA`||<span data-ttu-id="032f3-152">0</span><span class="sxs-lookup"><span data-stu-id="032f3-152">0</span></span>|  
|`dwImplFlags`|<span data-ttu-id="032f3-153">Set `miCil` and `miManaged`.</span><span class="sxs-lookup"><span data-stu-id="032f3-153">Set `miCil` and `miManaged`.</span></span>|<span data-ttu-id="032f3-154">Set `miNative` and `miUnmanaged`.</span><span class="sxs-lookup"><span data-stu-id="032f3-154">Set `miNative` and `miUnmanaged`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="032f3-155">Requisitos</span><span class="sxs-lookup"><span data-stu-id="032f3-155">Requirements</span></span>  
 <span data-ttu-id="032f3-156">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="032f3-156">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="032f3-157">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="032f3-157">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="032f3-158">**Library:** Used as a resource in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="032f3-158">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="032f3-159">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="032f3-159">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="032f3-160">Vea también</span><span class="sxs-lookup"><span data-stu-id="032f3-160">See also</span></span>

- [<span data-ttu-id="032f3-161">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="032f3-161">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="032f3-162">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="032f3-162">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
