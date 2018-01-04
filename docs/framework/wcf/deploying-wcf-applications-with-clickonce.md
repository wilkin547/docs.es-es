---
title: "Implementación de aplicaciones WCF con ClickOnce"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1a11feee-2a47-4d3e-a28a-ad69d5ff93e0
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0e87e01c39c5f50ff3f4d4e9479a68e19cceb90f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="deploying-wcf-applications-with-clickonce"></a><span data-ttu-id="dd224-102">Implementación de aplicaciones WCF con ClickOnce</span><span class="sxs-lookup"><span data-stu-id="dd224-102">Deploying WCF Applications with ClickOnce</span></span>
<span data-ttu-id="dd224-103">Las aplicaciones cliente que usen [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] se pueden implementar utilizando la tecnología de ClickOnce.</span><span class="sxs-lookup"><span data-stu-id="dd224-103">Client applications using [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] may be deployed using ClickOnce technology.</span></span> <span data-ttu-id="dd224-104">Esta tecnología les permite sacar partido de las protecciones de seguridad en tiempo de ejecución proporcionadas por seguridad de acceso del código (CAS), siempre que estén firmadas digitalmente con un certificado de confianza.</span><span class="sxs-lookup"><span data-stu-id="dd224-104">This technology allows them to take advantage of the runtime security protections provided by Code Access Security, provided that they are digitally signed with a trusted certificate.</span></span> <span data-ttu-id="dd224-105">El certificado utilizado para firmar la aplicación ClickOnce debe residir en el almacén del Editor de confianza y la directiva de seguridad local en el equipo cliente se debe configurar para conceder los permisos de plena confianza a las aplicaciones firmadas con el certificado del editor.</span><span class="sxs-lookup"><span data-stu-id="dd224-105">The certificate used to sign the ClickOnce application must reside in the Trusted Publisher store, and the local security policy on the client machine must be configured to grant Full Trust permissions to applications signed with the publisher's certificate.</span></span>  
  
 <span data-ttu-id="dd224-106">Para obtener información acerca de cómo configurar las aplicaciones ClickOnce y editores de confianza, consulte [Configurar editores de confianza de ClickOnce](http://go.microsoft.com/fwlink/?LinkId=94774).</span><span class="sxs-lookup"><span data-stu-id="dd224-106">For information on configuring ClickOnce applications and trusted publishers, see [Configuring ClickOnce Trusted Publishers](http://go.microsoft.com/fwlink/?LinkId=94774).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd224-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="dd224-107">See Also</span></span>  
 [<span data-ttu-id="dd224-108">Introducción a la implementación de aplicaciones de confianza</span><span class="sxs-lookup"><span data-stu-id="dd224-108">Trusted Application Deployment Overview</span></span>](http://go.microsoft.com/fwlink/?LinkId=94775)  
 [<span data-ttu-id="dd224-109">Las aplicaciones de implementación de ClickOnce para Windows Forms</span><span class="sxs-lookup"><span data-stu-id="dd224-109">ClickOnce Deployment for Windows Forms Applications</span></span>](http://go.microsoft.com/fwlink/?LinkId=94776)
