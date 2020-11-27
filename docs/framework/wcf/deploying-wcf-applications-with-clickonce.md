---
title: Implementación de aplicaciones WCF con ClickOnce
ms.date: 03/30/2017
ms.assetid: 1a11feee-2a47-4d3e-a28a-ad69d5ff93e0
ms.openlocfilehash: ad4c603d07885aa16640b71d43038746d3702b05
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96260863"
---
# <a name="deploying-wcf-applications-with-clickonce"></a><span data-ttu-id="3cea2-102">Implementación de aplicaciones WCF con ClickOnce</span><span class="sxs-lookup"><span data-stu-id="3cea2-102">Deploying WCF Applications with ClickOnce</span></span>

<span data-ttu-id="3cea2-103">Las aplicaciones cliente que usan Windows Communication Foundation (WCF) se pueden implementar mediante la tecnología ClickOnce.</span><span class="sxs-lookup"><span data-stu-id="3cea2-103">Client applications using Windows Communication Foundation (WCF) may be deployed using ClickOnce technology.</span></span> <span data-ttu-id="3cea2-104">Esta tecnología les permite sacar partido de las protecciones de seguridad en tiempo de ejecución proporcionadas por seguridad de acceso del código (CAS), siempre que estén firmadas digitalmente con un certificado de confianza.</span><span class="sxs-lookup"><span data-stu-id="3cea2-104">This technology allows them to take advantage of the runtime security protections provided by Code Access Security, provided that they are digitally signed with a trusted certificate.</span></span> <span data-ttu-id="3cea2-105">El certificado utilizado para firmar la aplicación ClickOnce debe residir en el almacén del Editor de confianza y la directiva de seguridad local en el equipo cliente se debe configurar para conceder los permisos de plena confianza a las aplicaciones firmadas con el certificado del editor.</span><span class="sxs-lookup"><span data-stu-id="3cea2-105">The certificate used to sign the ClickOnce application must reside in the Trusted Publisher store, and the local security policy on the client machine must be configured to grant Full Trust permissions to applications signed with the publisher's certificate.</span></span>  
  
 <span data-ttu-id="3cea2-106">Para obtener información sobre la configuración de aplicaciones ClickOnce y editores de confianza, vea [configurar editores de confianza de ClickOnce](/previous-versions/dotnet/articles/ms996418(v=msdn.10)).</span><span class="sxs-lookup"><span data-stu-id="3cea2-106">For information on configuring ClickOnce applications and trusted publishers, see [Configuring ClickOnce Trusted Publishers](/previous-versions/dotnet/articles/ms996418(v=msdn.10)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3cea2-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="3cea2-107">See also</span></span>

- [<span data-ttu-id="3cea2-108">Introducción a la implementación de aplicaciones de confianza</span><span class="sxs-lookup"><span data-stu-id="3cea2-108">Trusted Application Deployment Overview</span></span>](/visualstudio/deployment/trusted-application-deployment-overview)
- <span data-ttu-id="3cea2-109">[Implementación de ClickOnce para aplicaciones de Windows Forms](/previous-versions/visualstudio/visual-studio-2008/wh45kb66(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="3cea2-109">[ClickOnce Deployment for Windows Forms Applications](/previous-versions/visualstudio/visual-studio-2008/wh45kb66(v=vs.90))</span></span>
