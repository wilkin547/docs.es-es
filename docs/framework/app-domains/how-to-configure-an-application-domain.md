---
title: Procedimiento para configurar un dominio de aplicación
description: Configure un dominio de aplicación en .NET. Puede proporcionar información de configuración a CLR para un nuevo dominio de aplicación mediante la clase AppDomainSetup.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- application domains, configuring
- ApplicationBase property
ms.assetid: 07ea8438-7a34-49f0-a7e8-3d6ff7e4a482
ms.openlocfilehash: bbda1f75da6b994c54cd71c56f16615a3758859b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96271517"
---
# <a name="how-to-configure-an-application-domain"></a><span data-ttu-id="d7897-104">Procedimiento para configurar un dominio de aplicación</span><span class="sxs-lookup"><span data-stu-id="d7897-104">How to: Configure an Application Domain</span></span>

<span data-ttu-id="d7897-105">Puede proporcionar información de configuración a Common Language Runtime para un nuevo dominio de aplicación mediante la clase <xref:System.AppDomainSetup>.</span><span class="sxs-lookup"><span data-stu-id="d7897-105">You can provide the common language runtime with configuration information for a new application domain using the <xref:System.AppDomainSetup> class.</span></span> <span data-ttu-id="d7897-106">Al crear sus propios dominios de aplicación, la propiedad más importante es <xref:System.AppDomainSetup.ApplicationBase%2A>.</span><span class="sxs-lookup"><span data-stu-id="d7897-106">When creating your own application domains, the most important property is <xref:System.AppDomainSetup.ApplicationBase%2A>.</span></span> <span data-ttu-id="d7897-107">Las otras propiedades **AppDomainSetup** las usan principalmente los hosts en tiempo de ejecución para configurar un dominio de aplicación determinado.</span><span class="sxs-lookup"><span data-stu-id="d7897-107">The other **AppDomainSetup** properties are used mainly by runtime hosts to configure a particular application domain.</span></span>  
  
 <span data-ttu-id="d7897-108">La propiedad **ApplicationBase** define el directorio raíz de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d7897-108">The **ApplicationBase** property defines the root directory of the application.</span></span> <span data-ttu-id="d7897-109">Cuando el tiempo de ejecución tiene que satisfacer una solicitud de tipo, busca el ensamblado que contiene el tipo en el directorio especificado por la propiedad **ApplicationBase**.</span><span class="sxs-lookup"><span data-stu-id="d7897-109">When the runtime needs to satisfy a type request, it probes for the assembly containing the type in the directory specified by the **ApplicationBase** property.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d7897-110">Un nuevo dominio de aplicación solo hereda la propiedad **ApplicationBase** del creador.</span><span class="sxs-lookup"><span data-stu-id="d7897-110">A new application domain inherits only the **ApplicationBase** property of the creator.</span></span>  
  
 <span data-ttu-id="d7897-111">En el ejemplo siguiente se crea una instancia de la clase **AppDomainSetup**, se usa esta clase para crear un dominio de aplicación, se escribe la información en la consola y, luego, se descarga el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="d7897-111">The following example creates an instance of the **AppDomainSetup** class, uses this class to create a new application domain, writes the information to console, and then unloads the application domain.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d7897-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d7897-112">Example</span></span>  

 [!code-cpp[ADApplicationBase#2](../../../samples/snippets/cpp/VS_Snippets_CLR/ADApplicationBase/CPP/source2.cpp#2)]
 [!code-csharp[ADApplicationBase#2](../../../samples/snippets/csharp/VS_Snippets_CLR/ADApplicationBase/CS/source2.cs#2)]
 [!code-vb[ADApplicationBase#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/ADApplicationBase/VB/source2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="d7897-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="d7897-113">See also</span></span>

- [<span data-ttu-id="d7897-114">Programar con dominios de aplicación</span><span class="sxs-lookup"><span data-stu-id="d7897-114">Programming with Application Domains</span></span>](application-domains.md#programming-with-application-domains)
- [<span data-ttu-id="d7897-115">Utilizar dominios de aplicación</span><span class="sxs-lookup"><span data-stu-id="d7897-115">Using Application Domains</span></span>](use.md)
