---
title: "C&#243;mo: Crear un enlace personalizado mediante SecurityBindingElement | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "seguridad [WCF], creación de enlaces personalizados"
ms.assetid: 203a9f9e-3a73-427c-87aa-721c56265b29
caps.latest.revision: 19
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 19
---
# C&#243;mo: Crear un enlace personalizado mediante SecurityBindingElement
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] incluye varios enlaces proporcionados por el sistema que se pueden configurar pero que no proporcionan completa flexibilidad cuando se configuran todas las opciones de seguridad que [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] admite. Este tema muestra cómo crear un enlace personalizado directamente a partir de elementos de enlace individuales y resalta algunos de los ajustes de seguridad que pueden especificarse al crear este tipo de enlaces. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]creación de enlaces personalizados, vea [extender enlaces](../../../../docs/framework/wcf/extending/extending-bindings.md).  
  
> [!WARNING]
>  <xref:System.ServiceModel.Channels.SecurityBindingElement> no es compatible con la <xref:System.ServiceModel.Channels.IDuplexSessionChannel> forma, que es el uso de forma de canal predeterminada mediante TCP de canal de transporte cuando <xref:System.ServiceModel.TransferMode> está establecido en <xref:System.ServiceModel.TransferMode.Buffered>. Debe establecer <xref:System.ServiceModel.TransferMode> a <xref:System.ServiceModel.TransferMode.Streamed> para poder utilizar <xref:System.ServiceModel.Channels.SecurityBindingElement> en este escenario.  
  
## <a name="creating-a-custom-binding"></a>Creación de un enlace personalizado  
 En [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] todos los enlaces se componen de *elementos de enlace*. Cada elemento de enlace se deriva de la <xref:System.ServiceModel.Channels.BindingElement> clase. En el caso de los enlaces estándar proporcionados por el sistema, los elementos de enlace se crean y se configuran automáticamente, pero se pueden personalizar algunos de los valores de las propiedades.  
  
 En cambio, para crear un enlace personalizado, elementos de enlace se crean y configuran y un <xref:System.ServiceModel.Channels.CustomBinding> creada a partir de los elementos de enlace.  
  
 Para ello, se agregan los elementos de enlace individuales a una colección representada por una instancia de la <xref:System.ServiceModel.Channels.BindingElementCollection> de clase y, a continuación, establezca el `Elements` propiedad de la `CustomBinding` igual a ese objeto. Debe agregar los elementos de enlace en el orden siguiente: flujo de transacciones, sesión confiable, seguridad, dúplex compuesto, unidireccional, seguridad de secuencia, codificación de mensajes y transporte. Tenga en cuenta que no todos los elementos de enlace enumerados se necesitan en cada enlace.  
  
## <a name="securitybindingelement"></a>SecurityBindingElement  
 Tres elementos de enlace relacionadas con la seguridad de nivel de mensaje, que derivan de la <xref:System.ServiceModel.Channels.SecurityBindingElement> clase. Los tres elementos son <xref:System.ServiceModel.Channels.TransportSecurityBindingElement>, <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>, y <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>. El <xref:System.ServiceModel.Channels.TransportSecurityBindingElement> se utiliza para proporcionar seguridad de modo mixto. Se utilizan los otros dos elementos cuando la capa del mensaje proporciona seguridad.  
  
 Se utilizan clases adicionales cuando se proporciona seguridad de nivel de transporte:  
  
-   <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>  
  
-   <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>  
  
-   <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>  
  
## <a name="required-binding-elements"></a>Elementos de enlace necesarios  
 Hay un gran número de posibles elementos de enlace que se pueden combinar en un enlace. No todas estas combinaciones son válidas. En esta sección se describen los elementos necesarios que se deben encontrar en un enlace de seguridad.  
  
 La validez de los enlaces de seguridad depende de muchos factores, como los siguientes:  
  
-   Modo de seguridad.  
  
-   Protocolo de transporte.  
  
-   El patrón de intercambio de mensajes (MEP) especificado en el contrato.  
  
 En la tabla siguiente se muestran las configuraciones de pila de los elementos de enlace válidos para cada combinación de los factores mencionados. Tenga en cuenta que éstos son los requisitos mínimos. Puede agregar otros elementos de enlace al enlace, como elementos de enlace de codificación de mensajes y elementos de enlace de transacción.  
  
