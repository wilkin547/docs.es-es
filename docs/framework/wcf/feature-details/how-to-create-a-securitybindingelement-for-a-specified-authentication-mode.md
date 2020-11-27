---
title: Procedimiento para crear un SecurityBindingElement para un modo de autenticación especificado
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a7c7747a-5b8c-463f-8493-7266dac75066
ms.openlocfilehash: 7b71224c74d7e9e766fb17101219dc5718d5d6a6
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96286440"
---
# <a name="how-to-create-a-securitybindingelement-for-a-specified-authentication-mode"></a><span data-ttu-id="aa55f-102">Procedimiento para crear un SecurityBindingElement para un modo de autenticación especificado</span><span class="sxs-lookup"><span data-stu-id="aa55f-102">How to: Create a SecurityBindingElement for a Specified Authentication Mode</span></span>

<span data-ttu-id="aa55f-103">Windows Communication Foundation (WCF) proporciona varios modos en los que los clientes y servicios se autentican entre sí.</span><span class="sxs-lookup"><span data-stu-id="aa55f-103">Windows Communication Foundation (WCF) provides several modes by which clients and services authenticate to one another.</span></span> <span data-ttu-id="aa55f-104">Puede crear los elementos de enlace de seguridad para estos modos de autenticación utilizando los métodos estáticos en la clase <xref:System.ServiceModel.Channels.SecurityBindingElement> o a través de la configuración, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="aa55f-104">You can create security binding elements for these authentication modes by using static methods on the <xref:System.ServiceModel.Channels.SecurityBindingElement> class or through configuration, as shown in the following example.</span></span>  
  
 <span data-ttu-id="aa55f-105">Para obtener más información sobre los 18 modos de autenticación, consulte [modos de autenticación de SecurityBindingElement](securitybindingelement-authentication-modes.md).</span><span class="sxs-lookup"><span data-stu-id="aa55f-105">For more information about the 18 authentication modes, see [SecurityBindingElement Authentication Modes](securitybindingelement-authentication-modes.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="aa55f-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="aa55f-106">Example</span></span>  

 <span data-ttu-id="aa55f-107">El ejemplo de código siguiente muestra los métodos para crear los enlaces para los diferentes modos de autenticación.</span><span class="sxs-lookup"><span data-stu-id="aa55f-107">The following code example shows methods for creating bindings for the various authentication modes.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="aa55f-108">Una vez creada una instancia del objeto <xref:System.ServiceModel.Channels.SecurityBindingElement>, varias propiedades son inmutables, como <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.KeyType%2A> y <xref:System.ServiceModel.Channels.SecurityBindingElement.MessageSecurityVersion%2A>.</span><span class="sxs-lookup"><span data-stu-id="aa55f-108">Once an instance of the <xref:System.ServiceModel.Channels.SecurityBindingElement> object is created, a number of properties are immutable, such as <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.KeyType%2A> and <xref:System.ServiceModel.Channels.SecurityBindingElement.MessageSecurityVersion%2A>.</span></span> <span data-ttu-id="aa55f-109">El hecho de llamar a `set` en tales propiedades, no las cambia.</span><span class="sxs-lookup"><span data-stu-id="aa55f-109">Calling `set` on such properties does not change them.</span></span>  
  
 [!code-csharp[c_CustomBindingsAuthMode#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombindingsauthmode/cs/source.cs#2)]
 [!code-vb[c_CustomBindingsAuthMode#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_custombindingsauthmode/vb/source.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="aa55f-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="aa55f-110">See also</span></span>

- [<span data-ttu-id="aa55f-111">Modos de autenticación de SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="aa55f-111">SecurityBindingElement Authentication Modes</span></span>](securitybindingelement-authentication-modes.md)
- [<span data-ttu-id="aa55f-112">Procedimiento para crear un enlace personalizado mediante SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="aa55f-112">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](how-to-create-a-custom-binding-using-the-securitybindingelement.md)
