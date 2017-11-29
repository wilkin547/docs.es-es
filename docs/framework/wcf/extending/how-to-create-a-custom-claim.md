---
title: "Cómo crear una notificación personalizada"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: d619976b-eda3-475e-ac23-c7988a2dceb0
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: e1e85d1815d1fbde25e1963a54cce8f02f5344a8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-custom-claim"></a><span data-ttu-id="f56ec-102">Cómo crear una notificación personalizada</span><span class="sxs-lookup"><span data-stu-id="f56ec-102">How to: Create a Custom Claim</span></span>
<span data-ttu-id="f56ec-103">La infraestructura del modelo de identidad en [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] proporciona un conjunto de derechos y tipos de demanda integradas con las funciones auxiliares para crear instancias <xref:System.IdentityModel.Claims.Claim> con esos tipos y derechos.</span><span class="sxs-lookup"><span data-stu-id="f56ec-103">The Identity Model infrastructure in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] provides a set of built-in claim types and rights with the helper functions for creating <xref:System.IdentityModel.Claims.Claim> instances with those types and rights.</span></span> <span data-ttu-id="f56ec-104">Estas demandas integradas están diseñadas para modelar información en los tipos de credencial de un cliente que [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] admite de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="f56ec-104">These built-in claims are designed to model information found in client credential types that [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] supports by default.</span></span> <span data-ttu-id="f56ec-105">En muchos casos, las demandas integradas son suficientes; sin embargo, algunas aplicaciones pueden exigir demandas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="f56ec-105">In many cases, the built-in claims are sufficient; however some applications may require custom claims.</span></span> <span data-ttu-id="f56ec-106">Una demanda está compuesta por el tipo de demanda, el recurso para el que la demanda se aplica y el derecho que se impone sobre ese recurso.</span><span class="sxs-lookup"><span data-stu-id="f56ec-106">A claim consists of the claim type, the resource for which the claim applies to and the right that is asserted over that resource.</span></span> <span data-ttu-id="f56ec-107">En este tema se describe cómo crear una demanda personalizada.</span><span class="sxs-lookup"><span data-stu-id="f56ec-107">This topic describes how to create a custom claim.</span></span>  
  
### <a name="to-create-a-custom-claim-that-is-based-on-a-primitive-data-type"></a><span data-ttu-id="f56ec-108">Para crear una demanda personalizada que está basada en un tipo de datos primitivo</span><span class="sxs-lookup"><span data-stu-id="f56ec-108">To create a custom claim that is based on a primitive data type</span></span>  
  
