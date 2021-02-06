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
# <a name="how-to-compare-claims"></a>Procedimiento para comparar notificaciones

La infraestructura del modelo de identidad en Windows Communication Foundation (WCF) se usa para realizar la comprobación de la autorización. Como tal, una tarea común es comparar las notificaciones en el contexto de autorización con las notificaciones necesarias para realizar la acción solicitada o tener acceso al recurso solicitado. En este tema se describe cómo comparar las notificaciones, incluidos los tipos de notificación integrados y personalizados. Para obtener más información sobre la infraestructura del modelo de identidad, consulte [Administración de notificaciones y autorización con el modelo de identidad](../feature-details/managing-claims-and-authorization-with-the-identity-model.md).

La comparación de notificaciones implica la comparación de tres partes de una notificación (tipo, derecho y recurso) con las mismas partes en otra notificación para ver si son iguales. Consulte el ejemplo siguiente.

[!code-csharp[c_CustomClaimComparison#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaimcomparison/cs/c_customclaimcomparison.cs#9)]
[!code-vb[c_CustomClaimComparison#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaimcomparison/vb/source.vb#9)]

Ambas notificaciones tienen un tipo de notificación <xref:System.IdentityModel.Claims.ClaimTypes.Name%2A>, un derecho <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A> y un recurso con la cadena "someone". Como las tres partes de la notificación son iguales, las notificaciones en sí mismas también lo son.

Los tipos de notificación integrados se comparan mediante el método <xref:System.IdentityModel.Claims.Claim.Equals%2A>. Se utiliza el código de la comparación específico de la notificación allí donde sea necesario. Por ejemplo, dadas las siguientes dos notificaciones del nombre principal del usuario (UPN):

[!code-csharp[c_CustomClaimComparison#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaimcomparison/cs/c_customclaimcomparison.cs#4)]
[!code-vb[c_CustomClaimComparison#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaimcomparison/vb/source.vb#4)]

el código de comparación en el <xref:System.IdentityModel.Claims.Claim.Equals%2A> método devuelve `true` , suponiendo `example\someone` que identifica el mismo usuario de dominio que " someone@example.com ".

Los tipos de notificación personalizados también se pueden comparar con el método <xref:System.IdentityModel.Claims.Claim.Equals%2A>. Sin embargo, en los casos en que el tipo devuelto por la propiedad <xref:System.IdentityModel.Claims.Claim.Resource%2A> de la notificación es distinto a un tipo primitivo, <xref:System.IdentityModel.Claims.Claim.Equals%2A> solo devuelve `true` si los valores devueltos por las propiedades `Resource` son iguales de acuerdo con el método <xref:System.IdentityModel.Claims.Claim.Equals%2A>. En los casos en que esto no sea adecuado, el tipo personalizado devuelto por la propiedad `Resource` debería invalidar los métodos <xref:System.IdentityModel.Claims.Claim.Equals%2A> y <xref:System.Object.GetHashCode%2A> para realizar el procesamiento personalizado que sea necesario.

## <a name="comparing-built-in-claims"></a>Comparación de notificaciones integradas

1. Dadas dos instancias de la clase <xref:System.IdentityModel.Claims.Claim>, utilice <xref:System.IdentityModel.Claims.Claim.Equals%2A> para realizar la comparación, tal y como se muestra en el código siguiente.

     [!code-csharp[c_CustomClaimComparison#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaimcomparison/cs/c_customclaimcomparison.cs#5)]
     [!code-vb[c_CustomClaimComparison#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaimcomparison/vb/source.vb#5)]

### <a name="comparing-custom-claims-with-primitive-resource-types"></a>Comparación de las notificaciones personalizadas con los tipos de recursos primitivos

1. En el caso de las notificaciones personalizadas con tipos de recursos primitivos, se puede realizar la comparación para las notificaciones integradas, tal y como se muestra en el código siguiente.

     [!code-csharp[c_CustomClaimComparison#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaimcomparison/cs/c_customclaimcomparison.cs#6)]
     [!code-vb[c_CustomClaimComparison#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaimcomparison/vb/source.vb#6)]

2. En el caso de las notificaciones con tipos de recursos basados en la estructura o la clase, el tipo de recurso debería invalidar el método <xref:System.IdentityModel.Claims.Claim.Equals%2A>.

3. Primero compruebe si el parámetro `obj` es `null` y, en ese caso, devuelva `false`.

     [!code-csharp[c_CustomClaimComparison#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaimcomparison/cs/c_customclaimcomparison.cs#7)]
     [!code-vb[c_CustomClaimComparison#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaimcomparison/vb/source.vb#7)]

4. A continuación, llame a <xref:System.Object.ReferenceEquals%2A> y pase `this` y `obj` como parámetros. Si devuelve `true`, devuelva `true`.

     [!code-csharp[c_CustomClaimComparison#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaimcomparison/cs/c_customclaimcomparison.cs#8)]
     [!code-vb[c_CustomClaimComparison#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaimcomparison/vb/source.vb#8)]

5. Luego intente asignar `obj` a una variable local del tipo de clase. Si se produce un error, la referencia será `null`. En tales casos, devuelva `false`.

6. Realice la comparación personalizada necesaria para comparar correctamente la notificación actual con la notificación proporcionada.

## <a name="example"></a>Ejemplo

El ejemplo siguiente muestra una comparación de notificaciones personalizadas donde el recurso de la notificación es un tipo no primitivo.

[!code-csharp[c_CustomClaimComparison#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaimcomparison/cs/c_customclaimcomparison.cs#0)]
[!code-vb[c_CustomClaimComparison#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaimcomparison/vb/source.vb#0)]

## <a name="see-also"></a>Vea también

- [Administración de notificaciones y autorización con el modelo de identidad](../feature-details/managing-claims-and-authorization-with-the-identity-model.md)
- [Procedimiento para crear una notificación personalizada](how-to-create-a-custom-claim.md)
