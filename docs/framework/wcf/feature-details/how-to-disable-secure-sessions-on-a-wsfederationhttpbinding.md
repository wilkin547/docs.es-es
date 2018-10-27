---
title: Cómo deshabilitar sesiones seguras en WSFederationHttpBinding
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, federation
- federation
ms.assetid: 675fa143-6a4e-4be3-8afc-673334ab55ec
ms.openlocfilehash: ce02e562f3c6e92b6dfadbb065730e9f1644b82a
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/25/2018
ms.locfileid: "50042511"
---
# <a name="how-to-disable-secure-sessions-on-a-wsfederationhttpbinding"></a>Cómo deshabilitar sesiones seguras en WSFederationHttpBinding
Algunos servicios pueden requerir credenciales federadas pero no admiten sesiones seguras. En ese caso, debe deshabilitar la característica de sesión segura. A diferencia de la <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`>, el <xref:System.ServiceModel.WSFederationHttpBinding> clase no proporciona una manera de deshabilitar las sesiones seguras al comunicarse con un servicio. En su lugar, debe crear un enlace personalizado que reemplace los valores de sesión seguros con un arranque.  
  
 En este tema se muestra cómo modificar los elementos de enlace contenidos dentro de <xref:System.ServiceModel.WSFederationHttpBinding> para crear un enlace personalizado. El resultado es idéntico al <xref:System.ServiceModel.WSFederationHttpBinding>, solo que no utiliza las sesiones seguras.  
  
### <a name="to-create-a-custom-federated-binding-without-secure-session"></a>Para crear un enlace federado personalizado sin sesión segura  
  
1.  Cree una instancia de la clase <xref:System.ServiceModel.WSFederationHttpBinding> en código de manera imperativa o cargando una del archivo de configuración.  
  
2.  Clone el <xref:System.ServiceModel.WSFederationHttpBinding> en un <xref:System.ServiceModel.Channels.CustomBinding>.  
  
3.  Encuentre el <xref:System.ServiceModel.Channels.SecurityBindingElement> en el <xref:System.ServiceModel.Channels.CustomBinding>.  
  
4.  Encuentre el <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters> en el <xref:System.ServiceModel.Channels.SecurityBindingElement>.  
  
5.  Sustituya el original <xref:System.ServiceModel.Channels.SecurityBindingElement> con el elemento de enlace de seguridad de arranque de los <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters>.  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo crea un enlace federado personalizado sin sesión segura.  
  
 [!code-csharp[c_CustomFederationBinding#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customfederationbinding/cs/c_customfederationbinding.cs#0)]
 [!code-vb[c_CustomFederationBinding#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customfederationbinding/vb/c_customfederationbinding.vb#0)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
  
-   Para compilar el ejemplo de código, cree un proyecto que haga referencia al ensamblado System.ServiceModel.dll.  
  
## <a name="see-also"></a>Vea también  
 [Enlaces y seguridad](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)
