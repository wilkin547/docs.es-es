---
description: 'Más información acerca de cómo: deshabilitar sesiones seguras en un WSFederationHttpBinding'
title: Procedimiento para deshabilitar sesiones seguras en WSFederationHttpBinding
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, federation
- federation
ms.assetid: 675fa143-6a4e-4be3-8afc-673334ab55ec
ms.openlocfilehash: 73fb25c55cb6f7be13a286cf8e16701095739827
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99756128"
---
# <a name="how-to-disable-secure-sessions-on-a-wsfederationhttpbinding"></a><span data-ttu-id="6f1f2-103">Procedimiento para deshabilitar sesiones seguras en WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="6f1f2-103">How to: Disable Secure Sessions on a WSFederationHttpBinding</span></span>

<span data-ttu-id="6f1f2-104">Algunos servicios pueden requerir credenciales federadas pero no admiten sesiones seguras.</span><span class="sxs-lookup"><span data-stu-id="6f1f2-104">Some services may require federated credentials but not support secure sessions.</span></span> <span data-ttu-id="6f1f2-105">En ese caso, debe deshabilitar la característica de sesión segura.</span><span class="sxs-lookup"><span data-stu-id="6f1f2-105">In that case, you must disable the secure session feature.</span></span> <span data-ttu-id="6f1f2-106">A diferencia de <xref:System.ServiceModel.WSHttpBinding>, la clase <xref:System.ServiceModel.WSFederationHttpBinding> no proporciona ninguna manera de deshabilitar las sesiones seguras al comunicarse con un servicio.</span><span class="sxs-lookup"><span data-stu-id="6f1f2-106">Unlike the <xref:System.ServiceModel.WSHttpBinding>, the <xref:System.ServiceModel.WSFederationHttpBinding> class does not provide a way to disable secure sessions when communicating with a service.</span></span> <span data-ttu-id="6f1f2-107">En su lugar, debe crear un enlace personalizado que reemplace los valores de sesión seguros con un arranque.</span><span class="sxs-lookup"><span data-stu-id="6f1f2-107">Instead, you must create a custom binding that replaces the secure session settings with a bootstrap.</span></span>

<span data-ttu-id="6f1f2-108">En este tema se muestra cómo modificar los elementos de enlace contenidos dentro de <xref:System.ServiceModel.WSFederationHttpBinding> para crear un enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="6f1f2-108">This topic demonstrates how to modify the binding elements contained within a <xref:System.ServiceModel.WSFederationHttpBinding> to create a custom binding.</span></span> <span data-ttu-id="6f1f2-109">El resultado es idéntico al <xref:System.ServiceModel.WSFederationHttpBinding>, solo que no utiliza las sesiones seguras.</span><span class="sxs-lookup"><span data-stu-id="6f1f2-109">The result is identical to the <xref:System.ServiceModel.WSFederationHttpBinding> except that it does not use secure sessions.</span></span>

## <a name="to-create-a-custom-federated-binding-without-secure-session"></a><span data-ttu-id="6f1f2-110">Para crear un enlace federado personalizado sin sesión segura</span><span class="sxs-lookup"><span data-stu-id="6f1f2-110">To create a custom federated binding without secure session</span></span>

1. <span data-ttu-id="6f1f2-111">Cree una instancia de la clase <xref:System.ServiceModel.WSFederationHttpBinding> en código de manera imperativa o cargando una del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="6f1f2-111">Create an instance of the <xref:System.ServiceModel.WSFederationHttpBinding> class either imperatively in code or by loading one from the configuration file.</span></span>

2. <span data-ttu-id="6f1f2-112">Clone el <xref:System.ServiceModel.WSFederationHttpBinding> en un <xref:System.ServiceModel.Channels.CustomBinding>.</span><span class="sxs-lookup"><span data-stu-id="6f1f2-112">Clone the <xref:System.ServiceModel.WSFederationHttpBinding> into a <xref:System.ServiceModel.Channels.CustomBinding>.</span></span>

3. <span data-ttu-id="6f1f2-113">Encuentre el <xref:System.ServiceModel.Channels.SecurityBindingElement> en el <xref:System.ServiceModel.Channels.CustomBinding>.</span><span class="sxs-lookup"><span data-stu-id="6f1f2-113">Find the <xref:System.ServiceModel.Channels.SecurityBindingElement> in the <xref:System.ServiceModel.Channels.CustomBinding>.</span></span>

4. <span data-ttu-id="6f1f2-114">Encuentre el <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters> en el <xref:System.ServiceModel.Channels.SecurityBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="6f1f2-114">Find the <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters> in the <xref:System.ServiceModel.Channels.SecurityBindingElement>.</span></span>

5. <span data-ttu-id="6f1f2-115">Sustituya el original <xref:System.ServiceModel.Channels.SecurityBindingElement> con el elemento de enlace de seguridad de arranque de los <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters>.</span><span class="sxs-lookup"><span data-stu-id="6f1f2-115">Replace the original <xref:System.ServiceModel.Channels.SecurityBindingElement> with the bootstrap security binding element from the <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters>.</span></span>

## <a name="example"></a><span data-ttu-id="6f1f2-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6f1f2-116">Example</span></span>

<span data-ttu-id="6f1f2-117">Este ejemplo crea un enlace federado personalizado sin sesión segura.</span><span class="sxs-lookup"><span data-stu-id="6f1f2-117">This following example creates a custom federated binding without secure session.</span></span>

[!code-csharp[c_CustomFederationBinding#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customfederationbinding/cs/c_customfederationbinding.cs#0)]
[!code-vb[c_CustomFederationBinding#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customfederationbinding/vb/c_customfederationbinding.vb#0)]

## <a name="compiling-the-code"></a><span data-ttu-id="6f1f2-118">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="6f1f2-118">Compiling the Code</span></span>

- <span data-ttu-id="6f1f2-119">Para compilar el ejemplo de código, cree un proyecto que haga referencia al ensamblado System.ServiceModel.dll.</span><span class="sxs-lookup"><span data-stu-id="6f1f2-119">To compile the code example, create a project that references the System.ServiceModel.dll assembly.</span></span>

## <a name="see-also"></a><span data-ttu-id="6f1f2-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="6f1f2-120">See also</span></span>

- [<span data-ttu-id="6f1f2-121">Enlaces y seguridad</span><span class="sxs-lookup"><span data-stu-id="6f1f2-121">Bindings and Security</span></span>](bindings-and-security.md)
