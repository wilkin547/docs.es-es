---
title: "C&#243;mo crear un servicio que requiere sesiones | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8a7613ef-0df9-47c3-b8dc-47f42cb1fd8b
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# C&#243;mo crear un servicio que requiere sesiones
Las sesiones crean un estado compartido entre dos o más puntos de conexión que habilita características útiles como las devoluciones de llamada, la seguridad de saltos múltiples y asociaciones entre clientes e instancias de servicio. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]las sesiones en [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] aplicaciones, consulte [mediante sesiones](../../../../docs/framework/wcf/using-sessions.md).  
  
### <a name="to-specify-that-a-contract-require-its-binding-to-support-sessions"></a>Especificar que un contrato requiere su enlace para admitir sesiones  
  
1.  Crear un contrato de servicio que contenga al menos una operación. Para obtener un ejemplo de cómo crear un contrato de servicio, consulte [Cómo: definir un contrato de servicio](../../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md).  
  
2.  Modificar el <xref:System.ServiceModel.ServiceContractAttribute?displayProperty=fullName> que declara el contrato estableciendo la <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A?displayProperty=fullName> propiedad como:  
  
    -   <xref:System.ServiceModel.SessionMode?displayProperty=fullName> si este contrato se debe ejecutar dentro de una sesión.  
  
    -   <xref:System.ServiceModel.SessionMode?displayProperty=fullName> si este contrato se puede ejecutar dentro de una sesión.  
  
    -   <xref:System.ServiceModel.SessionMode?displayProperty=fullName> si este contrato no debe ejecutarse dentro de una sesión.  
  
3.  Configure su punto de conexión de servicio para que use un enlace que admita sesiones. En el ejemplo de configuración siguiente se muestra el uso de la <xref:System.ServiceModel.WSDualHttpBinding?displayProperty=fullName>, que admite una WS`-`sesión ReliableMessaging.  
  
     <!-- TODO: review snippet reference [!code[SCA.Session#2](../../../../samples/snippets/common/VS_Snippets_CFX/sca.session/common/hostapplication.exe.config#2)]  -->
     <!-- TODO: review snippet reference [!code-csharp[SCA.Session#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/sca.session/cs/hostapplication.exe.config#2)]  -->
     <!-- TODO: review snippet reference [!code-vb[SCA.Session#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/sca.session/vb/hostapplication.exe.config#2)]  -->  
  
## <a name="example"></a>Ejemplo  
 El ejemplo de código siguiente muestra cómo especificar un requisito de contrato de nivel de sesión y usar un archivo de configuración para admitir ese requisito con el <xref:System.ServiceModel.WSDualHttpBinding?displayProperty=fullName> enlace.  
  
 [!code-csharp[SCA.Session#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/sca.session/cs/services.cs#1)]
 [!code-vb[SCA.Session#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/sca.session/vb/services.vb#1)]  
  
 <!-- TODO: review snippet reference [!code[SCA.Session#2](../../../../samples/snippets/common/VS_Snippets_CFX/sca.session/common/hostapplication.exe.config#2)]  -->
 <!-- TODO: review snippet reference [!code-csharp[SCA.Session#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/sca.session/cs/hostapplication.exe.config#2)]  -->
 <!-- TODO: review snippet reference [!code-vb[SCA.Session#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/sca.session/vb/hostapplication.exe.config#2)]  -->  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.ServiceContractAttribute?displayProperty=fullName>   
 <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A?displayProperty=fullName>   
 <xref:System.ServiceModel.SessionMode?displayProperty=fullName>