---
description: 'Más información acerca de cómo: comparar notificaciones'
title: Procedimiento para comparar notificaciones
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- claims [WCF], comparing
- claims [WCF]
ms.assetid: 0c4ec84d-53df-408f-8953-9bc437f56c28
ms.openlocfilehash: c2088ad3992852bdc12e7bcd71d5f3598a237b45
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99653854"
---
# <a name="how-to-compare-claims"></a><span data-ttu-id="55344-103">Procedimiento para comparar notificaciones</span><span class="sxs-lookup"><span data-stu-id="55344-103">How to: Compare Claims</span></span>

<span data-ttu-id="55344-104">La infraestructura del modelo de identidad en Windows Communication Foundation (WCF) se usa para realizar la comprobación de la autorización.</span><span class="sxs-lookup"><span data-stu-id="55344-104">The Identity Model infrastructure in Windows Communication Foundation (WCF) is used to perform authorization checking.</span></span> <span data-ttu-id="55344-105">Como tal, una tarea común es comparar las notificaciones en el contexto de autorización con las notificaciones necesarias para realizar la acción solicitada o tener acceso al recurso solicitado.</span><span class="sxs-lookup"><span data-stu-id="55344-105">As such, a common task is to compare claims in the authorization context to the claims required to perform the requested action or access the requested resource.</span></span> <span data-ttu-id="55344-106">En este tema se describe cómo comparar las notificaciones, incluidos los tipos de notificación integrados y personalizados.</span><span class="sxs-lookup"><span data-stu-id="55344-106">This topic describes how to compare claims, including built-in and custom claim types.</span></span> <span data-ttu-id="55344-107">Para obtener más información sobre la infraestructura del modelo de identidad, consulte [Administración de notificaciones y autorización con el modelo de identidad](../feature-details/managing-claims-and-authorization-with-the-identity-model.md).</span><span class="sxs-lookup"><span data-stu-id="55344-107">For more information about the Identity Model infrastructure, see [Managing Claims and Authorization with the Identity Model](../feature-details/managing-claims-and-authorization-with-the-identity-model.md).</span></span>

<span data-ttu-id="55344-108">La comparación de notificaciones implica la comparación de tres partes de una notificación (tipo, derecho y recurso) con las mismas partes en otra notificación para ver si son iguales.</span><span class="sxs-lookup"><span data-stu-id="55344-108">Claim comparison involves comparing the three parts of a claim (type, right, and resource) against the same parts in another claim to see if they are equal.</span></span> <span data-ttu-id="55344-109">Consulte el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="55344-109">See the following example.</span></span>

