---
title: Procedimiento para crear una notificación personalizada
description: Obtenga información sobre cómo crear una demanda personalizada en WCF. WCF admite una variedad de notificaciones integradas y algunas aplicaciones pueden requerir notificaciones personalizadas.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d619976b-eda3-475e-ac23-c7988a2dceb0
ms.openlocfilehash: ea3bc7384ca10538ca5ab1d3bb05da6a2757fb67
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96256019"
---
# <a name="how-to-create-a-custom-claim"></a><span data-ttu-id="2a8e7-104">Procedimiento para crear una notificación personalizada</span><span class="sxs-lookup"><span data-stu-id="2a8e7-104">How to: Create a Custom Claim</span></span>

<span data-ttu-id="2a8e7-105">La infraestructura del modelo de identidad de Windows Communication Foundation (WCF) proporciona un conjunto de tipos y derechos de notificaciones integrados con las funciones auxiliares para crear <xref:System.IdentityModel.Claims.Claim> instancias con esos tipos y derechos.</span><span class="sxs-lookup"><span data-stu-id="2a8e7-105">The Identity Model infrastructure in Windows Communication Foundation (WCF) provides a set of built-in claim types and rights with the helper functions for creating <xref:System.IdentityModel.Claims.Claim> instances with those types and rights.</span></span> <span data-ttu-id="2a8e7-106">Estas notificaciones integradas están diseñadas para modelar la información que se encuentra en los tipos de credenciales de cliente que WCF admite de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="2a8e7-106">These built-in claims are designed to model information found in client credential types that WCF supports by default.</span></span> <span data-ttu-id="2a8e7-107">En muchos casos, las demandas integradas son suficientes; sin embargo, algunas aplicaciones pueden exigir demandas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="2a8e7-107">In many cases, the built-in claims are sufficient; however some applications may require custom claims.</span></span> <span data-ttu-id="2a8e7-108">Una demanda está compuesta por el tipo de demanda, el recurso para el que la demanda se aplica y el derecho que se impone sobre ese recurso.</span><span class="sxs-lookup"><span data-stu-id="2a8e7-108">A claim consists of the claim type, the resource for which the claim applies to and the right that is asserted over that resource.</span></span> <span data-ttu-id="2a8e7-109">En este tema se describe cómo crear una demanda personalizada.</span><span class="sxs-lookup"><span data-stu-id="2a8e7-109">This topic describes how to create a custom claim.</span></span>  
  
### <a name="to-create-a-custom-claim-that-is-based-on-a-primitive-data-type"></a><span data-ttu-id="2a8e7-110">Para crear una demanda personalizada que está basada en un tipo de datos primitivo</span><span class="sxs-lookup"><span data-stu-id="2a8e7-110">To create a custom claim that is based on a primitive data type</span></span>  
  