1.  <span data-ttu-id="f56ec-109">Cree una demanda personalizada pasando el tipo de demanda, valor de recurso y derecho al constructor <xref:System.IdentityModel.Claims.Claim.%23ctor%28System.String%2CSystem.Object%2CSystem.String%29>.</span><span class="sxs-lookup"><span data-stu-id="f56ec-109">Create a custom claim by passing the claim type, resource value and right to the <xref:System.IdentityModel.Claims.Claim.%23ctor%28System.String%2CSystem.Object%2CSystem.String%29> constructor.</span></span>  
  
    1.  <span data-ttu-id="f56ec-110">Seleccione un valor único para el tipo de demanda.</span><span class="sxs-lookup"><span data-stu-id="f56ec-110">Decide on a unique value for the claim type.</span></span>  
  
         <span data-ttu-id="f56ec-111">El tipo de demanda es un identificador de cadena único.</span><span class="sxs-lookup"><span data-stu-id="f56ec-111">The claim type is a unique string identifier.</span></span> <span data-ttu-id="f56ec-112">Es la responsabilidad del diseñador de la demanda personalizada asegurar que el identificador de cadena que se usa para el tipo de demanda sea único.</span><span class="sxs-lookup"><span data-stu-id="f56ec-112">It is the custom claim designer's responsibility to ensure that the string identifier that is used for the claim type is unique.</span></span> <span data-ttu-id="f56ec-113">Si necesita más información sobre la lista de tipos de demanda definidos por [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], consulte la clase <xref:System.IdentityModel.Claims.ClaimTypes>.</span><span class="sxs-lookup"><span data-stu-id="f56ec-113">For a list of claim types that are defined by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], see the <xref:System.IdentityModel.Claims.ClaimTypes> class.</span></span>  
  
    2.  <span data-ttu-id="f56ec-114">Elija el tipo de datos primitivo y el valor para el recurso.</span><span class="sxs-lookup"><span data-stu-id="f56ec-114">Choose the primitive data type and value for the resource.</span></span>  
  
         <span data-ttu-id="f56ec-115">Un recurso es un objeto.</span><span class="sxs-lookup"><span data-stu-id="f56ec-115">A resource is an object.</span></span> <span data-ttu-id="f56ec-116">El tipo CLR del recurso puede ser primitivo, como <xref:System.String> o <xref:System.Int32>, así como cualquier tipo serializable.</span><span class="sxs-lookup"><span data-stu-id="f56ec-116">The CLR type of the resource can be a primitive, such as <xref:System.String> or <xref:System.Int32>, or any serializable type.</span></span> <span data-ttu-id="f56ec-117">El tipo CLR del recurso debe ser serializable, porque las demandas se serializan en varios puntos a través de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f56ec-117">The CLR type of the resource must be serializable, because claims are serialized at various points by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span> <span data-ttu-id="f56ec-118">Los tipos primitivos son serializables.</span><span class="sxs-lookup"><span data-stu-id="f56ec-118">Primitive types are serializable.</span></span>  
  
    3.  <span data-ttu-id="f56ec-119">Elija un derecho definido por [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] o un valor único para un derecho personalizado.</span><span class="sxs-lookup"><span data-stu-id="f56ec-119">Choose a right that is defined by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] or a unique value for a custom right.</span></span>  
  
         <span data-ttu-id="f56ec-120">Un derecho es un identificador de cadena único.</span><span class="sxs-lookup"><span data-stu-id="f56ec-120">A right is a unique string identifier.</span></span> <span data-ttu-id="f56ec-121">Los derecho definidos por [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] se definen en la clase <xref:System.IdentityModel.Claims.Rights>.</span><span class="sxs-lookup"><span data-stu-id="f56ec-121">The rights that are defined by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] are defined in the <xref:System.IdentityModel.Claims.Rights> class.</span></span>  
  
         <span data-ttu-id="f56ec-122">Es la responsabilidad del diseñador de la demanda personalizada asegurar que el identificador de cadena que se usa para el derecho sea único.</span><span class="sxs-lookup"><span data-stu-id="f56ec-122">It is the custom claim designer's responsibility to ensure that the string identifier that is used for the right is unique.</span></span>  
  
         <span data-ttu-id="f56ec-123">El ejemplo de código siguiente crea una demanda personalizada con un tipo de demanda de `http://example.org/claims/simplecustomclaim`, para un recurso denominado `Driver's License` y con el derecho <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A>.</span><span class="sxs-lookup"><span data-stu-id="f56ec-123">The following code example creates a custom claim with a claim type of `http://example.org/claims/simplecustomclaim`, for a resource named `Driver's License`, and with the <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A> right.</span></span>  
  
     [!code-csharp[c_CustomClaim#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaim/cs/c_customclaim.cs#4)]
     [!code-vb[c_CustomClaim#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaim/vb/c_customclaim.vb#4)]  
  
### <a name="to-create-a-custom-claim-that-is-based-on-a-non-primitive-data-type"></a><span data-ttu-id="f56ec-124">Para crear una demanda personalizada basada en un tipo de datos no primitivo</span><span class="sxs-lookup"><span data-stu-id="f56ec-124">To create a custom claim that is based on a non-primitive data type</span></span>  
  
1.  <span data-ttu-id="f56ec-125">Cree una demanda personalizada pasando el tipo de demanda, valor de recurso y derecho al constructor <xref:System.IdentityModel.Claims.Claim.%23ctor%28System.String%2CSystem.Object%2CSystem.String%29>.</span><span class="sxs-lookup"><span data-stu-id="f56ec-125">Create a custom claim by passing the claim type, resource value and right to the <xref:System.IdentityModel.Claims.Claim.%23ctor%28System.String%2CSystem.Object%2CSystem.String%29> constructor.</span></span>  
  
    1.  <span data-ttu-id="f56ec-126">Seleccione un valor único para el tipo de demanda.</span><span class="sxs-lookup"><span data-stu-id="f56ec-126">Decide on a unique value for the claim type.</span></span>  
  
         <span data-ttu-id="f56ec-127">El tipo de demanda es un identificador de cadena único.</span><span class="sxs-lookup"><span data-stu-id="f56ec-127">The claim type is a unique string identifier.</span></span> <span data-ttu-id="f56ec-128">Es la responsabilidad del diseñador de la demanda personalizada asegurar que el identificador de cadena que se usa para el tipo de demanda sea único.</span><span class="sxs-lookup"><span data-stu-id="f56ec-128">It is the custom claim designer's responsibility to ensure that the string identifier that is used for the claim type is unique.</span></span> <span data-ttu-id="f56ec-129">Si necesita más información sobre la lista de tipos de demanda definidos por [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], consulte la clase <xref:System.IdentityModel.Claims.ClaimTypes>.</span><span class="sxs-lookup"><span data-stu-id="f56ec-129">For a list of claim types that are defined by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], see the <xref:System.IdentityModel.Claims.ClaimTypes> class.</span></span>  
  
    2.  <span data-ttu-id="f56ec-130">Elija o defina un tipo no primitivo serializable para el recurso.</span><span class="sxs-lookup"><span data-stu-id="f56ec-130">Choose or define a serializable non-primitive type for the resource.</span></span>  
  
         <span data-ttu-id="f56ec-131">Un recurso es un objeto.</span><span class="sxs-lookup"><span data-stu-id="f56ec-131">A resource is an object.</span></span> <span data-ttu-id="f56ec-132">El tipo CLR del recurso debe ser serializable, porque las demandas se serializan en varios puntos a través de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f56ec-132">The CLR type of the resource must be serializable, because claims are serialized at various points by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span> <span data-ttu-id="f56ec-133">Los tipos primitivos ya son serializables.</span><span class="sxs-lookup"><span data-stu-id="f56ec-133">Primitive types are already serializable.</span></span>  
  
         <span data-ttu-id="f56ec-134">Cuando se define un nuevo tipo, aplique <xref:System.Runtime.Serialization.DataContractAttribute> a la clase.</span><span class="sxs-lookup"><span data-stu-id="f56ec-134">When a new type is defined, apply the <xref:System.Runtime.Serialization.DataContractAttribute> to the class.</span></span> <span data-ttu-id="f56ec-135">Aplique también el atributo <xref:System.Runtime.Serialization.DataMemberAttribute> a todos los miembros del nuevo tipo que necesiten ser serializados como parte de la demanda.</span><span class="sxs-lookup"><span data-stu-id="f56ec-135">Also apply the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute to the all members of the new type that need to be serialized as part of the claim.</span></span>  
  
         <span data-ttu-id="f56ec-136">El ejemplo de código siguiente define un tipo de recurso personalizado denominado `MyResourceType`.</span><span class="sxs-lookup"><span data-stu-id="f56ec-136">The following code example defines a custom resource type named `MyResourceType`.</span></span>  
  
         [!code-csharp[c_CustomClaim#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaim/cs/c_customclaim.cs#2)] 
         [!code-vb[c_CustomClaim#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaim/vb/c_customclaim.vb#2)]        
  
    3.  <span data-ttu-id="f56ec-137">Elija un derecho definido por [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] o un valor único para un derecho personalizado.</span><span class="sxs-lookup"><span data-stu-id="f56ec-137">Choose a right that is defined by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] or a unique value for a custom right.</span></span>  
  
         <span data-ttu-id="f56ec-138">Un derecho es un identificador de cadena único.</span><span class="sxs-lookup"><span data-stu-id="f56ec-138">A right is a unique string identifier.</span></span> <span data-ttu-id="f56ec-139">Los derecho definidos por [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] se definen en la clase <xref:System.IdentityModel.Claims.Rights>.</span><span class="sxs-lookup"><span data-stu-id="f56ec-139">The rights that are defined by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] are defined in the <xref:System.IdentityModel.Claims.Rights> class.</span></span>  
  
         <span data-ttu-id="f56ec-140">Es la responsabilidad del diseñador de la demanda personalizada asegurar que el identificador de cadena que se usa para el derecho sea único.</span><span class="sxs-lookup"><span data-stu-id="f56ec-140">It is the custom claim designer's responsibility to ensure that the string identifier that is used for the right is unique.</span></span>  
  
         <span data-ttu-id="f56ec-141">El ejemplo de código siguiente crea una demanda personalizada con un tipo de demanda de `http://example.org/claims/complexcustomclaim`, un tipo de recurso personalizado de `MyResourceType` y con el derecho <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A>.</span><span class="sxs-lookup"><span data-stu-id="f56ec-141">The following code example creates a custom claim with a claim type of `http://example.org/claims/complexcustomclaim`, a custom resource type of `MyResourceType`, and with the <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A> right.</span></span>  
  
         [!code-csharp[c_CustomClaim#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaim/cs/c_customclaim.cs#5)] 
         [!code-vb[c_CustomClaim#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaim/vb/c_customclaim.vb#5)]     
  
## <a name="example"></a><span data-ttu-id="f56ec-142">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f56ec-142">Example</span></span>  
 <span data-ttu-id="f56ec-143">El ejemplo de código siguiente muestra cómo crear una demanda personalizada con un tipo de recurso primitivo y una demanda personalizada con un tipo de recurso no primitivo.</span><span class="sxs-lookup"><span data-stu-id="f56ec-143">The following code example demonstrates how to create a custom claim with a primitive resource type and a custom claim with a non-primitive resource type.</span></span>  
  
 [!code-csharp[c_CustomClaim#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaim/cs/c_customclaim.cs#0)]
 [!code-vb[c_CustomClaim#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaim/vb/c_customclaim.vb#0)]  
  
## <a name="see-also"></a><span data-ttu-id="f56ec-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="f56ec-144">See Also</span></span>  
 <xref:System.IdentityModel.Claims.Claim>  
 <xref:System.IdentityModel.Claims.Rights>  
 <xref:System.IdentityModel.Claims.ClaimTypes>  
 <xref:System.Runtime.Serialization.DataContractAttribute>  
 <xref:System.Runtime.Serialization.DataMemberAttribute>  
 [<span data-ttu-id="f56ec-145">Administración de notificaciones y autorización con el modelo de identidad</span><span class="sxs-lookup"><span data-stu-id="f56ec-145">Managing Claims and Authorization with the Identity Model</span></span>](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)  
 [<span data-ttu-id="f56ec-146">Administración de notificaciones y autorización con el modelo de identidad</span><span class="sxs-lookup"><span data-stu-id="f56ec-146">Managing Claims and Authorization with the Identity Model</span></span>](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)
