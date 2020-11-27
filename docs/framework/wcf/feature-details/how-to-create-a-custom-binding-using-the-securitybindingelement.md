---
title: Procedimiento para crear un enlace personalizado mediante SecurityBindingElement
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security [WCF], creating custom bindings
ms.assetid: 203a9f9e-3a73-427c-87aa-721c56265b29
ms.openlocfilehash: 9aaaf6a10e0c51db35720d72512c1a91cfbb9720
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96256747"
---
# <a name="how-to-create-a-custom-binding-using-the-securitybindingelement"></a>Procedimiento para crear un enlace personalizado mediante SecurityBindingElement

Windows Communication Foundation (WCF) incluye varios enlaces proporcionados por el sistema que se pueden configurar pero que no proporcionan flexibilidad completa al configurar todas las opciones de seguridad que admite WCF. Este tema muestra cómo crear un enlace personalizado directamente a partir de elementos de enlace individuales y resalta algunos de los ajustes de seguridad que pueden especificarse al crear este tipo de enlaces. Para obtener más información sobre la creación de enlaces personalizados, vea [extender enlaces](../extending/extending-bindings.md).  
  
> [!WARNING]
> <xref:System.ServiceModel.Channels.SecurityBindingElement> no admite la forma de canal de <xref:System.ServiceModel.Channels.IDuplexSessionChannel>, que es el uso predeterminado de la forma de canal por el transporte TCP cuando <xref:System.ServiceModel.TransferMode> se establece en <xref:System.ServiceModel.TransferMode.Buffered>. Debe establecer <xref:System.ServiceModel.TransferMode> en <xref:System.ServiceModel.TransferMode.Streamed> para usar <xref:System.ServiceModel.Channels.SecurityBindingElement> en este escenario.  
  
## <a name="creating-a-custom-binding"></a>Creación de un enlace personalizado  

 En WCF, todos los enlaces se componen de *elementos de enlace*. Cada elemento de enlace deriva de la clase <xref:System.ServiceModel.Channels.BindingElement>. En el caso de los enlaces estándar proporcionados por el sistema, los elementos de enlace se crean y se configuran automáticamente, pero se pueden personalizar algunos de los valores de las propiedades.  
  
 Por el contrario, para crear un enlace personalizado, se crean y configuran los elementos de enlace y se crea un objeto <xref:System.ServiceModel.Channels.CustomBinding> a partir de los elementos de enlace.  
  
 Para ello, se agregan los elementos de enlace individuales a una colección representada por una instancia de la clase <xref:System.ServiceModel.Channels.BindingElementCollection> y, a continuación, se establece la propiedad `Elements` de `CustomBinding` en ese objeto. Debe agregar los elementos de enlace en el orden siguiente: flujo de transacciones, sesión confiable, seguridad, dúplex compuesto, unidireccional, seguridad de secuencia, codificación de mensajes y transporte. Tenga en cuenta que no todos los elementos de enlace enumerados se necesitan en cada enlace.  
  
## <a name="securitybindingelement"></a>SecurityBindingElement  

 Tres elementos de enlace guardan relación con la seguridad, y todos se derivan de la clase <xref:System.ServiceModel.Channels.SecurityBindingElement>. Los tres elementos son <xref:System.ServiceModel.Channels.TransportSecurityBindingElement>, <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> y <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>. <xref:System.ServiceModel.Channels.TransportSecurityBindingElement> se utiliza para proporcionar seguridad de modo mixto. Se utilizan los otros dos elementos cuando la capa del mensaje proporciona seguridad.  
  
 Se utilizan clases adicionales cuando se proporciona seguridad de nivel de transporte:  
  
- <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>  
  
- <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>  
  
- <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>  
  
## <a name="required-binding-elements"></a>Elementos de enlace necesarios  

 Hay un gran número de posibles elementos de enlace que se pueden combinar en un enlace. No todas estas combinaciones son válidas. En esta sección se describen los elementos necesarios que se deben encontrar en un enlace de seguridad.  
  
 La validez de los enlaces de seguridad depende de muchos factores, como los siguientes:  
  
- Modo de seguridad.  
  
- Protocolo de transporte.  
  
- El patrón de intercambio de mensajes (MEP) especificado en el contrato.  
  
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
|Message|Http|SymmetricSecurityBindingElement|SymmetricSecurityBindingElement|SymmetricSecurityBindingElement (modo de autenticación = SecureConversation)|  
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
  
 Observe que hay muchos valores de configuración que se pueden definir en SecurityBindingElements. Para obtener más información, vea [modos de autenticación de SecurityBindingElement](securitybindingelement-authentication-modes.md).  
  
 Para obtener más información, vea [proteger conversaciones y sesiones seguras](secure-conversations-and-secure-sessions.md).  
  
## <a name="procedures"></a>Procedimientos  
  
#### <a name="to-create-a-custom-binding-that-uses-a-symmetricsecuritybindingelement"></a>Para crear un enlace personalizado que utilice un SymmetricSecurityBindingElement  
  
1. Cree una instancia de la clase <xref:System.ServiceModel.Channels.BindingElementCollection> con el nombre `outputBec`.  
  
2. Llame al método estático `M:System.ServiceModel.Channels.SecurityBindingElement.CreateSspiNegotiationBindingElement(true)`, que devuelve una instancia de la clase <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>.  
  
3. Agregue el <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> a la colección (`outputBec`) llamando a `Add` del método de la <xref:System.Collections.ObjectModel.Collection%601> de la clase <xref:System.ServiceModel.Channels.BindingElement>.  
  
4. Cree una instancia de la clase <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> y agréguela a la colección (`outputBec`). Esto especifica la codificación utilizada por el enlace.  
  
5. Cree un <xref:System.ServiceModel.Channels.HttpTransportBindingElement> y agréguelo a la colección (`outputBec`). Esto especifica que el enlace utiliza el transporte HTTP.  
  
6. Cree un nuevo enlace personalizado creando una instancia de la clase <xref:System.ServiceModel.Channels.CustomBinding> y pasando la colección `outputBec` al constructor.  
  
7. El enlace personalizado resultante comparte muchas de las mismas características que el <xref:System.ServiceModel.WSHttpBinding> estándar. Especifica seguridad del nivel de mensaje y credenciales de Windows pero deshabilita las sesiones seguras, requiere que la credencial del servicio se especifique fuera de banda, y no cifra las firmas. Lo último solo puede controlarse estableciendo la propiedad <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement.MessageProtectionOrder%2A> como se muestra en el paso 4. Los otros dos se pueden controlar usando los valores del enlace estándar.  
  
## <a name="example"></a>Ejemplo  
  
### <a name="description"></a>Descripción  

 El ejemplo siguiente proporciona una función completa para crear un enlace personalizado que utilice <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>.  
  
### <a name="code"></a>Código  

 [!code-csharp[c_CustomBinding#20](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#20)]
 [!code-vb[c_CustomBinding#20](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_custombinding/vb/source.vb#20)]  
  
## <a name="see-also"></a>Consulte también

- <xref:System.ServiceModel.Channels.SecurityBindingElement>
- <xref:System.ServiceModel.Channels.TransportSecurityBindingElement>
- <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [Extensión de enlaces](../extending/extending-bindings.md)
- [Enlaces proporcionados por el sistema](../system-provided-bindings.md)
