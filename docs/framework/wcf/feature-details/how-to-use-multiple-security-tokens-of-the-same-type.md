---
title: 'Cómo: Utilizar múltiples tokens de seguridad del mismo tipo'
ms.date: 03/30/2017
ms.assetid: cf179f48-4ed4-4caa-86a5-ef8eecc231cd
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 25afbb268a0ef7772585a0f3829b56f135758b61
ms.sourcegitcommit: 8c2ece71e54f46aef9a2153540d0bda7e74b19a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2018
ms.locfileid: "44507924"
---
# <a name="how-to-use-multiple-security-tokens-of-the-same-type"></a><span data-ttu-id="43896-102">Cómo: Utilizar múltiples tokens de seguridad del mismo tipo</span><span class="sxs-lookup"><span data-stu-id="43896-102">How to: Use Multiple Security Tokens of the Same Type</span></span>
-   <span data-ttu-id="43896-103">En [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 3.0, un mensaje de cliente solo contenía un token de un tipo dado.</span><span class="sxs-lookup"><span data-stu-id="43896-103">In [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 3.0, a client message only contained one token of any given type.</span></span> <span data-ttu-id="43896-104">Ahora, los mensajes de cliente pueden contener múltiples tokens de un tipo.</span><span class="sxs-lookup"><span data-stu-id="43896-104">Now client messages can contain multiple tokens of a type.</span></span> <span data-ttu-id="43896-105">En este tema se muestra cómo incluir múltiples tokens del mismo tipo en un mensaje de cliente.</span><span class="sxs-lookup"><span data-stu-id="43896-105">This topic shows how to include multiple tokens of the same type in a client message.</span></span>  
  
-   <span data-ttu-id="43896-106">Tenga en cuenta que no se puede configurar un servicio de esta manera: un servicio puede contener sólo un token auxiliar.</span><span class="sxs-lookup"><span data-stu-id="43896-106">Note that you cannot configure a service in this way: a service can contain only one supporting token.</span></span>  
  
### <a name="to-use-multiple-security-tokens-of-the-same-type"></a><span data-ttu-id="43896-107">Utilizar múltiples tokens de seguridad del mismo tipo</span><span class="sxs-lookup"><span data-stu-id="43896-107">To use multiple security tokens of the same type</span></span>  
  
1.  <span data-ttu-id="43896-108">Cree una colección vacía de elementos de enlace para rellenarla.</span><span class="sxs-lookup"><span data-stu-id="43896-108">Create an empty binding element collection to be populated.</span></span>  
  
     [!code-csharp[C_CustomBinding#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#9)]  
  
2.  <span data-ttu-id="43896-109">Cree <xref:System.ServiceModel.Channels.SecurityBindingElement> llamando a <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateMutualCertificateBindingElement%2A>.</span><span class="sxs-lookup"><span data-stu-id="43896-109">Create a <xref:System.ServiceModel.Channels.SecurityBindingElement> by calling <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateMutualCertificateBindingElement%2A>.</span></span>  
  
     [!code-csharp[C_CustomBinding#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#10)]  
  
3.  <span data-ttu-id="43896-110">Cree una colección <xref:System.ServiceModel.Security.Tokens.SupportingTokenParameters>.</span><span class="sxs-lookup"><span data-stu-id="43896-110">Create a <xref:System.ServiceModel.Security.Tokens.SupportingTokenParameters> collection.</span></span>  
  
     [!code-csharp[C_CustomBinding#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#11)]  
  
4.  <span data-ttu-id="43896-111">Agregue tokens SAML a la colección.</span><span class="sxs-lookup"><span data-stu-id="43896-111">Add SAML tokens to the collection.</span></span>  
  
     [!code-csharp[C_CustomBinding#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#12)]  
  
5.  <span data-ttu-id="43896-112">Agregue la colección a <xref:System.ServiceModel.Channels.SecurityBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="43896-112">Add the collection to the <xref:System.ServiceModel.Channels.SecurityBindingElement>.</span></span>  
  
     [!code-csharp[C_CustomBinding#13](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#13)]  
  
6.  <span data-ttu-id="43896-113">Agregue elementos de enlace a la colección de elementos de enlace.</span><span class="sxs-lookup"><span data-stu-id="43896-113">Add binding elements to the binding element collection.</span></span>  
  
     [!code-csharp[C_CustomBinding#14](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#14)]  
  
7.  <span data-ttu-id="43896-114">Devuelva un nuevo enlace personalizado creado a partir de la colección de elementos de enlace.</span><span class="sxs-lookup"><span data-stu-id="43896-114">Return a new custom binding created from the binding element collection.</span></span>  
  
     [!code-csharp[C_CustomBinding#15](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#15)]  
  
## <a name="example"></a><span data-ttu-id="43896-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="43896-115">Example</span></span>  
 <span data-ttu-id="43896-116">Lo siguiente es el método completo descrito por el procedimiento anterior.</span><span class="sxs-lookup"><span data-stu-id="43896-116">The following is the entire method described by the preceding procedure.</span></span>  
  
 [!code-csharp[C_CustomBinding#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#7)]  
  
## <a name="see-also"></a><span data-ttu-id="43896-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="43896-117">See Also</span></span>  
 [<span data-ttu-id="43896-118">Arquitectura de seguridad</span><span class="sxs-lookup"><span data-stu-id="43896-118">Security Architecture</span></span>](https://msdn.microsoft.com/library/16593476-d36a-408d-808c-ae6fd483e28f)