|Modo de seguridad|Transporte|Patrón de intercambio de mensajes de contrato|Patrón de intercambio de mensajes de contrato|Patrón de intercambio de mensajes de contrato|  
|-------------------|---------------|---------------------------------------|---------------------------------------|---------------------------------------|  
|||`Datagram`|`Request Reply`|`Duplex`|  
|Transporte|Https||||  
|||OneWayBindingElement|||  
|||HttpsTransportBindingElement|HttpsTransportBindingElement||  
||TCP||||  
|||OneWayBindingElement|||  
|||SSL o StreamSecurityBindingElement de Windows|SSL o StreamSecurityBindingElement de Windows|SSL o StreamSecurityBindingElement de Windows|  
|||TcpTransportBindingElement|TcpTransportBindingElement|TcpTransportBindingElement|  
|Mensaje|Http|SymmetricSecurityBindingElement|SymmetricSecurityBindingElement|SymmetricSecurityBindingElement (modo de autenticación = SecureConversation)|  
|||||CompositeDuplexBindingElement|  
|||OneWayBindingElement||OneWayBindingElement|  
|||HttpTransportBindingElement|HttpTransportBindingElement|HttpTransportBindingElement|  
||Tcp|SecurityBindingElement|SecurityBindingElement|SymmetricSecurityBindingElement (modo de autenticación = SecureConversation)|  
|||TcpTransportBindingElement|TcpTransportBindingElement|TcpTransportBindingElement|  
|Mixto (transporte con credenciales de mensaje)|Https|TransportSecurityBindingElement|TransportSecurityBindingElement||  
|||OneWayBindingElement|||  
|||HttpsTransportBindingElement|HttpsTransportBindingElement||  
||TCP|TransportSecurityBindingElement|SymmetricSecurityBindingElement (modo de autenticación = SecureConversation)|SymmetricSecurityBindingElement (modo de autenticación = SecureConversation)|  
|||OneWayBindingElement|||  
|||SSL o StreamSecurityBindingElement de Windows|SSL o StreamSecurityBindingElement de Windows|SSL o StreamSecurityBindingElement de Windows|  
|||TcpTransportBindingElement|TcpTransportBindingElement|TcpTransportBindingElement|  
  
 Observe que hay muchos valores de configuración que se pueden definir en SecurityBindingElements. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Modos de autenticación de SecurityBindingElement](../../../../docs/framework/wcf/feature-details/securitybindingelement-authentication-modes.md).  
  
 [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Conversaciones y sesiones seguras](../../../../docs/framework/wcf/feature-details/secure-conversations-and-secure-sessions.md).  
  
## <a name="procedures"></a>Procedimientos  
  
#### <a name="to-create-a-custom-binding-that-uses-a-symmetricsecuritybindingelement"></a>Para crear un enlace personalizado que utilice un SymmetricSecurityBindingElement  
  
1.  Cree una instancia de la <xref:System.ServiceModel.Channels.BindingElementCollection> clase con el nombre `outputBec`.  
  
2.  Llame al método estático `M:System.ServiceModel.Channels.SecurityBindingElement.CreateSspiNegotiationBindingElement(true)`, que devuelve una instancia de la <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> clase.  
  
3.  Agregue el <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> a la colección (`outputBec`) llamando a la `Add` método de la <xref:System.Collections.ObjectModel.Collection%601> de <xref:System.ServiceModel.Channels.BindingElement> clase.  
  
4.  Cree una instancia de la <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> clase y agregarla a la colección (`outputBec`). Esto especifica la codificación utilizada por el enlace.  
  
5.  Crear un <xref:System.ServiceModel.Channels.HttpTransportBindingElement> y agréguelo a la colección (`outputBec`). Esto especifica que el enlace utiliza el transporte HTTP.  
  
6.  Crear un nuevo enlace personalizado creando una instancia de la <xref:System.ServiceModel.Channels.CustomBinding> (clase) y pasando la colección `outputBec` al constructor.  
  
7.  El enlace personalizado resultante comparte muchas de las mismas características que el estándar <xref:System.ServiceModel.WSHttpBinding>. Especifica seguridad del nivel de mensaje y credenciales de Windows pero deshabilita las sesiones seguras, requiere que la credencial del servicio se especifique fuera de banda, y no cifra las firmas. Se puede controlar la última sólo estableciendo la <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement.MessageProtectionOrder%2A> propiedad tal como se muestra en el paso 4. Los otros dos se pueden controlar usando los valores del enlace estándar.  
  
## <a name="example"></a>Ejemplo  
  
### <a name="description"></a>Descripción  
 En el ejemplo siguiente se proporciona una función completa para crear un enlace personalizado que utiliza un <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>.  
  
### <a name="code"></a>Código  
 [!code-csharp[c_CustomBinding#20](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#20)]
 [!code-vb[c_CustomBinding#20](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_custombinding/vb/source.vb#20)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.Channels.SecurityBindingElement>   
 <xref:System.ServiceModel.Channels.TransportSecurityBindingElement>   
 <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>   
 <xref:System.ServiceModel.Channels.CustomBinding>   
 [Extensión de enlaces](../../../../docs/framework/wcf/extending/extending-bindings.md)   
 [Enlaces proporcionados por el sistema](../../../../docs/framework/wcf/system-provided-bindings.md)