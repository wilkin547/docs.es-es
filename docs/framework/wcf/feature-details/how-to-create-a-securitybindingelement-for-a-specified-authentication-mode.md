---
title: "Cómo: Crear un SecurityBindingElement para un modo de autenticación especificado"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: a7c7747a-5b8c-463f-8493-7266dac75066
caps.latest.revision: "9"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 658eaf3469e0be179c78d9963687e6de9cb7fc00
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-securitybindingelement-for-a-specified-authentication-mode"></a><span data-ttu-id="f048f-102">Cómo: Crear un SecurityBindingElement para un modo de autenticación especificado</span><span class="sxs-lookup"><span data-stu-id="f048f-102">How to: Create a SecurityBindingElement for a Specified Authentication Mode</span></span>
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="f048f-103"> proporciona varios modos por medio de los cuales los clientes y servicios se autentican entre sí.</span><span class="sxs-lookup"><span data-stu-id="f048f-103"> provides several modes by which clients and services authenticate to one another.</span></span> <span data-ttu-id="f048f-104">Puede crear los elementos de enlace de seguridad para estos modos de autenticación utilizando los métodos estáticos en la clase <xref:System.ServiceModel.Channels.SecurityBindingElement> o a través de la configuración, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="f048f-104">You can create security binding elements for these authentication modes by using static methods on the <xref:System.ServiceModel.Channels.SecurityBindingElement> class or through configuration, as shown in the following example.</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="f048f-105">los modos de 18 autenticación, consulte [modos de autenticación de SecurityBindingElement](../../../../docs/framework/wcf/feature-details/securitybindingelement-authentication-modes.md).</span><span class="sxs-lookup"><span data-stu-id="f048f-105"> the 18 authentication modes, see [SecurityBindingElement Authentication Modes](../../../../docs/framework/wcf/feature-details/securitybindingelement-authentication-modes.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f048f-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f048f-106">Example</span></span>  
 <span data-ttu-id="f048f-107">El ejemplo de código siguiente muestra los métodos para crear los enlaces para los diferentes modos de autenticación.</span><span class="sxs-lookup"><span data-stu-id="f048f-107">The following code example shows methods for creating bindings for the various authentication modes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f048f-108">Una vez creada una instancia del objeto <xref:System.ServiceModel.Channels.SecurityBindingElement>, varias propiedades son inmutables, como <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.KeyType%2A> y <xref:System.ServiceModel.Channels.SecurityBindingElement.MessageSecurityVersion%2A>.</span><span class="sxs-lookup"><span data-stu-id="f048f-108">Once an instance of the <xref:System.ServiceModel.Channels.SecurityBindingElement> object is created, a number of properties are immutable, such as <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.KeyType%2A> and <xref:System.ServiceModel.Channels.SecurityBindingElement.MessageSecurityVersion%2A>.</span></span> <span data-ttu-id="f048f-109">El hecho de llamar a `set` en tales propiedades, no las cambia.</span><span class="sxs-lookup"><span data-stu-id="f048f-109">Calling `set` on such properties does not change them.</span></span>  
  
 [!code-csharp[c_CustomBindingsAuthMode#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombindingsauthmode/cs/source.cs#2)]
 [!code-vb[c_CustomBindingsAuthMode#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_custombindingsauthmode/vb/source.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="f048f-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="f048f-110">See Also</span></span>  
 [<span data-ttu-id="f048f-111">Modos de autenticación de SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="f048f-111">SecurityBindingElement Authentication Modes</span></span>](../../../../docs/framework/wcf/feature-details/securitybindingelement-authentication-modes.md)  
 [<span data-ttu-id="f048f-112">Cómo: crear un enlace personalizado mediante SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="f048f-112">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
