---
title: 'Cómo: Permitir las solicitudes de metadatos durante la autorización'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- allowing metadata requests while authorizing [WCF]
ms.assetid: 90cec34f-b619-452b-a056-8b1c0de49d05
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 6b0b331da49fca7be5106610e4b6f144220cc849
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="how-to-allow-metadata-requests-while-authorizing"></a><span data-ttu-id="e9dd1-102">Cómo: Permitir las solicitudes de metadatos durante la autorización</span><span class="sxs-lookup"><span data-stu-id="e9dd1-102">How To: Allow Metadata Requests While Authorizing</span></span>
<span data-ttu-id="e9dd1-103">Durante la autorización personalizada, puede ser necesario permitir una solicitud para que se procesen los metadatos.</span><span class="sxs-lookup"><span data-stu-id="e9dd1-103">During custom authorization, it may be necessary to allow a request for metadata to be processed.</span></span> <span data-ttu-id="e9dd1-104">El tema siguientes describe los pasos para validar este tipo de solicitud.</span><span class="sxs-lookup"><span data-stu-id="e9dd1-104">The following topic walks through the steps to validate such a request.</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="e9dd1-105"> [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] la autorización, consulte [autorización](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md).</span><span class="sxs-lookup"><span data-stu-id="e9dd1-105"> [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] authorization, see [Authorization](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md).</span></span>  
  
### <a name="to-allow-metadata-requests-during-authorization"></a><span data-ttu-id="e9dd1-106">Para permitir las solicitudes de los metadatos durante la autorización</span><span class="sxs-lookup"><span data-stu-id="e9dd1-106">To allow metadata requests during authorization</span></span>  
  
1.  <span data-ttu-id="e9dd1-107">Cree una extensión de la clase <xref:System.ServiceModel.ServiceAuthorizationManager>.</span><span class="sxs-lookup"><span data-stu-id="e9dd1-107">Create an extension of the <xref:System.ServiceModel.ServiceAuthorizationManager> class.</span></span>  
  
2.  <span data-ttu-id="e9dd1-108">Invalide el método <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A>.</span><span class="sxs-lookup"><span data-stu-id="e9dd1-108">Override the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A> method.</span></span> <span data-ttu-id="e9dd1-109">El método devuelve `true` o `false` dependiendo de si se permite la autorización.</span><span class="sxs-lookup"><span data-stu-id="e9dd1-109">The method returns `true` or `false` depending on whether authorization is allowed.</span></span> <span data-ttu-id="e9dd1-110">La información sobre el procedimiento actual se encuentra en <xref:System.ServiceModel.OperationContext> que se pasa como un parámetro al método.</span><span class="sxs-lookup"><span data-stu-id="e9dd1-110">Information about the current procedure is found in the <xref:System.ServiceModel.OperationContext> passed as a parameter to the method.</span></span>  
  
3.  <span data-ttu-id="e9dd1-111">En la invalidación, compruebe el nombre del contrato, espacio de nombres y la acción tal como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="e9dd1-111">In the override, check the contract name, namespace, and the action as shown in the following example.</span></span> <span data-ttu-id="e9dd1-112">Si las condiciones son válidas, devuelva `true.`</span><span class="sxs-lookup"><span data-stu-id="e9dd1-112">If the conditions are valid, then return `true.`</span></span>  
  
4.  <span data-ttu-id="e9dd1-113">Utilice el punto de extensibilidad para emplear la clase.</span><span class="sxs-lookup"><span data-stu-id="e9dd1-113">Use the extensibility point to employ the class.</span></span> <span data-ttu-id="e9dd1-114">Para obtener más información, consulte [Cómo: crear un administrador de autorización personalizado para un servicio](../../../../docs/framework/wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md).</span><span class="sxs-lookup"><span data-stu-id="e9dd1-114">For more information, see [How to: Create a Custom Authorization Manager for a Service](../../../../docs/framework/wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e9dd1-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e9dd1-115">Example</span></span>  
 <span data-ttu-id="e9dd1-116">En el siguiente ejemplo de código se muestra una invalidación del método <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A>.</span><span class="sxs-lookup"><span data-stu-id="e9dd1-116">The following example shows an override of the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A> method.</span></span>  
  
 [!code-csharp[C_HowtoCheckForMexRequestsInAuthorization#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtocheckformexrequestsinauthorization/cs/source.cs#1)]
 [!code-vb[C_HowtoCheckForMexRequestsInAuthorization#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtocheckformexrequestsinauthorization/vb/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="e9dd1-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="e9dd1-117">See Also</span></span>  
 <xref:System.ServiceModel.ServiceAuthorizationManager>  
 [<span data-ttu-id="e9dd1-118">Autorización</span><span class="sxs-lookup"><span data-stu-id="e9dd1-118">Authorization</span></span>](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
 [<span data-ttu-id="e9dd1-119">Administración de notificaciones y autorización con el modelo de identidad</span><span class="sxs-lookup"><span data-stu-id="e9dd1-119">Managing Claims and Authorization with the Identity Model</span></span>](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)
