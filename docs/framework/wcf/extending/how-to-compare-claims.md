---
title: Filtrar para comparar notificaciones
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- claims [WCF], comparing
- claims [WCF]
ms.assetid: 0c4ec84d-53df-408f-8953-9bc437f56c28
ms.openlocfilehash: 932ad347730b35a936e040e116e5aa6af36cd3dc
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59343316"
---
# <a name="how-to-compare-claims"></a><span data-ttu-id="9f16b-102">Filtrar para comparar notificaciones</span><span class="sxs-lookup"><span data-stu-id="9f16b-102">How to: Compare Claims</span></span>
<span data-ttu-id="9f16b-103">La infraestructura del modelo de identidad en Windows Communication Foundation (WCF) se usa para realizar la comprobación de autorización.</span><span class="sxs-lookup"><span data-stu-id="9f16b-103">The Identity Model infrastructure in Windows Communication Foundation (WCF) is used to perform authorization checking.</span></span> <span data-ttu-id="9f16b-104">Como tal, una tarea común es comparar las notificaciones en el contexto de autorización con las notificaciones necesarias para realizar la acción solicitada o tener acceso al recurso solicitado.</span><span class="sxs-lookup"><span data-stu-id="9f16b-104">As such, a common task is to compare claims in the authorization context to the claims required to perform the requested action or access the requested resource.</span></span> <span data-ttu-id="9f16b-105">En este tema se describe cómo comparar las notificaciones, incluidos los tipos de notificación integrados y personalizados.</span><span class="sxs-lookup"><span data-stu-id="9f16b-105">This topic describes how to compare claims, including built-in and custom claim types.</span></span> <span data-ttu-id="9f16b-106">Para obtener más información acerca de la infraestructura del modelo de identidad, vea [Administrar notificaciones y autorización con el modelo de identidad](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md).</span><span class="sxs-lookup"><span data-stu-id="9f16b-106">For more information about the Identity Model infrastructure, see [Managing Claims and Authorization with the Identity Model](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md).</span></span>  
  
 <span data-ttu-id="9f16b-107">La comparación de notificaciones implica la comparación de tres partes de una notificación (tipo, derecho y recurso) con las mismas partes en otra notificación para ver si son iguales.</span><span class="sxs-lookup"><span data-stu-id="9f16b-107">Claim comparison involves comparing the three parts of a claim (type, right, and resource) against the same parts in another claim to see if they are equal.</span></span> <span data-ttu-id="9f16b-108">Vea el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="9f16b-108">See the following example.</span></span>  
  
 [!code-csharp[c_CustomClaimComparison#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaimcomparison/cs/c_customclaimcomparison.cs#9)]
 [!code-vb[c_CustomClaimComparison#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaimcomparison/vb/source.vb#9)]  
  
 <span data-ttu-id="9f16b-109">Ambas notificaciones tienen un tipo de notificación <xref:System.IdentityModel.Claims.ClaimTypes.Name%2A>, un derecho <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A> y un recurso con la cadena "someone".</span><span class="sxs-lookup"><span data-stu-id="9f16b-109">Both claims have a claim type of <xref:System.IdentityModel.Claims.ClaimTypes.Name%2A>, a right of <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A>, and a resource of the string "someone".</span></span> <span data-ttu-id="9f16b-110">Como las tres partes de la notificación son iguales, las notificaciones en sí mismas también lo son.</span><span class="sxs-lookup"><span data-stu-id="9f16b-110">As all three parts of the claim are equal, the claims themselves are equal.</span></span>  
  
 <span data-ttu-id="9f16b-111">Los tipos de notificación integrados se comparan mediante el método <xref:System.IdentityModel.Claims.Claim.Equals%2A>.</span><span class="sxs-lookup"><span data-stu-id="9f16b-111">The built-in claim types are compared using the <xref:System.IdentityModel.Claims.Claim.Equals%2A> method.</span></span> <span data-ttu-id="9f16b-112">Se utiliza el código de la comparación específico de la notificación allí donde sea necesario.</span><span class="sxs-lookup"><span data-stu-id="9f16b-112">Claim-specific comparison code is used where necessary.</span></span> <span data-ttu-id="9f16b-113">Por ejemplo, dadas las siguientes dos notificaciones del nombre principal del usuario (UPN):</span><span class="sxs-lookup"><span data-stu-id="9f16b-113">For example, given the following two user principal name (UPN) claims:</span></span>  
  
 [!code-csharp[c_CustomClaimComparison#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaimcomparison/cs/c_customclaimcomparison.cs#4)]
 [!code-vb[c_CustomClaimComparison#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaimcomparison/vb/source.vb#4)]  
  
 <span data-ttu-id="9f16b-114">el código de la comparación en el <xref:System.IdentityModel.Claims.Claim.Equals%2A> devuelve del método `true`, suponiendo que `example\someone` identifica el mismo usuario de dominio que "someone@example.com".</span><span class="sxs-lookup"><span data-stu-id="9f16b-114">the comparison code in the <xref:System.IdentityModel.Claims.Claim.Equals%2A> method returns `true`, assuming `example\someone` identifies the same domain user as "someone@example.com".</span></span>  
  
 <span data-ttu-id="9f16b-115">Los tipos de notificación personalizados también se pueden comparar con el método <xref:System.IdentityModel.Claims.Claim.Equals%2A>.</span><span class="sxs-lookup"><span data-stu-id="9f16b-115">Custom claim types can also be compared using the <xref:System.IdentityModel.Claims.Claim.Equals%2A> method.</span></span> <span data-ttu-id="9f16b-116">Sin embargo, en los casos en que el tipo devuelto por la propiedad <xref:System.IdentityModel.Claims.Claim.Resource%2A> de la notificación es distinto a un tipo primitivo, <xref:System.IdentityModel.Claims.Claim.Equals%2A> solo devuelve `true` si los valores devueltos por las propiedades `Resource` son iguales de acuerdo con el método <xref:System.IdentityModel.Claims.Claim.Equals%2A>.</span><span class="sxs-lookup"><span data-stu-id="9f16b-116">However, in cases where the type returned by the <xref:System.IdentityModel.Claims.Claim.Resource%2A> property of the claim is something other than a primitive type, the <xref:System.IdentityModel.Claims.Claim.Equals%2A> returns `true` only if the values returned by the `Resource` properties are equal according to the <xref:System.IdentityModel.Claims.Claim.Equals%2A> method.</span></span> <span data-ttu-id="9f16b-117">En los casos en que esto no sea adecuado, el tipo personalizado devuelto por la propiedad `Resource` debería invalidar los métodos <xref:System.IdentityModel.Claims.Claim.Equals%2A> y <xref:System.Object.GetHashCode%2A> para realizar el procesamiento personalizado que sea necesario.</span><span class="sxs-lookup"><span data-stu-id="9f16b-117">In cases where this is not appropriate, the custom type returned by the `Resource` property should override the <xref:System.IdentityModel.Claims.Claim.Equals%2A> and <xref:System.Object.GetHashCode%2A> methods to perform whatever custom processing is necessary.</span></span>  
  
### <a name="comparing-built-in-claims"></a><span data-ttu-id="9f16b-118">Comparación de notificaciones integradas</span><span class="sxs-lookup"><span data-stu-id="9f16b-118">Comparing built-in claims</span></span>  
  
1. <span data-ttu-id="9f16b-119">Dadas dos instancias de la clase <xref:System.IdentityModel.Claims.Claim>, utilice <xref:System.IdentityModel.Claims.Claim.Equals%2A> para realizar la comparación, tal y como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="9f16b-119">Given two instances of the <xref:System.IdentityModel.Claims.Claim> class, use the <xref:System.IdentityModel.Claims.Claim.Equals%2A> to make the comparison, as shown in the following code.</span></span>  
  
     [!code-csharp[c_CustomClaimComparison#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaimcomparison/cs/c_customclaimcomparison.cs#5)]
     [!code-vb[c_CustomClaimComparison#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaimcomparison/vb/source.vb#5)]  
  
### <a name="comparing-custom-claims-with-primitive-resource-types"></a><span data-ttu-id="9f16b-120">Comparación de las notificaciones personalizadas con los tipos de recursos primitivos</span><span class="sxs-lookup"><span data-stu-id="9f16b-120">Comparing custom claims with primitive resource types</span></span>  
  
1. <span data-ttu-id="9f16b-121">En el caso de las notificaciones personalizadas con tipos de recursos primitivos, se puede realizar la comparación para las notificaciones integradas, tal y como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="9f16b-121">For custom claims with primitive resource types, comparison can be performed as for built-in claims, as shown in the following code.</span></span>  
  
     [!code-csharp[c_CustomClaimComparison#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaimcomparison/cs/c_customclaimcomparison.cs#6)]
     [!code-vb[c_CustomClaimComparison#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaimcomparison/vb/source.vb#6)]  
  
2. <span data-ttu-id="9f16b-122">En el caso de las notificaciones con tipos de recursos basados en la estructura o la clase, el tipo de recurso debería invalidar el método <xref:System.IdentityModel.Claims.Claim.Equals%2A>.</span><span class="sxs-lookup"><span data-stu-id="9f16b-122">For custom claims with structure or class based resource types, the resource type should override the <xref:System.IdentityModel.Claims.Claim.Equals%2A> method.</span></span>  
  
3. <span data-ttu-id="9f16b-123">Primero compruebe si el parámetro `obj` es `null` y, en ese caso, devuelva `false`.</span><span class="sxs-lookup"><span data-stu-id="9f16b-123">First check whether the `obj` parameter is `null`, and if so, return `false`.</span></span>  
  
     [!code-csharp[c_CustomClaimComparison#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaimcomparison/cs/c_customclaimcomparison.cs#7)]
     [!code-vb[c_CustomClaimComparison#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaimcomparison/vb/source.vb#7)]  
  
4. <span data-ttu-id="9f16b-124">A continuación, llame a <xref:System.Object.ReferenceEquals%2A> y pase `this` y `obj` como parámetros.</span><span class="sxs-lookup"><span data-stu-id="9f16b-124">Next call <xref:System.Object.ReferenceEquals%2A> and pass `this` and `obj` as parameters.</span></span> <span data-ttu-id="9f16b-125">Si devuelve `true`, devuelva `true`.</span><span class="sxs-lookup"><span data-stu-id="9f16b-125">If it returns `true`, then return `true`.</span></span>  
  
     [!code-csharp[c_CustomClaimComparison#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaimcomparison/cs/c_customclaimcomparison.cs#8)]
     [!code-vb[c_CustomClaimComparison#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaimcomparison/vb/source.vb#8)]  
  
5. <span data-ttu-id="9f16b-126">Luego intente asignar `obj` a una variable local del tipo de clase.</span><span class="sxs-lookup"><span data-stu-id="9f16b-126">Next attempt to assign `obj` to a local variable of the class type.</span></span> <span data-ttu-id="9f16b-127">Si se produce un error, la referencia será `null`.</span><span class="sxs-lookup"><span data-stu-id="9f16b-127">If this fails, the reference is `null`.</span></span> <span data-ttu-id="9f16b-128">En tales casos, devuelva `false`.</span><span class="sxs-lookup"><span data-stu-id="9f16b-128">In such cases, return `false`.</span></span>  
  
6. <span data-ttu-id="9f16b-129">Realice la comparación personalizada necesaria para comparar correctamente la notificación actual con la notificación proporcionada.</span><span class="sxs-lookup"><span data-stu-id="9f16b-129">Perform the custom comparison necessary to correctly compare the current claim to the provided claim.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9f16b-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9f16b-130">Example</span></span>  
 <span data-ttu-id="9f16b-131">El ejemplo siguiente muestra una comparación de notificaciones personalizadas donde el recurso de la notificación es un tipo no primitivo.</span><span class="sxs-lookup"><span data-stu-id="9f16b-131">The following example shows a comparison of custom claims where the claim resource is a non-primitive type.</span></span>  
  
 [!code-csharp[c_CustomClaimComparison#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaimcomparison/cs/c_customclaimcomparison.cs#0)]
 [!code-vb[c_CustomClaimComparison#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaimcomparison/vb/source.vb#0)]  
  
## <a name="see-also"></a><span data-ttu-id="9f16b-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="9f16b-132">See also</span></span>

- [<span data-ttu-id="9f16b-133">Administración de notificaciones y autorización con el modelo de identidad</span><span class="sxs-lookup"><span data-stu-id="9f16b-133">Managing Claims and Authorization with the Identity Model</span></span>](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)
- [<span data-ttu-id="9f16b-134">Filtrar para crear una notificación personalizada</span><span class="sxs-lookup"><span data-stu-id="9f16b-134">How to: Create a Custom Claim</span></span>](../../../../docs/framework/wcf/extending/how-to-create-a-custom-claim.md)
