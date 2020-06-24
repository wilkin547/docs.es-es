---
title: Procedimiento para crear una notificación personalizada
description: Obtenga información sobre cómo crear una demanda personalizada en WCF. WCF admite una variedad de notificaciones integradas y algunas aplicaciones pueden requerir notificaciones personalizadas.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d619976b-eda3-475e-ac23-c7988a2dceb0
ms.openlocfilehash: 89f2b1359b48b71720db6ff38f27883745cfe612
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85247551"
---
# <a name="how-to-create-a-custom-claim"></a>Procedimiento para crear una notificación personalizada
La infraestructura del modelo de identidad de Windows Communication Foundation (WCF) proporciona un conjunto de tipos y derechos de notificaciones integrados con las funciones auxiliares para crear <xref:System.IdentityModel.Claims.Claim> instancias con esos tipos y derechos. Estas notificaciones integradas están diseñadas para modelar la información que se encuentra en los tipos de credenciales de cliente que WCF admite de forma predeterminada. En muchos casos, las demandas integradas son suficientes; sin embargo, algunas aplicaciones pueden exigir demandas personalizadas. Una demanda está compuesta por el tipo de demanda, el recurso para el que la demanda se aplica y el derecho que se impone sobre ese recurso. En este tema se describe cómo crear una demanda personalizada.  
  
### <a name="to-create-a-custom-claim-that-is-based-on-a-primitive-data-type"></a>Para crear una demanda personalizada que está basada en un tipo de datos primitivo  
  
1. Cree una demanda personalizada pasando el tipo de demanda, valor de recurso y derecho al constructor <xref:System.IdentityModel.Claims.Claim.%23ctor%28System.String%2CSystem.Object%2CSystem.String%29>.  
  
    1. Seleccione un valor único para el tipo de demanda.  
  
         El tipo de demanda es un identificador de cadena único. Es la responsabilidad del diseñador de la demanda personalizada asegurar que el identificador de cadena que se usa para el tipo de demanda sea único. Para obtener una lista de los tipos de notificaciones definidos por WCF, vea la <xref:System.IdentityModel.Claims.ClaimTypes> clase.  
  
    2. Elija el tipo de datos primitivo y el valor para el recurso.  
  
         Un recurso es un objeto. El tipo CLR del recurso puede ser primitivo, como <xref:System.String> o <xref:System.Int32>, así como cualquier tipo serializable. El tipo CLR del recurso debe ser serializable, porque las notificaciones se serializan en varios puntos por WCF. Los tipos primitivos son serializables.  
  
    3. Elija un derecho definido por WCF o un valor único para un derecho personalizado.  
  
         Un derecho es un identificador de cadena único. Los derechos definidos por WCF se definen en la <xref:System.IdentityModel.Claims.Rights> clase.  
  
         Es la responsabilidad del diseñador de la demanda personalizada asegurar que el identificador de cadena que se usa para el derecho sea único.  
  
         El ejemplo de código siguiente crea una demanda personalizada con un tipo de demanda de `http://example.org/claims/simplecustomclaim`, para un recurso denominado `Driver's License` y con el derecho <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A>.  
  
     [!code-csharp[c_CustomClaim#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaim/cs/c_customclaim.cs#4)]
     [!code-vb[c_CustomClaim#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaim/vb/c_customclaim.vb#4)]  
  
### <a name="to-create-a-custom-claim-that-is-based-on-a-non-primitive-data-type"></a>Para crear una demanda personalizada basada en un tipo de datos no primitivo  
  
1. Cree una demanda personalizada pasando el tipo de demanda, valor de recurso y derecho al constructor <xref:System.IdentityModel.Claims.Claim.%23ctor%28System.String%2CSystem.Object%2CSystem.String%29>.  
  
    1. Seleccione un valor único para el tipo de demanda.  
  
         El tipo de demanda es un identificador de cadena único. Es la responsabilidad del diseñador de la demanda personalizada asegurar que el identificador de cadena que se usa para el tipo de demanda sea único. Para obtener una lista de los tipos de notificaciones definidos por WCF, vea la <xref:System.IdentityModel.Claims.ClaimTypes> clase.  
  
    2. Elija o defina un tipo no primitivo serializable para el recurso.  
  
         Un recurso es un objeto. El tipo CLR del recurso debe ser serializable, porque las notificaciones se serializan en varios puntos por WCF. Los tipos primitivos ya son serializables.  
  
         Cuando se define un nuevo tipo, aplique <xref:System.Runtime.Serialization.DataContractAttribute> a la clase. Aplique también el atributo <xref:System.Runtime.Serialization.DataMemberAttribute> a todos los miembros del nuevo tipo que necesiten ser serializados como parte de la demanda.  
  
         El ejemplo de código siguiente define un tipo de recurso personalizado denominado `MyResourceType`.  
  
         [!code-csharp[c_CustomClaim#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaim/cs/c_customclaim.cs#2)]
         [!code-vb[c_CustomClaim#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaim/vb/c_customclaim.vb#2)]
  
    3. Elija un derecho definido por WCF o un valor único para un derecho personalizado.  
  
         Un derecho es un identificador de cadena único. Los derechos definidos por WCF se definen en la <xref:System.IdentityModel.Claims.Rights> clase.  
  
         Es la responsabilidad del diseñador de la demanda personalizada asegurar que el identificador de cadena que se usa para el derecho sea único.  
  
         El ejemplo de código siguiente crea una demanda personalizada con un tipo de demanda de `http://example.org/claims/complexcustomclaim`, un tipo de recurso personalizado de `MyResourceType` y con el derecho <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A>.  
  
         [!code-csharp[c_CustomClaim#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaim/cs/c_customclaim.cs#5)]
         [!code-vb[c_CustomClaim#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaim/vb/c_customclaim.vb#5)]
  
## <a name="example"></a>Ejemplo  
 El ejemplo de código siguiente muestra cómo crear una demanda personalizada con un tipo de recurso primitivo y una demanda personalizada con un tipo de recurso no primitivo.  
  
 [!code-csharp[c_CustomClaim#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaim/cs/c_customclaim.cs#0)]
 [!code-vb[c_CustomClaim#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaim/vb/c_customclaim.vb#0)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.IdentityModel.Claims.Claim>
- <xref:System.IdentityModel.Claims.Rights>
- <xref:System.IdentityModel.Claims.ClaimTypes>
- <xref:System.Runtime.Serialization.DataContractAttribute>
- <xref:System.Runtime.Serialization.DataMemberAttribute>
- [Administración de notificaciones y autorización con el modelo de identidad](../feature-details/managing-claims-and-authorization-with-the-identity-model.md)
