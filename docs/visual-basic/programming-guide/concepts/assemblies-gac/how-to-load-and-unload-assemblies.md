---
title: "Cómo: cargar y descargar ensamblados (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bbc84236-04b6-4c1b-9672-52773f65a5dc
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: fd52a1094dba16c7e1bcba5bface9e13747cd4f6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-load-and-unload-assemblies-visual-basic"></a><span data-ttu-id="9c7df-102">Cómo: cargar y descargar ensamblados (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9c7df-102">How to: Load and Unload Assemblies (Visual Basic)</span></span>
<span data-ttu-id="9c7df-103">Los ensamblados a los que hace referencia el programa se cargarán automáticamente en tiempo de compilación, pero también es posible cargar ensamblados específicos en el dominio de aplicación actual en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="9c7df-103">The assemblies referenced by your program will automatically be loaded at build time, but it is also possible to load specific assemblies into the current application domain at runtime.</span></span> <span data-ttu-id="9c7df-104">Para obtener más información, vea [Cómo: Cargar ensamblados en un dominio de aplicación](../../../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md).</span><span class="sxs-lookup"><span data-stu-id="9c7df-104">For more information, see [How to: Load Assemblies into an Application Domain](../../../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md).</span></span>  
  
 <span data-ttu-id="9c7df-105">No existe ninguna forma de descargar un ensamblado individual sin descargar todos los dominios de aplicación que lo contienen.</span><span class="sxs-lookup"><span data-stu-id="9c7df-105">There is no way to unload an individual assembly without unloading all of the application domains that contain it.</span></span> <span data-ttu-id="9c7df-106">Aunque el ensamblado esté fuera de ámbito, el archivo de ensamblado actual permanecerá cargado hasta que se descarguen todos los dominios de aplicación que lo contienen.</span><span class="sxs-lookup"><span data-stu-id="9c7df-106">Even if the assembly goes out of scope, the actual assembly file will remain loaded until all application domains that contain it are unloaded.</span></span>  
  
 <span data-ttu-id="9c7df-107">Si desea descargar algunos ensamblados pero no otros, considere la posibilidad de crear un nuevo dominio de aplicación, ejecutar el código en el dominio y, a continuación, descargar ese dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="9c7df-107">If you want to unload some assemblies but not others, consider creating a new application domain, executing the code inside that domain, and then unloading that application domain.</span></span> <span data-ttu-id="9c7df-108">Para obtener más información, vea [Cómo: Descargar un dominio de aplicación](../../../../framework/app-domains/how-to-unload-an-application-domain.md).</span><span class="sxs-lookup"><span data-stu-id="9c7df-108">For more information, see [How to: Unload an Application Domain](../../../../framework/app-domains/how-to-unload-an-application-domain.md).</span></span>  
  
### <a name="to-load-an-assembly-into-an-application-domain"></a><span data-ttu-id="9c7df-109">Para cargar un ensamblado en un dominio de aplicación</span><span class="sxs-lookup"><span data-stu-id="9c7df-109">To load an assembly into an application domain</span></span>  
  
1.  <span data-ttu-id="9c7df-110">Utilice uno de los diversos métodos de carga de las clases <xref:System.AppDomain> y <xref:System.Reflection>.</span><span class="sxs-lookup"><span data-stu-id="9c7df-110">Use one of the several load methods contained in the classes <xref:System.AppDomain> and <xref:System.Reflection>.</span></span> <span data-ttu-id="9c7df-111">Para obtener más información, vea [Cómo: Cargar ensamblados en un dominio de aplicación](../../../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md).</span><span class="sxs-lookup"><span data-stu-id="9c7df-111">For more information, see [How to: Load Assemblies into an Application Domain](../../../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md).</span></span>  
  
### <a name="to-unload-an-application-domain"></a><span data-ttu-id="9c7df-112">Para descargar un dominio de aplicación</span><span class="sxs-lookup"><span data-stu-id="9c7df-112">To unload an application domain</span></span>  
  
1.  <span data-ttu-id="9c7df-113">No existe ninguna forma de descargar un ensamblado individual sin descargar todos los dominios de aplicación que lo contienen.</span><span class="sxs-lookup"><span data-stu-id="9c7df-113">There is no way to unload an individual assembly without unloading all of the application domains that contain it.</span></span> <span data-ttu-id="9c7df-114">Utilice el método `Unload` de <xref:System.AppDomain> para descargar los dominios de aplicación.</span><span class="sxs-lookup"><span data-stu-id="9c7df-114">Use the `Unload` method from <xref:System.AppDomain> to unload the application domains.</span></span> <span data-ttu-id="9c7df-115">Para obtener más información, vea [Cómo: Descargar un dominio de aplicación](../../../../framework/app-domains/how-to-unload-an-application-domain.md).</span><span class="sxs-lookup"><span data-stu-id="9c7df-115">For more information, see [How to: Unload an Application Domain](../../../../framework/app-domains/how-to-unload-an-application-domain.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c7df-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="9c7df-116">See Also</span></span>  
 [<span data-ttu-id="9c7df-117">Conceptos de programación</span><span class="sxs-lookup"><span data-stu-id="9c7df-117">Programming Concepts</span></span>](../../../../visual-basic/programming-guide/concepts/index.md)  
 [<span data-ttu-id="9c7df-118">Ensamblados y caché global de ensamblados (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9c7df-118">Assemblies and the Global Assembly Cache (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [<span data-ttu-id="9c7df-119">Cómo: Cargar ensamblados en un dominio de aplicación</span><span class="sxs-lookup"><span data-stu-id="9c7df-119">How to: Load Assemblies into an Application Domain</span></span>](../../../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md)
