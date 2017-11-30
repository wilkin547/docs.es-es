---
title: "Cómo: Crear un dominio de aplicación"
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
helpviewer_keywords: application domains, creating
ms.assetid: ba1fa43e-49f5-47d9-bd7f-3024af16f4ba
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6f8d791a7aa673c25104e5dddf018d4b167563ae
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-an-application-domain"></a><span data-ttu-id="4eccc-102">Cómo: Crear un dominio de aplicación</span><span class="sxs-lookup"><span data-stu-id="4eccc-102">How to: Create an Application Domain</span></span>
<span data-ttu-id="4eccc-103">Un host de Common Language Runtime habitual crea dominios de aplicación automáticamente cuando son necesarios,</span><span class="sxs-lookup"><span data-stu-id="4eccc-103">A common language runtime host creates application domains automatically when they are needed.</span></span> <span data-ttu-id="4eccc-104">pero puede crear sus propios dominios de aplicación y cargar en ellos los ensamblados que desee administrar personalmente.</span><span class="sxs-lookup"><span data-stu-id="4eccc-104">However, you can create your own application domains and load into them those assemblies that you want to manage personally.</span></span> <span data-ttu-id="4eccc-105">También puede crear dominios de aplicación desde los que puede ejecutar el código.</span><span class="sxs-lookup"><span data-stu-id="4eccc-105">You can also create application domains from which you execute code.</span></span>  
  
 <span data-ttu-id="4eccc-106">Cree un dominio de aplicación mediante uno de los métodos **CreateDomain** sobrecargados en la clase <xref:System.AppDomain?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4eccc-106">You create a new application domain using one of the overloaded **CreateDomain** methods in the <xref:System.AppDomain?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="4eccc-107">Puede asignar un nombre al dominio de aplicación y hacer referencia a él con ese nombre.</span><span class="sxs-lookup"><span data-stu-id="4eccc-107">You can give the application domain a name and reference it by that name.</span></span>  
  
 <span data-ttu-id="4eccc-108">En el siguiente ejemplo se crea un dominio de aplicación, se le asigna el nombre `MyDomain` y, luego, se imprime el nombre del dominio host y el dominio de aplicación secundario recién creado en la consola.</span><span class="sxs-lookup"><span data-stu-id="4eccc-108">The following example creates a new application domain, assigns it the name `MyDomain`, and then prints the name of the host domain and the newly created child application domain to the console.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4eccc-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4eccc-109">Example</span></span>  
 [!code-cpp[ADCreateDomain#2](../../../samples/snippets/cpp/VS_Snippets_CLR/ADCreateDomain/CPP/source2.cpp#2)]
 [!code-csharp[ADCreateDomain#2](../../../samples/snippets/csharp/VS_Snippets_CLR/ADCreateDomain/CS/source2.cs#2)]
 [!code-vb[ADCreateDomain#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/ADCreateDomain/VB/source2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="4eccc-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="4eccc-110">See Also</span></span>  
 [<span data-ttu-id="4eccc-111">Programar con dominios de aplicación</span><span class="sxs-lookup"><span data-stu-id="4eccc-111">Programming with Application Domains</span></span>](http://msdn.microsoft.com/en-us/bd36055b-56bd-43eb-b4d8-820c37172131)  
 [<span data-ttu-id="4eccc-112">Utilizar dominios de aplicación</span><span class="sxs-lookup"><span data-stu-id="4eccc-112">Using Application Domains</span></span>](../../../docs/framework/app-domains/use.md)
