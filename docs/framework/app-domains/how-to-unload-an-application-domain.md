---
title: 'Cómo: Descargar un dominio de aplicación'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Unload method
- application domains, unloading
- unloading application domains
ms.assetid: f356116d-e415-4f7c-a332-6e6a60227192
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0a9e5ee865b5e0ac9ec0214a4a0b5194bbcd9f30
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32742093"
---
# <a name="how-to-unload-an-application-domain"></a><span data-ttu-id="cca79-102">Cómo: Descargar un dominio de aplicación</span><span class="sxs-lookup"><span data-stu-id="cca79-102">How to: Unload an Application Domain</span></span>
<span data-ttu-id="cca79-103">Cuando haya terminado de usar un dominio de aplicación, descárguelo con el método <xref:System.AppDomain.Unload%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="cca79-103">When you have finished using an application domain, unload it using the <xref:System.AppDomain.Unload%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="cca79-104">El método **Unload** cierra discretamente el dominio de aplicación especificado.</span><span class="sxs-lookup"><span data-stu-id="cca79-104">The **Unload** method gracefully shuts down the specified application domain.</span></span> <span data-ttu-id="cca79-105">Durante el proceso de descarga, ningún subproceso nuevo puede obtener acceso al dominio de aplicación. Además, se liberan todas las estructuras de datos específicas del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="cca79-105">During the unloading process, no new threads can access the application domain, and all application domain–specific data structures are freed.</span></span>  
  
 <span data-ttu-id="cca79-106">Los ensamblados cargados en el dominio de aplicación se quitan y dejan de estar disponibles.</span><span class="sxs-lookup"><span data-stu-id="cca79-106">Assemblies loaded into the application domain are removed and are no longer available.</span></span> <span data-ttu-id="cca79-107">Si un ensamblado del dominio de aplicación es neutral respecto al dominio, sus datos permanecen en la memoria hasta que se cierra todo el proceso.</span><span class="sxs-lookup"><span data-stu-id="cca79-107">If an assembly in the application domain is domain-neutral, data for the assembly remains in memory until the entire process is shut down.</span></span> <span data-ttu-id="cca79-108">No existe ningún mecanismo para descargar un ensamblado neutral con respecto al dominio, aparte de cerrar todo el proceso.</span><span class="sxs-lookup"><span data-stu-id="cca79-108">There is no mechanism to unload a domain-neutral assembly other than shutting down the entire process.</span></span> <span data-ttu-id="cca79-109">Existen situaciones en las que la solicitud para descargar un dominio de aplicación no funciona y genera como resultado una <xref:System.CannotUnloadAppDomainException>.</span><span class="sxs-lookup"><span data-stu-id="cca79-109">There are situations where the request to unload an application domain does not work and results in a <xref:System.CannotUnloadAppDomainException>.</span></span>  
  
 <span data-ttu-id="cca79-110">En el ejemplo siguiente se crea un nuevo dominio de aplicación denominado `MyDomain`, se imprime cierta información en la consola y, a continuación, se descarga el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="cca79-110">The following example creates a new application domain called `MyDomain`, prints some information to the console, and then unloads the application domain.</span></span> <span data-ttu-id="cca79-111">Tenga en cuenta que, después, el código intenta imprimir en la consola el nombre descriptivo del dominio de aplicación descargado.</span><span class="sxs-lookup"><span data-stu-id="cca79-111">Note that the code then attempts to print the friendly name of the unloaded application domain to the console.</span></span> <span data-ttu-id="cca79-112">Esta acción genera una excepción que controlan las instrucciones try/catch al final del programa.</span><span class="sxs-lookup"><span data-stu-id="cca79-112">This action generates an exception that is handled by the try/catch statements at the end of the program.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cca79-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cca79-113">Example</span></span>  
 [!code-cpp[System.AppDomain.Load#3](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.appdomain.load/cpp/source3.cpp#3)]
 [!code-csharp[System.AppDomain.Load#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.load/cs/source3.cs#3)]
 [!code-vb[System.AppDomain.Load#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.load/vb/source3.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="cca79-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="cca79-114">See Also</span></span>  
 [<span data-ttu-id="cca79-115">Programar con dominios de aplicación</span><span class="sxs-lookup"><span data-stu-id="cca79-115">Programming with Application Domains</span></span>](application-domains.md#programming-with-application-domains)  
 [<span data-ttu-id="cca79-116">Crear un dominio de aplicación</span><span class="sxs-lookup"><span data-stu-id="cca79-116">How to: Create an Application Domain</span></span>](../../../docs/framework/app-domains/how-to-create-an-application-domain.md)  
 [<span data-ttu-id="cca79-117">Utilizar dominios de aplicación</span><span class="sxs-lookup"><span data-stu-id="cca79-117">Using Application Domains</span></span>](../../../docs/framework/app-domains/use.md)
