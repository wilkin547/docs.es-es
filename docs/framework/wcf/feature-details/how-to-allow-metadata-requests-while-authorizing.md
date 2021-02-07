---
description: 'Más información acerca de cómo: permitir solicitudes de metadatos durante la autorización'
title: Cómo permitir las solicitudes de metadatos durante la autorización
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- allowing metadata requests while authorizing [WCF]
ms.assetid: 90cec34f-b619-452b-a056-8b1c0de49d05
ms.openlocfilehash: a9f5ab7db73aaa8a2a420a60c3172f1b1a738fb2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99742750"
---
# <a name="how-to-allow-metadata-requests-while-authorizing"></a><span data-ttu-id="041a5-103">Cómo permitir las solicitudes de metadatos durante la autorización</span><span class="sxs-lookup"><span data-stu-id="041a5-103">How To: Allow Metadata Requests While Authorizing</span></span>

<span data-ttu-id="041a5-104">Durante la autorización personalizada, puede ser necesario permitir una solicitud para que se procesen los metadatos.</span><span class="sxs-lookup"><span data-stu-id="041a5-104">During custom authorization, it may be necessary to allow a request for metadata to be processed.</span></span> <span data-ttu-id="041a5-105">El tema siguientes describe los pasos para validar este tipo de solicitud.</span><span class="sxs-lookup"><span data-stu-id="041a5-105">The following topic walks through the steps to validate such a request.</span></span>  
  
 <span data-ttu-id="041a5-106">Para obtener más información acerca de la autorización de Windows Communication Foundation (WCF), consulte [autorización](authorization-in-wcf.md).</span><span class="sxs-lookup"><span data-stu-id="041a5-106">For more information about Windows Communication Foundation (WCF) authorization, see [Authorization](authorization-in-wcf.md).</span></span>  
  
### <a name="to-allow-metadata-requests-during-authorization"></a><span data-ttu-id="041a5-107">Para permitir las solicitudes de los metadatos durante la autorización</span><span class="sxs-lookup"><span data-stu-id="041a5-107">To allow metadata requests during authorization</span></span>  
  
1. <span data-ttu-id="041a5-108">Cree una extensión de la clase <xref:System.ServiceModel.ServiceAuthorizationManager>.</span><span class="sxs-lookup"><span data-stu-id="041a5-108">Create an extension of the <xref:System.ServiceModel.ServiceAuthorizationManager> class.</span></span>  
  
2. <span data-ttu-id="041a5-109">Invalide el método <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A> .</span><span class="sxs-lookup"><span data-stu-id="041a5-109">Override the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A> method.</span></span> <span data-ttu-id="041a5-110">El método devuelve `true` o `false` dependiendo de si se permite la autorización.</span><span class="sxs-lookup"><span data-stu-id="041a5-110">The method returns `true` or `false` depending on whether authorization is allowed.</span></span> <span data-ttu-id="041a5-111">La información sobre el procedimiento actual se encuentra en <xref:System.ServiceModel.OperationContext> que se pasa como un parámetro al método.</span><span class="sxs-lookup"><span data-stu-id="041a5-111">Information about the current procedure is found in the <xref:System.ServiceModel.OperationContext> passed as a parameter to the method.</span></span>  
  
3. <span data-ttu-id="041a5-112">En la invalidación, compruebe el nombre del contrato, espacio de nombres y la acción tal como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="041a5-112">In the override, check the contract name, namespace, and the action as shown in the following example.</span></span> <span data-ttu-id="041a5-113">Si las condiciones son válidas, devuelva `true.`</span><span class="sxs-lookup"><span data-stu-id="041a5-113">If the conditions are valid, then return `true.`</span></span>  
  
4. <span data-ttu-id="041a5-114">Utilice el punto de extensibilidad para emplear la clase.</span><span class="sxs-lookup"><span data-stu-id="041a5-114">Use the extensibility point to employ the class.</span></span> <span data-ttu-id="041a5-115">Para obtener más información, consulte [Cómo: crear un administrador de autorización personalizado para un servicio](../extending/how-to-create-a-custom-authorization-manager-for-a-service.md).</span><span class="sxs-lookup"><span data-stu-id="041a5-115">For more information, see [How to: Create a Custom Authorization Manager for a Service](../extending/how-to-create-a-custom-authorization-manager-for-a-service.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="041a5-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="041a5-116">Example</span></span>  

 <span data-ttu-id="041a5-117">En el siguiente ejemplo de código se muestra una invalidación del método <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A>.</span><span class="sxs-lookup"><span data-stu-id="041a5-117">The following example shows an override of the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A> method.</span></span>  
  
 [!code-csharp[C_HowtoCheckForMexRequestsInAuthorization#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtocheckformexrequestsinauthorization/cs/source.cs#1)]
 [!code-vb[C_HowtoCheckForMexRequestsInAuthorization#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtocheckformexrequestsinauthorization/vb/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="041a5-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="041a5-118">See also</span></span>

- <xref:System.ServiceModel.ServiceAuthorizationManager>
- [<span data-ttu-id="041a5-119">Autorización</span><span class="sxs-lookup"><span data-stu-id="041a5-119">Authorization</span></span>](authorization-in-wcf.md)
- [<span data-ttu-id="041a5-120">Administración de notificaciones y autorización con el modelo de identidad</span><span class="sxs-lookup"><span data-stu-id="041a5-120">Managing Claims and Authorization with the Identity Model</span></span>](managing-claims-and-authorization-with-the-identity-model.md)
