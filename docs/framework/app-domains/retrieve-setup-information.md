---
title: Recuperar información de instalación de un dominio de aplicación
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- AppDomainSetup object
- retrieving setup information
- application domains, retrieving setup information
ms.assetid: 5cdb12ae-1e37-4a62-8ec7-93d6dcc6e8d9
ms.openlocfilehash: 4d06a8a3ccfa35af283323478ee44a7da63d896d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73119743"
---
# <a name="retrieving-setup-information-from-an-application-domain"></a><span data-ttu-id="addd4-102">Recuperar información de instalación de un dominio de aplicación</span><span class="sxs-lookup"><span data-stu-id="addd4-102">Retrieving Setup Information from an Application Domain</span></span>
<span data-ttu-id="addd4-103">Cada instancia de un dominio de aplicación consta de propiedades e información <xref:System.AppDomainSetup>.</span><span class="sxs-lookup"><span data-stu-id="addd4-103">Each instance of an application domain consists of both properties and <xref:System.AppDomainSetup> information.</span></span> <span data-ttu-id="addd4-104">Puede recuperar información de instalación de un dominio de aplicación mediante la clase <xref:System.AppDomain?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="addd4-104">You can retrieve setup information from an application domain using the <xref:System.AppDomain?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="addd4-105">Esta clase proporciona varios miembros que recuperan información de configuración sobre un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="addd4-105">This class provides several members that retrieve configuration information about an application domain.</span></span>  
  
 <span data-ttu-id="addd4-106">También puede consultar el objeto **AppDomainSetup** del dominio de aplicación para la obtener la información de configuración pasada al dominio al crearse.</span><span class="sxs-lookup"><span data-stu-id="addd4-106">You can also query the **AppDomainSetup** object for the application domain to obtain setup information that was passed to the domain when it was created.</span></span>  
  
 <span data-ttu-id="addd4-107">En el ejemplo siguiente se crea un dominio de aplicación y, después, se imprimen varios valores de miembro en la consola.</span><span class="sxs-lookup"><span data-stu-id="addd4-107">The following example creates a new application domain and then prints several member values to the console.</span></span>  
  
 [!code-cpp[AppDomain_Setup#2](../../../samples/snippets/cpp/VS_Snippets_CLR/AppDomain_Setup/CPP/source2.cpp#2)]
 [!code-csharp[AppDomain_Setup#2](../../../samples/snippets/csharp/VS_Snippets_CLR/AppDomain_Setup/CS/source2.cs#2)]
 [!code-vb[AppDomain_Setup#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AppDomain_Setup/VB/source2.vb#2)]  
  
 <span data-ttu-id="addd4-108">En el ejemplo siguiente se establece y, después, se recupera la información de configuración de un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="addd4-108">The following example sets, and then retrieves, setup information for an application domain.</span></span> <span data-ttu-id="addd4-109">Observe que `AppDomain.SetupInformation.ApplicationBase` obtiene la información de configuración.</span><span class="sxs-lookup"><span data-stu-id="addd4-109">Note that `AppDomain.SetupInformation.ApplicationBase` gets the configuration information.</span></span>  
  
 [!code-cpp[AppDomain_Setup#3](../../../samples/snippets/cpp/VS_Snippets_CLR/AppDomain_Setup/CPP/source3.cpp#3)]
 [!code-csharp[AppDomain_Setup#3](../../../samples/snippets/csharp/VS_Snippets_CLR/AppDomain_Setup/CS/source3.cs#3)]
 [!code-vb[AppDomain_Setup#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AppDomain_Setup/VB/source3.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="addd4-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="addd4-110">See also</span></span>

- [<span data-ttu-id="addd4-111">Programar con dominios de aplicación</span><span class="sxs-lookup"><span data-stu-id="addd4-111">Programming with Application Domains</span></span>](application-domains.md#programming-with-application-domains)
- [<span data-ttu-id="addd4-112">Utilizar dominios de aplicación</span><span class="sxs-lookup"><span data-stu-id="addd4-112">Using Application Domains</span></span>](use.md)
