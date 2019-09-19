---
title: Procedimiento para crear un dominio de aplicación
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- application domains, creating
ms.assetid: ba1fa43e-49f5-47d9-bd7f-3024af16f4ba
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7f42f85adf3e9b0874df6c0360bea25b07facc0d
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053157"
---
# <a name="how-to-create-an-application-domain"></a><span data-ttu-id="47044-102">Procedimiento para crear un dominio de aplicación</span><span class="sxs-lookup"><span data-stu-id="47044-102">How to: Create an Application Domain</span></span>
<span data-ttu-id="47044-103">Un host de Common Language Runtime habitual crea dominios de aplicación automáticamente cuando son necesarios,</span><span class="sxs-lookup"><span data-stu-id="47044-103">A common language runtime host creates application domains automatically when they are needed.</span></span> <span data-ttu-id="47044-104">pero puede crear sus propios dominios de aplicación y cargar en ellos los ensamblados que desee administrar personalmente.</span><span class="sxs-lookup"><span data-stu-id="47044-104">However, you can create your own application domains and load into them those assemblies that you want to manage personally.</span></span> <span data-ttu-id="47044-105">También puede crear dominios de aplicación desde los que puede ejecutar el código.</span><span class="sxs-lookup"><span data-stu-id="47044-105">You can also create application domains from which you execute code.</span></span>  
  
 <span data-ttu-id="47044-106">Cree un dominio de aplicación mediante uno de los métodos **CreateDomain** sobrecargados en la clase <xref:System.AppDomain?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="47044-106">You create a new application domain using one of the overloaded **CreateDomain** methods in the <xref:System.AppDomain?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="47044-107">Puede asignar un nombre al dominio de aplicación y hacer referencia a él con ese nombre.</span><span class="sxs-lookup"><span data-stu-id="47044-107">You can give the application domain a name and reference it by that name.</span></span>  
  
 <span data-ttu-id="47044-108">En el siguiente ejemplo se crea un dominio de aplicación, se le asigna el nombre `MyDomain` y, luego, se imprime el nombre del dominio host y el dominio de aplicación secundario recién creado en la consola.</span><span class="sxs-lookup"><span data-stu-id="47044-108">The following example creates a new application domain, assigns it the name `MyDomain`, and then prints the name of the host domain and the newly created child application domain to the console.</span></span>  
  
## <a name="example"></a><span data-ttu-id="47044-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="47044-109">Example</span></span>  
 [!code-cpp[ADCreateDomain#2](../../../samples/snippets/cpp/VS_Snippets_CLR/ADCreateDomain/CPP/source2.cpp#2)]
 [!code-csharp[ADCreateDomain#2](../../../samples/snippets/csharp/VS_Snippets_CLR/ADCreateDomain/CS/source2.cs#2)]
 [!code-vb[ADCreateDomain#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/ADCreateDomain/VB/source2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="47044-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="47044-110">See also</span></span>

- [<span data-ttu-id="47044-111">Programar con dominios de aplicación</span><span class="sxs-lookup"><span data-stu-id="47044-111">Programming with Application Domains</span></span>](application-domains.md#programming-with-application-domains)
- [<span data-ttu-id="47044-112">Utilizar dominios de aplicación</span><span class="sxs-lookup"><span data-stu-id="47044-112">Using Application Domains</span></span>](use.md)
