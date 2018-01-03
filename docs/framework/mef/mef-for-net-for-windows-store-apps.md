---
title: MEF para .NET para aplicaciones de la tienda de Windows
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7667770e-d163-4ad6-a303-085cf73db2f2
caps.latest.revision: "3"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8436bff3b6ca1061621a67eb45bdc8aedea33f2c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="mef-for-net-for-windows-store-apps"></a><span data-ttu-id="e3acd-102">MEF para .NET para aplicaciones de la tienda de Windows</span><span class="sxs-lookup"><span data-stu-id="e3acd-102">MEF for .NET for Windows Store Apps</span></span>
<span data-ttu-id="e3acd-103"><xref:System.Composition?displayProperty=nameWithType>y sus espacios de nombres secundarios contienen tipos para desarrollar extensibles [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] aplicaciones con Managed Extensibility Framework (MEF).</span><span class="sxs-lookup"><span data-stu-id="e3acd-103"><xref:System.Composition?displayProperty=nameWithType> and its child namespaces contain types for developing extensible [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps with Managed Extensibility Framework (MEF).</span></span> <span data-ttu-id="e3acd-104">Estos espacios de nombres forman parte de la [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] subconjunto para el [!INCLUDE[win8](../../../includes/win8-md.md)] sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="e3acd-104">These namespaces are part of the [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] subset for the [!INCLUDE[win8](../../../includes/win8-md.md)] operating system.</span></span>  
  
 <span data-ttu-id="e3acd-105">Estos espacios de nombres no forman parte de la biblioteca de clases básica distribuida con .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e3acd-105">These namespaces are not part of the core class library distributed with the .NET Framework.</span></span> <span data-ttu-id="e3acd-106">Para instalar estos espacios de nombres, abra el proyecto en [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], elija **administrar paquetes de NuGet** desde el **proyecto** menú y busque en línea el paquete Microsoft.Composition.</span><span class="sxs-lookup"><span data-stu-id="e3acd-106">To install these namespaces, open your project in [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], choose **Manage NuGet Packages** from the **Project** menu, and search online for the Microsoft.Composition package.</span></span>  
  
-   <span data-ttu-id="e3acd-107"><xref:System.Composition?displayProperty=nameWithType>Proporciona clases que constituyen el núcleo de MEF para [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="e3acd-107"><xref:System.Composition?displayProperty=nameWithType> provides classes that constitute the core MEF for [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps.</span></span>  
  
-   <span data-ttu-id="e3acd-108"><xref:System.Composition.Convention?displayProperty=nameWithType>Proporciona tipos que admiten el uso de MEF con un modelo de configuración basada en convenciones.</span><span class="sxs-lookup"><span data-stu-id="e3acd-108"><xref:System.Composition.Convention?displayProperty=nameWithType> provides types that support using MEF with a convention-based configuration model.</span></span>  
  
-   <span data-ttu-id="e3acd-109"><xref:System.Composition.Hosting?displayProperty=nameWithType>Proporciona los tipos MEF que son útiles para los desarrolladores de aplicaciones de host.</span><span class="sxs-lookup"><span data-stu-id="e3acd-109"><xref:System.Composition.Hosting?displayProperty=nameWithType> provides MEF types that are useful to developers of host applications.</span></span>  
  
-   <span data-ttu-id="e3acd-110"><xref:System.Composition.Hosting.Core?displayProperty=nameWithType>Proporciona los tipos MEF utilizados internamente por el motor de composición.</span><span class="sxs-lookup"><span data-stu-id="e3acd-110"><xref:System.Composition.Hosting.Core?displayProperty=nameWithType> provides MEF types used internally by the composition engine.</span></span>  
  
 <span data-ttu-id="e3acd-111">Para obtener más información acerca de [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] y ver una lista de espacios de nombres y tipos que contiene, [información general de aplicaciones de .NET para la tienda Windows](http://go.microsoft.com/fwlink/p/?LinkID=238312) en el centro de desarrollo de Windows.</span><span class="sxs-lookup"><span data-stu-id="e3acd-111">For more information about [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] and a list of namespaces and types that it contains, see [.NET for Windows Store apps overview](http://go.microsoft.com/fwlink/p/?LinkID=238312) in the Windows Dev Center.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3acd-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="e3acd-112">See Also</span></span>  
 [<span data-ttu-id="e3acd-113">Información general de aplicaciones de .NET para la tienda Windows</span><span class="sxs-lookup"><span data-stu-id="e3acd-113">.NET for Windows Store apps overview</span></span>](http://go.microsoft.com/fwlink/p/?LinkID=238312)  
 [<span data-ttu-id="e3acd-114">.NET para aplicaciones de la Tienda Windows: API admitidas</span><span class="sxs-lookup"><span data-stu-id="e3acd-114">.NET for Windows Store apps – supported APIs</span></span>](http://go.microsoft.com/fwlink/p/?LinkID=247912)  
 [<span data-ttu-id="e3acd-115">Managed Extensibility Framework (MEF)</span><span class="sxs-lookup"><span data-stu-id="e3acd-115">Managed Extensibility Framework (MEF)</span></span>](../../../docs/framework/mef/index.md)
