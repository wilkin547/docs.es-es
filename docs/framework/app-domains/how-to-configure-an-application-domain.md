---
title: Procedimiento para configurar un dominio de aplicación
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- application domains, configuring
- ApplicationBase property
ms.assetid: 07ea8438-7a34-49f0-a7e8-3d6ff7e4a482
ms.openlocfilehash: ca28984fa4a328e33d8d9bf79641cc451160f5ea
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73119914"
---
# <a name="how-to-configure-an-application-domain"></a><span data-ttu-id="e0577-102">Procedimiento para configurar un dominio de aplicación</span><span class="sxs-lookup"><span data-stu-id="e0577-102">How to: Configure an Application Domain</span></span>
<span data-ttu-id="e0577-103">Puede proporcionar información de configuración a Common Language Runtime para un nuevo dominio de aplicación mediante la clase <xref:System.AppDomainSetup>.</span><span class="sxs-lookup"><span data-stu-id="e0577-103">You can provide the common language runtime with configuration information for a new application domain using the <xref:System.AppDomainSetup> class.</span></span> <span data-ttu-id="e0577-104">Al crear sus propios dominios de aplicación, la propiedad más importante es <xref:System.AppDomainSetup.ApplicationBase%2A>.</span><span class="sxs-lookup"><span data-stu-id="e0577-104">When creating your own application domains, the most important property is <xref:System.AppDomainSetup.ApplicationBase%2A>.</span></span> <span data-ttu-id="e0577-105">Las otras propiedades **AppDomainSetup** las usan principalmente los hosts en tiempo de ejecución para configurar un dominio de aplicación determinado.</span><span class="sxs-lookup"><span data-stu-id="e0577-105">The other **AppDomainSetup** properties are used mainly by runtime hosts to configure a particular application domain.</span></span>  
  
 <span data-ttu-id="e0577-106">La propiedad **ApplicationBase** define el directorio raíz de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e0577-106">The **ApplicationBase** property defines the root directory of the application.</span></span> <span data-ttu-id="e0577-107">Cuando el tiempo de ejecución tiene que satisfacer una solicitud de tipo, busca el ensamblado que contiene el tipo en el directorio especificado por la propiedad **ApplicationBase**.</span><span class="sxs-lookup"><span data-stu-id="e0577-107">When the runtime needs to satisfy a type request, it probes for the assembly containing the type in the directory specified by the **ApplicationBase** property.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e0577-108">Un nuevo dominio de aplicación solo hereda la propiedad **ApplicationBase** del creador.</span><span class="sxs-lookup"><span data-stu-id="e0577-108">A new application domain inherits only the **ApplicationBase** property of the creator.</span></span>  
  
 <span data-ttu-id="e0577-109">En el ejemplo siguiente se crea una instancia de la clase **AppDomainSetup**, se usa esta clase para crear un dominio de aplicación, se escribe la información en la consola y, luego, se descarga el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="e0577-109">The following example creates an instance of the **AppDomainSetup** class, uses this class to create a new application domain, writes the information to console, and then unloads the application domain.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e0577-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e0577-110">Example</span></span>  
 [!code-cpp[ADApplicationBase#2](../../../samples/snippets/cpp/VS_Snippets_CLR/ADApplicationBase/CPP/source2.cpp#2)]
 [!code-csharp[ADApplicationBase#2](../../../samples/snippets/csharp/VS_Snippets_CLR/ADApplicationBase/CS/source2.cs#2)]
 [!code-vb[ADApplicationBase#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/ADApplicationBase/VB/source2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="e0577-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="e0577-111">See also</span></span>

- [<span data-ttu-id="e0577-112">Programar con dominios de aplicación</span><span class="sxs-lookup"><span data-stu-id="e0577-112">Programming with Application Domains</span></span>](application-domains.md#programming-with-application-domains)
- [<span data-ttu-id="e0577-113">Utilizar dominios de aplicación</span><span class="sxs-lookup"><span data-stu-id="e0577-113">Using Application Domains</span></span>](use.md)
