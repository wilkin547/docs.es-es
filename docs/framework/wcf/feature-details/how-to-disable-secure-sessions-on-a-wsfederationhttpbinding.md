---
title: Filtrar para deshabilitar sesiones seguras en WSFederationHttpBinding
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, federation
- federation
ms.assetid: 675fa143-6a4e-4be3-8afc-673334ab55ec
ms.openlocfilehash: 809626d0d6d69d22f09b0f10210cfda7a033ac3d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59211808"
---
# <a name="how-to-disable-secure-sessions-on-a-wsfederationhttpbinding"></a><span data-ttu-id="8afcd-102">Filtrar para deshabilitar sesiones seguras en WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="8afcd-102">How to: Disable Secure Sessions on a WSFederationHttpBinding</span></span>
<span data-ttu-id="8afcd-103">Algunos servicios pueden requerir credenciales federadas pero no admiten sesiones seguras.</span><span class="sxs-lookup"><span data-stu-id="8afcd-103">Some services may require federated credentials but not support secure sessions.</span></span> <span data-ttu-id="8afcd-104">En ese caso, debe deshabilitar la característica de sesión segura.</span><span class="sxs-lookup"><span data-stu-id="8afcd-104">In that case, you must disable the secure session feature.</span></span> <span data-ttu-id="8afcd-105">A diferencia de <xref:System.ServiceModel.WSHttpBinding>, la clase <xref:System.ServiceModel.WSFederationHttpBinding> no proporciona ninguna manera de deshabilitar las sesiones seguras al comunicarse con un servicio.</span><span class="sxs-lookup"><span data-stu-id="8afcd-105">Unlike the <xref:System.ServiceModel.WSHttpBinding>, the <xref:System.ServiceModel.WSFederationHttpBinding> class does not provide a way to disable secure sessions when communicating with a service.</span></span> <span data-ttu-id="8afcd-106">En su lugar, debe crear un enlace personalizado que reemplace los valores de sesión seguros con un arranque.</span><span class="sxs-lookup"><span data-stu-id="8afcd-106">Instead, you must create a custom binding that replaces the secure session settings with a bootstrap.</span></span>  
  
 <span data-ttu-id="8afcd-107">En este tema se muestra cómo modificar los elementos de enlace contenidos dentro de <xref:System.ServiceModel.WSFederationHttpBinding> para crear un enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="8afcd-107">This topic demonstrates how to modify the binding elements contained within a <xref:System.ServiceModel.WSFederationHttpBinding> to create a custom binding.</span></span> <span data-ttu-id="8afcd-108">El resultado es idéntico al <xref:System.ServiceModel.WSFederationHttpBinding>, solo que no utiliza las sesiones seguras.</span><span class="sxs-lookup"><span data-stu-id="8afcd-108">The result is identical to the <xref:System.ServiceModel.WSFederationHttpBinding> except that it does not use secure sessions.</span></span>  
  
### <a name="to-create-a-custom-federated-binding-without-secure-session"></a><span data-ttu-id="8afcd-109">Para crear un enlace federado personalizado sin sesión segura</span><span class="sxs-lookup"><span data-stu-id="8afcd-109">To create a custom federated binding without secure session</span></span>  
  
1.  <span data-ttu-id="8afcd-110">Cree una instancia de la clase <xref:System.ServiceModel.WSFederationHttpBinding> en código de manera imperativa o cargando una del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="8afcd-110">Create an instance of the <xref:System.ServiceModel.WSFederationHttpBinding> class either imperatively in code or by loading one from the configuration file.</span></span>  
  
2.  <span data-ttu-id="8afcd-111">Clone el <xref:System.ServiceModel.WSFederationHttpBinding> en un <xref:System.ServiceModel.Channels.CustomBinding>.</span><span class="sxs-lookup"><span data-stu-id="8afcd-111">Clone the <xref:System.ServiceModel.WSFederationHttpBinding> into a <xref:System.ServiceModel.Channels.CustomBinding>.</span></span>  
  
3.  <span data-ttu-id="8afcd-112">Encuentre el <xref:System.ServiceModel.Channels.SecurityBindingElement> en el <xref:System.ServiceModel.Channels.CustomBinding>.</span><span class="sxs-lookup"><span data-stu-id="8afcd-112">Find the <xref:System.ServiceModel.Channels.SecurityBindingElement> in the <xref:System.ServiceModel.Channels.CustomBinding>.</span></span>  
  
4.  <span data-ttu-id="8afcd-113">Encuentre el <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters> en el <xref:System.ServiceModel.Channels.SecurityBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="8afcd-113">Find the <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters> in the <xref:System.ServiceModel.Channels.SecurityBindingElement>.</span></span>  
  
5.  <span data-ttu-id="8afcd-114">Sustituya el original <xref:System.ServiceModel.Channels.SecurityBindingElement> con el elemento de enlace de seguridad de arranque de los <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters>.</span><span class="sxs-lookup"><span data-stu-id="8afcd-114">Replace the original <xref:System.ServiceModel.Channels.SecurityBindingElement> with the bootstrap security binding element from the <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8afcd-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8afcd-115">Example</span></span>  
 <span data-ttu-id="8afcd-116">Este ejemplo crea un enlace federado personalizado sin sesión segura.</span><span class="sxs-lookup"><span data-stu-id="8afcd-116">This following example creates a custom federated binding without secure session.</span></span>  
  
 [!code-csharp[c_CustomFederationBinding#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customfederationbinding/cs/c_customfederationbinding.cs#0)]
 [!code-vb[c_CustomFederationBinding#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customfederationbinding/vb/c_customfederationbinding.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8afcd-117">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="8afcd-117">Compiling the Code</span></span>  
  
-   <span data-ttu-id="8afcd-118">Para compilar el ejemplo de código, cree un proyecto que haga referencia al ensamblado System.ServiceModel.dll.</span><span class="sxs-lookup"><span data-stu-id="8afcd-118">To compile the code example, create a project that references the System.ServiceModel.dll assembly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8afcd-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="8afcd-119">See also</span></span>

- [<span data-ttu-id="8afcd-120">Enlaces y seguridad</span><span class="sxs-lookup"><span data-stu-id="8afcd-120">Bindings and Security</span></span>](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)
