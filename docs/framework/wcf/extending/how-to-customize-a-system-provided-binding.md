---
title: Procedimiento para personalizar un enlace proporcionado por el sistema
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f8b97862-e8bb-470d-8b96-07733c21fe26
ms.openlocfilehash: 0c5474a65bee7d3d290372e79f8423ea9986235f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59301183"
---
# <a name="how-to-customize-a-system-provided-binding"></a>Procedimiento para personalizar un enlace proporcionado por el sistema
Windows Communication Foundation (WCF) incluye varios enlaces proporcionados por el sistema que le permiten configurar algunas de las propiedades de los elementos de enlace subyacente, pero no todas las propiedades. En este tema se muestra cómo establecer las propiedades en los elementos de enlace para crear un enlace personalizado.  
  
 Para obtener más información acerca de cómo crear y configurar elementos de enlace sin utilizar los enlaces proporcionados por el sistema directamente, vea [enlaces personalizados](../../../../docs/framework/wcf/extending/custom-bindings.md).  
  
 Para obtener más información sobre la creación y extensión de enlaces personalizados, consulte [extender enlaces](../../../../docs/framework/wcf/extending/extending-bindings.md).  
  
 En WCF todos los enlaces se componen de *elementos de enlace*. Cada elemento de enlace deriva de la clase <xref:System.ServiceModel.Channels.BindingElement>. Los enlaces proporcionados por el sistema, como <xref:System.ServiceModel.BasicHttpBinding> crean y configuran sus propios elementos de enlace. En este tema se muestra cómo obtener acceso y cambiar las propiedades de estos elementos de enlace, que no se exponen directamente en el enlace; en concreto, la clase <xref:System.ServiceModel.BasicHttpBinding>.  
  
 Los elementos de enlace individuales se incluyen en una colección representada por el <xref:System.ServiceModel.Channels.BindingElementCollection> clase y se agregan en este orden: Flujo de transacciones, sesión confiable, seguridad, dúplex compuesto, unidireccional, seguridad de Stream, codificación de mensajes y transporte. Tenga en cuenta que no todos los elementos de enlace enumerados se necesitan en cada enlace. Los elementos de enlace definidos por el usuario pueden aparecer también en esta colección de elementos de enlace y deben aparecer en el orden descrito anteriormente. Por ejemplo, un transporte definido por el usuario debe ser el último elemento de la colección de elementos de enlace.  
  
 La clase <xref:System.ServiceModel.BasicHttpBinding> contiene tres elementos de enlace:  
  
1. Un elemento de enlace de seguridad opcional, la clase <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement> utilizada con el transporte HTTP (seguridad de mensajes) o la clase <xref:System.ServiceModel.Channels.TransportSecurityBindingElement>, que se utiliza cuando el nivel de transporte proporciona seguridad, en cuyo caso se utiliza el transporte de HTTPS.  
  
2. Un elemento de enlace del codificador de mensajes requerido, <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> o <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>.  
  
3. Un elemento de enlace del transporte requerido, o <xref:System.ServiceModel.Channels.HttpTransportBindingElement>, o <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>.  
  
 En este ejemplo se crea una instancia del enlace, genere un *enlace personalizado* , examine los elementos de enlace en el enlace personalizado, y cuando encontramos el elemento de enlace de HTTP, establecemos su `KeepAliveEnabled` propiedad `false`. La propiedad `KeepAliveEnabled` no se expone directamente en `BasicHttpBinding`, por lo que debemos crear un enlace personalizado para explorar hacia abajo hasta el elemento de enlace y establecer esta propiedad.  
  
### <a name="to-modify-a-system-provided-binding"></a>Modificación de un enlace proporcionado por el sistema  
  
1. Cree una instancia de la clase <xref:System.ServiceModel.BasicHttpBinding> y establezca su modo de seguridad en el nivel de mensaje.  
  
     [!code-csharp[C_HowTo_ChangeStandardBinding#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_changestandardbinding/cs/program.cs#1)]
     [!code-vb[C_HowTo_ChangeStandardBinding#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_changestandardbinding/vb/program.vb#1)]  
  
2. Cree un enlace personalizado a partir del enlace y cree una clase <xref:System.ServiceModel.Channels.BindingElementCollection> a partir de una de las propiedades del enlace personalizado.  
  
     [!code-csharp[C_HowTo_ChangeStandardBinding#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_changestandardbinding/cs/program.cs#2)]
     [!code-vb[C_HowTo_ChangeStandardBinding#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_changestandardbinding/vb/program.vb#2)]  
  
3. Recorra a través de la clase <xref:System.ServiceModel.Channels.BindingElementCollection> y cuando encuentre la clase <xref:System.ServiceModel.Channels.HttpTransportBindingElement>, establezca su propiedad <xref:System.ServiceModel.Channels.HttpTransportBindingElement.KeepAliveEnabled%2A> en `false`.  
  
     [!code-csharp[C_HowTo_ChangeStandardBinding#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_changestandardbinding/cs/program.cs#3)]
     [!code-vb[C_HowTo_ChangeStandardBinding#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_changestandardbinding/vb/program.vb#3)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Channels.HttpTransportBindingElement>
- <xref:System.ServiceModel.BasicHttpBinding>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [Enlaces personalizados](../../../../docs/framework/wcf/extending/custom-bindings.md)
