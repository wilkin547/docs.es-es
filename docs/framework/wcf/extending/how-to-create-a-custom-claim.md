---
title: Cómo crear una notificación personalizada
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d619976b-eda3-475e-ac23-c7988a2dceb0
ms.openlocfilehash: e78f577e0fd3473575fab998e55616936212ebb3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185617"
---
# <a name="how-to-create-a-custom-claim"></a><span data-ttu-id="30124-102">Cómo crear una notificación personalizada</span><span class="sxs-lookup"><span data-stu-id="30124-102">How to: Create a Custom Claim</span></span>
<span data-ttu-id="30124-103">La infraestructura del modelo de identidad en Windows Communication Foundation (WCF) proporciona un <xref:System.IdentityModel.Claims.Claim> conjunto de tipos de notificación integrados y derechos con las funciones auxiliares para crear instancias con esos tipos y derechos.</span><span class="sxs-lookup"><span data-stu-id="30124-103">The Identity Model infrastructure in Windows Communication Foundation (WCF) provides a set of built-in claim types and rights with the helper functions for creating <xref:System.IdentityModel.Claims.Claim> instances with those types and rights.</span></span> <span data-ttu-id="30124-104">Estas notificaciones integradas están diseñadas para modelar la información que se encuentra en los tipos de credenciales de cliente que WCF admite de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="30124-104">These built-in claims are designed to model information found in client credential types that WCF supports by default.</span></span> <span data-ttu-id="30124-105">En muchos casos, las demandas integradas son suficientes; sin embargo, algunas aplicaciones pueden exigir demandas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="30124-105">In many cases, the built-in claims are sufficient; however some applications may require custom claims.</span></span> <span data-ttu-id="30124-106">Una demanda está compuesta por el tipo de demanda, el recurso para el que la demanda se aplica y el derecho que se impone sobre ese recurso.</span><span class="sxs-lookup"><span data-stu-id="30124-106">A claim consists of the claim type, the resource for which the claim applies to and the right that is asserted over that resource.</span></span> <span data-ttu-id="30124-107">En este tema se describe cómo crear una demanda personalizada.</span><span class="sxs-lookup"><span data-stu-id="30124-107">This topic describes how to create a custom claim.</span></span>  
  
### <a name="to-create-a-custom-claim-that-is-based-on-a-primitive-data-type"></a><span data-ttu-id="30124-108">Para crear una demanda personalizada que está basada en un tipo de datos primitivo</span><span class="sxs-lookup"><span data-stu-id="30124-108">To create a custom claim that is based on a primitive data type</span></span>  
  
