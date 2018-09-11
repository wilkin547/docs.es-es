---
title: Implementación de aplicaciones WCF con ClickOnce
ms.date: 03/30/2017
ms.assetid: 1a11feee-2a47-4d3e-a28a-ad69d5ff93e0
ms.openlocfilehash: d733c6f523393737418c6394707c1d4e6e9c1710
ms.sourcegitcommit: 8c2ece71e54f46aef9a2153540d0bda7e74b19a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/11/2018
ms.locfileid: "44365022"
---
# <a name="deploying-wcf-applications-with-clickonce"></a><span data-ttu-id="fc505-102">Implementación de aplicaciones WCF con ClickOnce</span><span class="sxs-lookup"><span data-stu-id="fc505-102">Deploying WCF Applications with ClickOnce</span></span>
<span data-ttu-id="fc505-103">Las aplicaciones cliente mediante Windows Communication Foundation (WCF) se pueden implementar mediante la tecnología ClickOnce.</span><span class="sxs-lookup"><span data-stu-id="fc505-103">Client applications using Windows Communication Foundation (WCF) may be deployed using ClickOnce technology.</span></span> <span data-ttu-id="fc505-104">Esta tecnología les permite sacar partido de las protecciones de seguridad en tiempo de ejecución proporcionadas por seguridad de acceso del código (CAS), siempre que estén firmadas digitalmente con un certificado de confianza.</span><span class="sxs-lookup"><span data-stu-id="fc505-104">This technology allows them to take advantage of the runtime security protections provided by Code Access Security, provided that they are digitally signed with a trusted certificate.</span></span> <span data-ttu-id="fc505-105">El certificado utilizado para firmar la aplicación ClickOnce debe residir en el almacén del Editor de confianza y la directiva de seguridad local en el equipo cliente se debe configurar para conceder los permisos de plena confianza a las aplicaciones firmadas con el certificado del editor.</span><span class="sxs-lookup"><span data-stu-id="fc505-105">The certificate used to sign the ClickOnce application must reside in the Trusted Publisher store, and the local security policy on the client machine must be configured to grant Full Trust permissions to applications signed with the publisher's certificate.</span></span>  
  
 <span data-ttu-id="fc505-106">Para obtener información sobre cómo configurar las aplicaciones ClickOnce y editores de confianza, consulte [Configuring ClickOnce Trusted Publishers](https://go.microsoft.com/fwlink/?LinkId=94774).</span><span class="sxs-lookup"><span data-stu-id="fc505-106">For information on configuring ClickOnce applications and trusted publishers, see [Configuring ClickOnce Trusted Publishers](https://go.microsoft.com/fwlink/?LinkId=94774).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc505-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="fc505-107">See Also</span></span>  
 [<span data-ttu-id="fc505-108">Introducción a la implementación de aplicaciones de confianza</span><span class="sxs-lookup"><span data-stu-id="fc505-108">Trusted Application Deployment Overview</span></span>](https://go.microsoft.com/fwlink/?LinkId=94775)  
 [<span data-ttu-id="fc505-109">Las aplicaciones de implementación de ClickOnce para Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fc505-109">ClickOnce Deployment for Windows Forms Applications</span></span>](https://go.microsoft.com/fwlink/?LinkId=94776)