1. <span data-ttu-id="2a8e7-111">Cree una demanda personalizada pasando el tipo de demanda, valor de recurso y derecho al constructor <xref:System.IdentityModel.Claims.Claim.%23ctor%28System.String%2CSystem.Object%2CSystem.String%29>.</span><span class="sxs-lookup"><span data-stu-id="2a8e7-111">Create a custom claim by passing the claim type, resource value and right to the <xref:System.IdentityModel.Claims.Claim.%23ctor%28System.String%2CSystem.Object%2CSystem.String%29> constructor.</span></span>  
  
    1. <span data-ttu-id="2a8e7-112">Seleccione un valor único para el tipo de demanda.</span><span class="sxs-lookup"><span data-stu-id="2a8e7-112">Decide on a unique value for the claim type.</span></span>  
  
         <span data-ttu-id="2a8e7-113">El tipo de demanda es un identificador de cadena único.</span><span class="sxs-lookup"><span data-stu-id="2a8e7-113">The claim type is a unique string identifier.</span></span> <span data-ttu-id="2a8e7-114">Es la responsabilidad del diseñador de la demanda personalizada asegurar que el identificador de cadena que se usa para el tipo de demanda sea único.</span><span class="sxs-lookup"><span data-stu-id="2a8e7-114">It is the custom claim designer's responsibility to ensure that the string identifier that is used for the claim type is unique.</span></span> <span data-ttu-id="2a8e7-115">Para obtener una lista de los tipos de notificaciones definidos por WCF, vea la <xref:System.IdentityModel.Claims.ClaimTypes> clase.</span><span class="sxs-lookup"><span data-stu-id="2a8e7-115">For a list of claim types that are defined by WCF, see the <xref:System.IdentityModel.Claims.ClaimTypes> class.</span></span>  
  
    2. <span data-ttu-id="2a8e7-116">Elija el tipo de datos primitivo y el valor para el recurso.</span><span class="sxs-lookup"><span data-stu-id="2a8e7-116">Choose the primitive data type and value for the resource.</span></span>  
  
         <span data-ttu-id="2a8e7-117">Un recurso es un objeto.</span><span class="sxs-lookup"><span data-stu-id="2a8e7-117">A resource is an object.</span></span> <span data-ttu-id="2a8e7-118">El tipo CLR del recurso puede ser primitivo, como <xref:System.String> o <xref:System.Int32>, así como cualquier tipo serializable.</span><span class="sxs-lookup"><span data-stu-id="2a8e7-118">The CLR type of the resource can be a primitive, such as <xref:System.String> or <xref:System.Int32>, or any serializable type.</span></span> <span data-ttu-id="2a8e7-119">El tipo CLR del recurso debe ser serializable, porque las notificaciones se serializan en varios puntos por WCF.</span><span class="sxs-lookup"><span data-stu-id="2a8e7-119">The CLR type of the resource must be serializable, because claims are serialized at various points by WCF.</span></span> <span data-ttu-id="2a8e7-120">Los tipos primitivos son serializables.</span><span class="sxs-lookup"><span data-stu-id="2a8e7-120">Primitive types are serializable.</span></span>  
  
    3. <span data-ttu-id="2a8e7-121">Elija un derecho definido por WCF o un valor único para un derecho personalizado.</span><span class="sxs-lookup"><span data-stu-id="2a8e7-121">Choose a right that is defined by WCF or a unique value for a custom right.</span></span>  
  
         <span data-ttu-id="2a8e7-122">Un derecho es un identificador de cadena único.</span><span class="sxs-lookup"><span data-stu-id="2a8e7-122">A right is a unique string identifier.</span></span> <span data-ttu-id="2a8e7-123">Los derechos definidos por WCF se definen en la <xref:System.IdentityModel.Claims.Rights> clase.</span><span class="sxs-lookup"><span data-stu-id="2a8e7-123">The rights that are defined by WCF are defined in the <xref:System.IdentityModel.Claims.Rights> class.</span></span>  
  
         <span data-ttu-id="2a8e7-124">Es la responsabilidad del diseñador de la demanda personalizada asegurar que el identificador de cadena que se usa para el derecho sea único.</span><span class="sxs-lookup"><span data-stu-id="2a8e7-124">It is the custom claim designer's responsibility to ensure that the string identifier that is used for the right is unique.</span></span>  
  
         <span data-ttu-id="2a8e7-125">El ejemplo de código siguiente crea una demanda personalizada con un tipo de demanda de `http://example.org/claims/simplecustomclaim`, para un recurso denominado `Driver's License` y con el derecho <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A>.</span><span class="sxs-lookup"><span data-stu-id="2a8e7-125">The following code example creates a custom claim with a claim type of `http://example.org/claims/simplecustomclaim`, for a resource named `Driver's License`, and with the <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A> right.</span></span>  
  
     [!code-csharp[c_CustomClaim#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaim/cs/c_customclaim.cs#4)]
     [!code-vb[c_CustomClaim#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaim/vb/c_customclaim.vb#4)]  
  
### <a name="to-create-a-custom-claim-that-is-based-on-a-non-primitive-data-type"></a><span data-ttu-id="2a8e7-126">Para crear una demanda personalizada basada en un tipo de datos no primitivo</span><span class="sxs-lookup"><span data-stu-id="2a8e7-126">To create a custom claim that is based on a non-primitive data type</span></span>  
  
1. <span data-ttu-id="2a8e7-127">Cree una demanda personalizada pasando el tipo de demanda, valor de recurso y derecho al constructor <xref:System.IdentityModel.Claims.Claim.%23ctor%28System.String%2CSystem.Object%2CSystem.String%29>.</span><span class="sxs-lookup"><span data-stu-id="2a8e7-127">Create a custom claim by passing the claim type, resource value and right to the <xref:System.IdentityModel.Claims.Claim.%23ctor%28System.String%2CSystem.Object%2CSystem.String%29> constructor.</span></span>  
  
    1. <span data-ttu-id="2a8e7-128">Seleccione un valor único para el tipo de demanda.</span><span class="sxs-lookup"><span data-stu-id="2a8e7-128">Decide on a unique value for the claim type.</span></span>  
  
         <span data-ttu-id="2a8e7-129">El tipo de demanda es un identificador de cadena único.</span><span class="sxs-lookup"><span data-stu-id="2a8e7-129">The claim type is a unique string identifier.</span></span> <span data-ttu-id="2a8e7-130">Es la responsabilidad del diseñador de la demanda personalizada asegurar que el identificador de cadena que se usa para el tipo de demanda sea único.</span><span class="sxs-lookup"><span data-stu-id="2a8e7-130">It is the custom claim designer's responsibility to ensure that the string identifier that is used for the claim type is unique.</span></span> <span data-ttu-id="2a8e7-131">Para obtener una lista de los tipos de notificaciones definidos por WCF, vea la <xref:System.IdentityModel.Claims.ClaimTypes> clase.</span><span class="sxs-lookup"><span data-stu-id="2a8e7-131">For a list of claim types that are defined by WCF, see the <xref:System.IdentityModel.Claims.ClaimTypes> class.</span></span>  
  
    2. <span data-ttu-id="2a8e7-132">Elija o defina un tipo no primitivo serializable para el recurso.</span><span class="sxs-lookup"><span data-stu-id="2a8e7-132">Choose or define a serializable non-primitive type for the resource.</span></span>  
  
         <span data-ttu-id="2a8e7-133">Un recurso es un objeto.</span><span class="sxs-lookup"><span data-stu-id="2a8e7-133">A resource is an object.</span></span> <span data-ttu-id="2a8e7-134">El tipo CLR del recurso debe ser serializable, porque las notificaciones se serializan en varios puntos por WCF.</span><span class="sxs-lookup"><span data-stu-id="2a8e7-134">The CLR type of the resource must be serializable, because claims are serialized at various points by WCF.</span></span> <span data-ttu-id="2a8e7-135">Los tipos primitivos ya son serializables.</span><span class="sxs-lookup"><span data-stu-id="2a8e7-135">Primitive types are already serializable.</span></span>  
  
         <span data-ttu-id="2a8e7-136">Cuando se define un nuevo tipo, aplique <xref:System.Runtime.Serialization.DataContractAttribute> a la clase.</span><span class="sxs-lookup"><span data-stu-id="2a8e7-136">When a new type is defined, apply the <xref:System.Runtime.Serialization.DataContractAttribute> to the class.</span></span> <span data-ttu-id="2a8e7-137">Aplique también el atributo <xref:System.Runtime.Serialization.DataMemberAttribute> a todos los miembros del nuevo tipo que necesiten ser serializados como parte de la demanda.</span><span class="sxs-lookup"><span data-stu-id="2a8e7-137">Also apply the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute to the all members of the new type that need to be serialized as part of the claim.</span></span>  
  
         <span data-ttu-id="2a8e7-138">El ejemplo de código siguiente define un tipo de recurso personalizado denominado `MyResourceType`.</span><span class="sxs-lookup"><span data-stu-id="2a8e7-138">The following code example defines a custom resource type named `MyResourceType`.</span></span>  
  
         [!code-csharp[c_CustomClaim#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaim/cs/c_customclaim.cs#2)]
         [!code-vb[c_CustomClaim#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaim/vb/c_customclaim.vb#2)]
  
    3. <span data-ttu-id="2a8e7-139">Elija un derecho definido por WCF o un valor único para un derecho personalizado.</span><span class="sxs-lookup"><span data-stu-id="2a8e7-139">Choose a right that is defined by WCF or a unique value for a custom right.</span></span>  
  
         <span data-ttu-id="2a8e7-140">Un derecho es un identificador de cadena único.</span><span class="sxs-lookup"><span data-stu-id="2a8e7-140">A right is a unique string identifier.</span></span> <span data-ttu-id="2a8e7-141">Los derechos definidos por WCF se definen en la <xref:System.IdentityModel.Claims.Rights> clase.</span><span class="sxs-lookup"><span data-stu-id="2a8e7-141">The rights that are defined by WCF are defined in the <xref:System.IdentityModel.Claims.Rights> class.</span></span>  
  
         <span data-ttu-id="2a8e7-142">Es la responsabilidad del diseñador de la demanda personalizada asegurar que el identificador de cadena que se usa para el derecho sea único.</span><span class="sxs-lookup"><span data-stu-id="2a8e7-142">It is the custom claim designer's responsibility to ensure that the string identifier that is used for the right is unique.</span></span>  
  
         <span data-ttu-id="2a8e7-143">El ejemplo de código siguiente crea una demanda personalizada con un tipo de demanda de `http://example.org/claims/complexcustomclaim`, un tipo de recurso personalizado de `MyResourceType` y con el derecho <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A>.</span><span class="sxs-lookup"><span data-stu-id="2a8e7-143">The following code example creates a custom claim with a claim type of `http://example.org/claims/complexcustomclaim`, a custom resource type of `MyResourceType`, and with the <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A> right.</span></span>  
  
         [!code-csharp[c_CustomClaim#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaim/cs/c_customclaim.cs#5)]
         [!code-vb[c_CustomClaim#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaim/vb/c_customclaim.vb#5)]
  
## <a name="example"></a><span data-ttu-id="2a8e7-144">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2a8e7-144">Example</span></span>  

 <span data-ttu-id="2a8e7-145">El ejemplo de código siguiente muestra cómo crear una demanda personalizada con un tipo de recurso primitivo y una demanda personalizada con un tipo de recurso no primitivo.</span><span class="sxs-lookup"><span data-stu-id="2a8e7-145">The following code example demonstrates how to create a custom claim with a primitive resource type and a custom claim with a non-primitive resource type.</span></span>  
  
 [!code-csharp[c_CustomClaim#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaim/cs/c_customclaim.cs#0)]
 [!code-vb[c_CustomClaim#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaim/vb/c_customclaim.vb#0)]  
  
## <a name="see-also"></a><span data-ttu-id="2a8e7-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="2a8e7-146">See also</span></span>

- <xref:System.IdentityModel.Claims.Claim>
- <xref:System.IdentityModel.Claims.Rights>
- <xref:System.IdentityModel.Claims.ClaimTypes>
- <xref:System.Runtime.Serialization.DataContractAttribute>
- <xref:System.Runtime.Serialization.DataMemberAttribute>
- [<span data-ttu-id="2a8e7-147">Administración de notificaciones y autorización con el modelo de identidad</span><span class="sxs-lookup"><span data-stu-id="2a8e7-147">Managing Claims and Authorization with the Identity Model</span></span>](../feature-details/managing-claims-and-authorization-with-the-identity-model.md)