1. <span data-ttu-id="30124-109">Cree una demanda personalizada pasando el tipo de demanda, valor de recurso y derecho al constructor <xref:System.IdentityModel.Claims.Claim.%23ctor%28System.String%2CSystem.Object%2CSystem.String%29>.</span><span class="sxs-lookup"><span data-stu-id="30124-109">Create a custom claim by passing the claim type, resource value and right to the <xref:System.IdentityModel.Claims.Claim.%23ctor%28System.String%2CSystem.Object%2CSystem.String%29> constructor.</span></span>  
  
    1. <span data-ttu-id="30124-110">Seleccione un valor único para el tipo de demanda.</span><span class="sxs-lookup"><span data-stu-id="30124-110">Decide on a unique value for the claim type.</span></span>  
  
         <span data-ttu-id="30124-111">El tipo de demanda es un identificador de cadena único.</span><span class="sxs-lookup"><span data-stu-id="30124-111">The claim type is a unique string identifier.</span></span> <span data-ttu-id="30124-112">Es la responsabilidad del diseñador de la demanda personalizada asegurar que el identificador de cadena que se usa para el tipo de demanda sea único.</span><span class="sxs-lookup"><span data-stu-id="30124-112">It is the custom claim designer's responsibility to ensure that the string identifier that is used for the claim type is unique.</span></span> <span data-ttu-id="30124-113">Para obtener una lista de tipos de <xref:System.IdentityModel.Claims.ClaimTypes> notificación definidos por WCF, vea la clase.</span><span class="sxs-lookup"><span data-stu-id="30124-113">For a list of claim types that are defined by WCF, see the <xref:System.IdentityModel.Claims.ClaimTypes> class.</span></span>  
  
    2. <span data-ttu-id="30124-114">Elija el tipo de datos primitivo y el valor para el recurso.</span><span class="sxs-lookup"><span data-stu-id="30124-114">Choose the primitive data type and value for the resource.</span></span>  
  
         <span data-ttu-id="30124-115">Un recurso es un objeto.</span><span class="sxs-lookup"><span data-stu-id="30124-115">A resource is an object.</span></span> <span data-ttu-id="30124-116">El tipo CLR del recurso puede ser primitivo, como <xref:System.String> o <xref:System.Int32>, así como cualquier tipo serializable.</span><span class="sxs-lookup"><span data-stu-id="30124-116">The CLR type of the resource can be a primitive, such as <xref:System.String> or <xref:System.Int32>, or any serializable type.</span></span> <span data-ttu-id="30124-117">El tipo CLR del recurso debe ser serializable, porque WCF serializa las notificaciones en varios puntos.</span><span class="sxs-lookup"><span data-stu-id="30124-117">The CLR type of the resource must be serializable, because claims are serialized at various points by WCF.</span></span> <span data-ttu-id="30124-118">Los tipos primitivos son serializables.</span><span class="sxs-lookup"><span data-stu-id="30124-118">Primitive types are serializable.</span></span>  
  
    3. <span data-ttu-id="30124-119">Elija un derecho definido por WCF o un valor único para un derecho personalizado.</span><span class="sxs-lookup"><span data-stu-id="30124-119">Choose a right that is defined by WCF or a unique value for a custom right.</span></span>  
  
         <span data-ttu-id="30124-120">Un derecho es un identificador de cadena único.</span><span class="sxs-lookup"><span data-stu-id="30124-120">A right is a unique string identifier.</span></span> <span data-ttu-id="30124-121">Los derechos definidos por WCF <xref:System.IdentityModel.Claims.Rights> se definen en la clase.</span><span class="sxs-lookup"><span data-stu-id="30124-121">The rights that are defined by WCF are defined in the <xref:System.IdentityModel.Claims.Rights> class.</span></span>  
  
         <span data-ttu-id="30124-122">Es la responsabilidad del diseñador de la demanda personalizada asegurar que el identificador de cadena que se usa para el derecho sea único.</span><span class="sxs-lookup"><span data-stu-id="30124-122">It is the custom claim designer's responsibility to ensure that the string identifier that is used for the right is unique.</span></span>  
  
         <span data-ttu-id="30124-123">El ejemplo de código siguiente crea una demanda personalizada con un tipo de demanda de `http://example.org/claims/simplecustomclaim`, para un recurso denominado `Driver's License` y con el derecho <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A>.</span><span class="sxs-lookup"><span data-stu-id="30124-123">The following code example creates a custom claim with a claim type of `http://example.org/claims/simplecustomclaim`, for a resource named `Driver's License`, and with the <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A> right.</span></span>  
  
     [!code-csharp[c_CustomClaim#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaim/cs/c_customclaim.cs#4)]
     [!code-vb[c_CustomClaim#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaim/vb/c_customclaim.vb#4)]  
  
### <a name="to-create-a-custom-claim-that-is-based-on-a-non-primitive-data-type"></a><span data-ttu-id="30124-124">Para crear una demanda personalizada basada en un tipo de datos no primitivo</span><span class="sxs-lookup"><span data-stu-id="30124-124">To create a custom claim that is based on a non-primitive data type</span></span>  
  
1. <span data-ttu-id="30124-125">Cree una demanda personalizada pasando el tipo de demanda, valor de recurso y derecho al constructor <xref:System.IdentityModel.Claims.Claim.%23ctor%28System.String%2CSystem.Object%2CSystem.String%29>.</span><span class="sxs-lookup"><span data-stu-id="30124-125">Create a custom claim by passing the claim type, resource value and right to the <xref:System.IdentityModel.Claims.Claim.%23ctor%28System.String%2CSystem.Object%2CSystem.String%29> constructor.</span></span>  
  
    1. <span data-ttu-id="30124-126">Seleccione un valor único para el tipo de demanda.</span><span class="sxs-lookup"><span data-stu-id="30124-126">Decide on a unique value for the claim type.</span></span>  
  
         <span data-ttu-id="30124-127">El tipo de demanda es un identificador de cadena único.</span><span class="sxs-lookup"><span data-stu-id="30124-127">The claim type is a unique string identifier.</span></span> <span data-ttu-id="30124-128">Es la responsabilidad del diseñador de la demanda personalizada asegurar que el identificador de cadena que se usa para el tipo de demanda sea único.</span><span class="sxs-lookup"><span data-stu-id="30124-128">It is the custom claim designer's responsibility to ensure that the string identifier that is used for the claim type is unique.</span></span> <span data-ttu-id="30124-129">Para obtener una lista de tipos de <xref:System.IdentityModel.Claims.ClaimTypes> notificación definidos por WCF, vea la clase.</span><span class="sxs-lookup"><span data-stu-id="30124-129">For a list of claim types that are defined by WCF, see the <xref:System.IdentityModel.Claims.ClaimTypes> class.</span></span>  
  
    2. <span data-ttu-id="30124-130">Elija o defina un tipo no primitivo serializable para el recurso.</span><span class="sxs-lookup"><span data-stu-id="30124-130">Choose or define a serializable non-primitive type for the resource.</span></span>  
  
         <span data-ttu-id="30124-131">Un recurso es un objeto.</span><span class="sxs-lookup"><span data-stu-id="30124-131">A resource is an object.</span></span> <span data-ttu-id="30124-132">El tipo CLR del recurso debe ser serializable, porque WCF serializa las notificaciones en varios puntos.</span><span class="sxs-lookup"><span data-stu-id="30124-132">The CLR type of the resource must be serializable, because claims are serialized at various points by WCF.</span></span> <span data-ttu-id="30124-133">Los tipos primitivos ya son serializables.</span><span class="sxs-lookup"><span data-stu-id="30124-133">Primitive types are already serializable.</span></span>  
  
         <span data-ttu-id="30124-134">Cuando se define un nuevo tipo, aplique <xref:System.Runtime.Serialization.DataContractAttribute> a la clase.</span><span class="sxs-lookup"><span data-stu-id="30124-134">When a new type is defined, apply the <xref:System.Runtime.Serialization.DataContractAttribute> to the class.</span></span> <span data-ttu-id="30124-135">Aplique también el atributo <xref:System.Runtime.Serialization.DataMemberAttribute> a todos los miembros del nuevo tipo que necesiten ser serializados como parte de la demanda.</span><span class="sxs-lookup"><span data-stu-id="30124-135">Also apply the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute to the all members of the new type that need to be serialized as part of the claim.</span></span>  
  
         <span data-ttu-id="30124-136">El ejemplo de código siguiente define un tipo de recurso personalizado denominado `MyResourceType`.</span><span class="sxs-lookup"><span data-stu-id="30124-136">The following code example defines a custom resource type named `MyResourceType`.</span></span>  
  
         [!code-csharp[c_CustomClaim#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaim/cs/c_customclaim.cs#2)]
         [!code-vb[c_CustomClaim#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaim/vb/c_customclaim.vb#2)]
  
    3. <span data-ttu-id="30124-137">Elija un derecho definido por WCF o un valor único para un derecho personalizado.</span><span class="sxs-lookup"><span data-stu-id="30124-137">Choose a right that is defined by WCF or a unique value for a custom right.</span></span>  
  
         <span data-ttu-id="30124-138">Un derecho es un identificador de cadena único.</span><span class="sxs-lookup"><span data-stu-id="30124-138">A right is a unique string identifier.</span></span> <span data-ttu-id="30124-139">Los derechos definidos por WCF <xref:System.IdentityModel.Claims.Rights> se definen en la clase.</span><span class="sxs-lookup"><span data-stu-id="30124-139">The rights that are defined by WCF are defined in the <xref:System.IdentityModel.Claims.Rights> class.</span></span>  
  
         <span data-ttu-id="30124-140">Es la responsabilidad del diseñador de la demanda personalizada asegurar que el identificador de cadena que se usa para el derecho sea único.</span><span class="sxs-lookup"><span data-stu-id="30124-140">It is the custom claim designer's responsibility to ensure that the string identifier that is used for the right is unique.</span></span>  
  
         <span data-ttu-id="30124-141">El ejemplo de código siguiente crea una demanda personalizada con un tipo de demanda de `http://example.org/claims/complexcustomclaim`, un tipo de recurso personalizado de `MyResourceType` y con el derecho <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A>.</span><span class="sxs-lookup"><span data-stu-id="30124-141">The following code example creates a custom claim with a claim type of `http://example.org/claims/complexcustomclaim`, a custom resource type of `MyResourceType`, and with the <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A> right.</span></span>  
  
         [!code-csharp[c_CustomClaim#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaim/cs/c_customclaim.cs#5)]
         [!code-vb[c_CustomClaim#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaim/vb/c_customclaim.vb#5)]
  
## <a name="example"></a><span data-ttu-id="30124-142">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="30124-142">Example</span></span>  
 <span data-ttu-id="30124-143">El ejemplo de código siguiente muestra cómo crear una demanda personalizada con un tipo de recurso primitivo y una demanda personalizada con un tipo de recurso no primitivo.</span><span class="sxs-lookup"><span data-stu-id="30124-143">The following code example demonstrates how to create a custom claim with a primitive resource type and a custom claim with a non-primitive resource type.</span></span>  
  
 [!code-csharp[c_CustomClaim#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaim/cs/c_customclaim.cs#0)]
 [!code-vb[c_CustomClaim#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaim/vb/c_customclaim.vb#0)]  
  
## <a name="see-also"></a><span data-ttu-id="30124-144">Consulte también</span><span class="sxs-lookup"><span data-stu-id="30124-144">See also</span></span>

- <xref:System.IdentityModel.Claims.Claim>
- <xref:System.IdentityModel.Claims.Rights>
- <xref:System.IdentityModel.Claims.ClaimTypes>
- <xref:System.Runtime.Serialization.DataContractAttribute>
- <xref:System.Runtime.Serialization.DataMemberAttribute>
- [<span data-ttu-id="30124-145">Administración de notificaciones y autorización con el modelo de identidad</span><span class="sxs-lookup"><span data-stu-id="30124-145">Managing Claims and Authorization with the Identity Model</span></span>](../feature-details/managing-claims-and-authorization-with-the-identity-model.md)
