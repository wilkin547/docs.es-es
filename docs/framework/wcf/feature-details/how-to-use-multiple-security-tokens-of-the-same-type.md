---
title: Procedimiento para usar varios tokens de seguridad del mismo tipo
ms.date: 03/30/2017
ms.assetid: cf179f48-4ed4-4caa-86a5-ef8eecc231cd
ms.openlocfilehash: 1b383c6ccd96d1b3d7b091b2d7c67bb166da51df
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2019
ms.locfileid: "65589423"
---
# <a name="how-to-use-multiple-security-tokens-of-the-same-type"></a><span data-ttu-id="0caa1-102">Procedimiento para usar varios tokens de seguridad del mismo tipo</span><span class="sxs-lookup"><span data-stu-id="0caa1-102">How to: Use Multiple Security Tokens of the Same Type</span></span>
- <span data-ttu-id="0caa1-103">En .NET Framework 3.0, un mensaje de cliente solo contenía un token de un tipo dado.</span><span class="sxs-lookup"><span data-stu-id="0caa1-103">In .NET Framework 3.0, a client message only contained one token of any given type.</span></span> <span data-ttu-id="0caa1-104">Ahora, los mensajes de cliente pueden contener múltiples tokens de un tipo.</span><span class="sxs-lookup"><span data-stu-id="0caa1-104">Now client messages can contain multiple tokens of a type.</span></span> <span data-ttu-id="0caa1-105">En este tema se muestra cómo incluir múltiples tokens del mismo tipo en un mensaje de cliente.</span><span class="sxs-lookup"><span data-stu-id="0caa1-105">This topic shows how to include multiple tokens of the same type in a client message.</span></span>  
  
- <span data-ttu-id="0caa1-106">Tenga en cuenta que no se puede configurar un servicio de esta manera: un servicio puede contener sólo un token auxiliar.</span><span class="sxs-lookup"><span data-stu-id="0caa1-106">Note that you cannot configure a service in this way: a service can contain only one supporting token.</span></span>  
  
### <a name="to-use-multiple-security-tokens-of-the-same-type"></a><span data-ttu-id="0caa1-107">Utilizar múltiples tokens de seguridad del mismo tipo</span><span class="sxs-lookup"><span data-stu-id="0caa1-107">To use multiple security tokens of the same type</span></span>  
  
1. <span data-ttu-id="0caa1-108">Cree una colección vacía de elementos de enlace para rellenarla.</span><span class="sxs-lookup"><span data-stu-id="0caa1-108">Create an empty binding element collection to be populated.</span></span>  
  
     [!code-csharp[C_CustomBinding#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#9)]  
  
2. <span data-ttu-id="0caa1-109">Cree <xref:System.ServiceModel.Channels.SecurityBindingElement> llamando a <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateMutualCertificateBindingElement%2A>.</span><span class="sxs-lookup"><span data-stu-id="0caa1-109">Create a <xref:System.ServiceModel.Channels.SecurityBindingElement> by calling <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateMutualCertificateBindingElement%2A>.</span></span>  
  
     [!code-csharp[C_CustomBinding#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#10)]  
  
3. <span data-ttu-id="0caa1-110">Cree una colección <xref:System.ServiceModel.Security.Tokens.SupportingTokenParameters>.</span><span class="sxs-lookup"><span data-stu-id="0caa1-110">Create a <xref:System.ServiceModel.Security.Tokens.SupportingTokenParameters> collection.</span></span>  
  
     [!code-csharp[C_CustomBinding#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#11)]  
  
4. <span data-ttu-id="0caa1-111">Agregue tokens SAML a la colección.</span><span class="sxs-lookup"><span data-stu-id="0caa1-111">Add SAML tokens to the collection.</span></span>  
  
     [!code-csharp[C_CustomBinding#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#12)]  
  
5. <span data-ttu-id="0caa1-112">Agregue la colección a <xref:System.ServiceModel.Channels.SecurityBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="0caa1-112">Add the collection to the <xref:System.ServiceModel.Channels.SecurityBindingElement>.</span></span>  
  
     [!code-csharp[C_CustomBinding#13](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#13)]  
  
6. <span data-ttu-id="0caa1-113">Agregue elementos de enlace a la colección de elementos de enlace.</span><span class="sxs-lookup"><span data-stu-id="0caa1-113">Add binding elements to the binding element collection.</span></span>  
  
     [!code-csharp[C_CustomBinding#14](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#14)]  
  
7. <span data-ttu-id="0caa1-114">Devuelva un nuevo enlace personalizado creado a partir de la colección de elementos de enlace.</span><span class="sxs-lookup"><span data-stu-id="0caa1-114">Return a new custom binding created from the binding element collection.</span></span>  
  
     [!code-csharp[C_CustomBinding#15](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#15)]  
  
## <a name="example"></a><span data-ttu-id="0caa1-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0caa1-115">Example</span></span>  
 <span data-ttu-id="0caa1-116">Lo siguiente es el método completo descrito por el procedimiento anterior.</span><span class="sxs-lookup"><span data-stu-id="0caa1-116">The following is the entire method described by the preceding procedure.</span></span>  
  
 [!code-csharp[C_CustomBinding#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#7)]  
