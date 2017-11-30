---
title: "Recuperar información de instalación de un dominio de aplicación"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- AppDomainSetup object
- retrieving setup information
- application domains, retrieving setup information
ms.assetid: 5cdb12ae-1e37-4a62-8ec7-93d6dcc6e8d9
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ed6674580649e645ea3e647fa00682f2545255e9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="retrieving-setup-information-from-an-application-domain"></a><span data-ttu-id="43ea9-102">Recuperar información de instalación de un dominio de aplicación</span><span class="sxs-lookup"><span data-stu-id="43ea9-102">Retrieving Setup Information from an Application Domain</span></span>
<span data-ttu-id="43ea9-103">Cada instancia de un dominio de aplicación consta de propiedades e información <xref:System.AppDomainSetup>.</span><span class="sxs-lookup"><span data-stu-id="43ea9-103">Each instance of an application domain consists of both properties and <xref:System.AppDomainSetup> information.</span></span> <span data-ttu-id="43ea9-104">Puede recuperar información de instalación de un dominio de aplicación mediante la clase <xref:System.AppDomain?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="43ea9-104">You can retrieve setup information from an application domain using the <xref:System.AppDomain?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="43ea9-105">Esta clase proporciona varios miembros que recuperan información de configuración sobre un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="43ea9-105">This class provides several members that retrieve configuration information about an application domain.</span></span>  
  
 <span data-ttu-id="43ea9-106">También puede consultar el objeto **AppDomainSetup** del dominio de aplicación para la obtener la información de configuración pasada al dominio al crearse.</span><span class="sxs-lookup"><span data-stu-id="43ea9-106">You can also query the **AppDomainSetup** object for the application domain to obtain setup information that was passed to the domain when it was created.</span></span>  
  
 <span data-ttu-id="43ea9-107">En el ejemplo siguiente se crea un dominio de aplicación y, después, se imprimen varios valores de miembro en la consola.</span><span class="sxs-lookup"><span data-stu-id="43ea9-107">The following example creates a new application domain and then prints several member values to the console.</span></span>  
  
 [!code-cpp[AppDomain_Setup#2](../../../samples/snippets/cpp/VS_Snippets_CLR/AppDomain_Setup/CPP/source2.cpp#2)]
 [!code-csharp[AppDomain_Setup#2](../../../samples/snippets/csharp/VS_Snippets_CLR/AppDomain_Setup/CS/source2.cs#2)]
 [!code-vb[AppDomain_Setup#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AppDomain_Setup/VB/source2.vb#2)]  
  
 <span data-ttu-id="43ea9-108">En el ejemplo siguiente se establece y, después, se recupera la información de configuración de un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="43ea9-108">The following example sets, and then retrieves, setup information for an application domain.</span></span> <span data-ttu-id="43ea9-109">Observe que `AppDomain.SetupInformation.ApplicationBase` obtiene la información de configuración.</span><span class="sxs-lookup"><span data-stu-id="43ea9-109">Note that `AppDomain.SetupInformation.ApplicationBase` gets the configuration information.</span></span>  
  
 [!code-cpp[AppDomain_Setup#3](../../../samples/snippets/cpp/VS_Snippets_CLR/AppDomain_Setup/CPP/source3.cpp#3)]
 [!code-csharp[AppDomain_Setup#3](../../../samples/snippets/csharp/VS_Snippets_CLR/AppDomain_Setup/CS/source3.cs#3)]
 [!code-vb[AppDomain_Setup#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AppDomain_Setup/VB/source3.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="43ea9-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="43ea9-110">See Also</span></span>  
 [<span data-ttu-id="43ea9-111">Programar con dominios de aplicación</span><span class="sxs-lookup"><span data-stu-id="43ea9-111">Programming with Application Domains</span></span>](http://msdn.microsoft.com/en-us/bd36055b-56bd-43eb-b4d8-820c37172131)  
 [<span data-ttu-id="43ea9-112">Utilizar dominios de aplicación</span><span class="sxs-lookup"><span data-stu-id="43ea9-112">Using Application Domains</span></span>](../../../docs/framework/app-domains/use.md)