[!code-csharp[c_CustomClaimComparison#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaimcomparison/cs/c_customclaimcomparison.cs#9)]
[!code-vb[c_CustomClaimComparison#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaimcomparison/vb/source.vb#9)]

<span data-ttu-id="55344-110">Ambas notificaciones tienen un tipo de notificación <xref:System.IdentityModel.Claims.ClaimTypes.Name%2A>, un derecho <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A> y un recurso con la cadena "someone".</span><span class="sxs-lookup"><span data-stu-id="55344-110">Both claims have a claim type of <xref:System.IdentityModel.Claims.ClaimTypes.Name%2A>, a right of <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A>, and a resource of the string "someone".</span></span> <span data-ttu-id="55344-111">Como las tres partes de la notificación son iguales, las notificaciones en sí mismas también lo son.</span><span class="sxs-lookup"><span data-stu-id="55344-111">As all three parts of the claim are equal, the claims themselves are equal.</span></span>

<span data-ttu-id="55344-112">Los tipos de notificación integrados se comparan mediante el método <xref:System.IdentityModel.Claims.Claim.Equals%2A>.</span><span class="sxs-lookup"><span data-stu-id="55344-112">The built-in claim types are compared using the <xref:System.IdentityModel.Claims.Claim.Equals%2A> method.</span></span> <span data-ttu-id="55344-113">Se utiliza el código de la comparación específico de la notificación allí donde sea necesario.</span><span class="sxs-lookup"><span data-stu-id="55344-113">Claim-specific comparison code is used where necessary.</span></span> <span data-ttu-id="55344-114">Por ejemplo, dadas las siguientes dos notificaciones del nombre principal del usuario (UPN):</span><span class="sxs-lookup"><span data-stu-id="55344-114">For example, given the following two user principal name (UPN) claims:</span></span>

[!code-csharp[c_CustomClaimComparison#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaimcomparison/cs/c_customclaimcomparison.cs#4)]
[!code-vb[c_CustomClaimComparison#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaimcomparison/vb/source.vb#4)]

<span data-ttu-id="55344-115">el código de comparación en el <xref:System.IdentityModel.Claims.Claim.Equals%2A> método devuelve `true` , suponiendo `example\someone` que identifica el mismo usuario de dominio que " someone@example.com ".</span><span class="sxs-lookup"><span data-stu-id="55344-115">the comparison code in the <xref:System.IdentityModel.Claims.Claim.Equals%2A> method returns `true`, assuming `example\someone` identifies the same domain user as "someone@example.com".</span></span>

<span data-ttu-id="55344-116">Los tipos de notificación personalizados también se pueden comparar con el método <xref:System.IdentityModel.Claims.Claim.Equals%2A>.</span><span class="sxs-lookup"><span data-stu-id="55344-116">Custom claim types can also be compared using the <xref:System.IdentityModel.Claims.Claim.Equals%2A> method.</span></span> <span data-ttu-id="55344-117">Sin embargo, en los casos en que el tipo devuelto por la propiedad <xref:System.IdentityModel.Claims.Claim.Resource%2A> de la notificación es distinto a un tipo primitivo, <xref:System.IdentityModel.Claims.Claim.Equals%2A> solo devuelve `true` si los valores devueltos por las propiedades `Resource` son iguales de acuerdo con el método <xref:System.IdentityModel.Claims.Claim.Equals%2A>.</span><span class="sxs-lookup"><span data-stu-id="55344-117">However, in cases where the type returned by the <xref:System.IdentityModel.Claims.Claim.Resource%2A> property of the claim is something other than a primitive type, the <xref:System.IdentityModel.Claims.Claim.Equals%2A> returns `true` only if the values returned by the `Resource` properties are equal according to the <xref:System.IdentityModel.Claims.Claim.Equals%2A> method.</span></span> <span data-ttu-id="55344-118">En los casos en que esto no sea adecuado, el tipo personalizado devuelto por la propiedad `Resource` debería invalidar los métodos <xref:System.IdentityModel.Claims.Claim.Equals%2A> y <xref:System.Object.GetHashCode%2A> para realizar el procesamiento personalizado que sea necesario.</span><span class="sxs-lookup"><span data-stu-id="55344-118">In cases where this is not appropriate, the custom type returned by the `Resource` property should override the <xref:System.IdentityModel.Claims.Claim.Equals%2A> and <xref:System.Object.GetHashCode%2A> methods to perform whatever custom processing is necessary.</span></span>

## <a name="comparing-built-in-claims"></a><span data-ttu-id="55344-119">Comparación de notificaciones integradas</span><span class="sxs-lookup"><span data-stu-id="55344-119">Comparing built-in claims</span></span>

1. <span data-ttu-id="55344-120">Dadas dos instancias de la clase <xref:System.IdentityModel.Claims.Claim>, utilice <xref:System.IdentityModel.Claims.Claim.Equals%2A> para realizar la comparación, tal y como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="55344-120">Given two instances of the <xref:System.IdentityModel.Claims.Claim> class, use the <xref:System.IdentityModel.Claims.Claim.Equals%2A> to make the comparison, as shown in the following code.</span></span>

     [!code-csharp[c_CustomClaimComparison#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaimcomparison/cs/c_customclaimcomparison.cs#5)]
     [!code-vb[c_CustomClaimComparison#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaimcomparison/vb/source.vb#5)]

### <a name="comparing-custom-claims-with-primitive-resource-types"></a><span data-ttu-id="55344-121">Comparación de las notificaciones personalizadas con los tipos de recursos primitivos</span><span class="sxs-lookup"><span data-stu-id="55344-121">Comparing custom claims with primitive resource types</span></span>

1. <span data-ttu-id="55344-122">En el caso de las notificaciones personalizadas con tipos de recursos primitivos, se puede realizar la comparación para las notificaciones integradas, tal y como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="55344-122">For custom claims with primitive resource types, comparison can be performed as for built-in claims, as shown in the following code.</span></span>

     [!code-csharp[c_CustomClaimComparison#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaimcomparison/cs/c_customclaimcomparison.cs#6)]
     [!code-vb[c_CustomClaimComparison#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaimcomparison/vb/source.vb#6)]

2. <span data-ttu-id="55344-123">En el caso de las notificaciones con tipos de recursos basados en la estructura o la clase, el tipo de recurso debería invalidar el método <xref:System.IdentityModel.Claims.Claim.Equals%2A>.</span><span class="sxs-lookup"><span data-stu-id="55344-123">For custom claims with structure or class based resource types, the resource type should override the <xref:System.IdentityModel.Claims.Claim.Equals%2A> method.</span></span>

3. <span data-ttu-id="55344-124">Primero compruebe si el parámetro `obj` es `null` y, en ese caso, devuelva `false`.</span><span class="sxs-lookup"><span data-stu-id="55344-124">First check whether the `obj` parameter is `null`, and if so, return `false`.</span></span>

     [!code-csharp[c_CustomClaimComparison#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaimcomparison/cs/c_customclaimcomparison.cs#7)]
     [!code-vb[c_CustomClaimComparison#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaimcomparison/vb/source.vb#7)]

4. <span data-ttu-id="55344-125">A continuación, llame a <xref:System.Object.ReferenceEquals%2A> y pase `this` y `obj` como parámetros.</span><span class="sxs-lookup"><span data-stu-id="55344-125">Next call <xref:System.Object.ReferenceEquals%2A> and pass `this` and `obj` as parameters.</span></span> <span data-ttu-id="55344-126">Si devuelve `true`, devuelva `true`.</span><span class="sxs-lookup"><span data-stu-id="55344-126">If it returns `true`, then return `true`.</span></span>

     [!code-csharp[c_CustomClaimComparison#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaimcomparison/cs/c_customclaimcomparison.cs#8)]
     [!code-vb[c_CustomClaimComparison#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaimcomparison/vb/source.vb#8)]

5. <span data-ttu-id="55344-127">Luego intente asignar `obj` a una variable local del tipo de clase.</span><span class="sxs-lookup"><span data-stu-id="55344-127">Next attempt to assign `obj` to a local variable of the class type.</span></span> <span data-ttu-id="55344-128">Si se produce un error, la referencia será `null`.</span><span class="sxs-lookup"><span data-stu-id="55344-128">If this fails, the reference is `null`.</span></span> <span data-ttu-id="55344-129">En tales casos, devuelva `false`.</span><span class="sxs-lookup"><span data-stu-id="55344-129">In such cases, return `false`.</span></span>

6. <span data-ttu-id="55344-130">Realice la comparación personalizada necesaria para comparar correctamente la notificación actual con la notificación proporcionada.</span><span class="sxs-lookup"><span data-stu-id="55344-130">Perform the custom comparison necessary to correctly compare the current claim to the provided claim.</span></span>

## <a name="example"></a><span data-ttu-id="55344-131">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="55344-131">Example</span></span>

<span data-ttu-id="55344-132">El ejemplo siguiente muestra una comparación de notificaciones personalizadas donde el recurso de la notificación es un tipo no primitivo.</span><span class="sxs-lookup"><span data-stu-id="55344-132">The following example shows a comparison of custom claims where the claim resource is a non-primitive type.</span></span>

[!code-csharp[c_CustomClaimComparison#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaimcomparison/cs/c_customclaimcomparison.cs#0)]
[!code-vb[c_CustomClaimComparison#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaimcomparison/vb/source.vb#0)]

## <a name="see-also"></a><span data-ttu-id="55344-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="55344-133">See also</span></span>

- [<span data-ttu-id="55344-134">Administración de notificaciones y autorización con el modelo de identidad</span><span class="sxs-lookup"><span data-stu-id="55344-134">Managing Claims and Authorization with the Identity Model</span></span>](../feature-details/managing-claims-and-authorization-with-the-identity-model.md)
- [<span data-ttu-id="55344-135">Procedimiento para crear una notificación personalizada</span><span class="sxs-lookup"><span data-stu-id="55344-135">How to: Create a Custom Claim</span></span>](how-to-create-a-custom-claim.md)
