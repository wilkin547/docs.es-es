---
title: "Cómo: Cargar y descargar ensamblados (C#)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 6a4f490f-3576-471f-9533-003737cad4a3
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 6bf6de24f4cbc3f3bd855b6d2cafa8120ebd90ee
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-load-and-unload-assemblies-c"></a><span data-ttu-id="39d6c-102">Cómo: Cargar y descargar ensamblados (C#)</span><span class="sxs-lookup"><span data-stu-id="39d6c-102">How to: Load and Unload Assemblies (C#)</span></span>
<span data-ttu-id="39d6c-103">Los ensamblados a los que hace referencia el programa se cargarán automáticamente en tiempo de compilación, pero también es posible cargar ensamblados específicos en el dominio de aplicación actual en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="39d6c-103">The assemblies referenced by your program will automatically be loaded at build time, but it is also possible to load specific assemblies into the current application domain at runtime.</span></span> <span data-ttu-id="39d6c-104">Para obtener más información, vea [Cómo: Cargar ensamblados en un dominio de aplicación](../../../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md).</span><span class="sxs-lookup"><span data-stu-id="39d6c-104">For more information, see [How to: Load Assemblies into an Application Domain](../../../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md).</span></span>  
  
 <span data-ttu-id="39d6c-105">No existe ninguna forma de descargar un ensamblado individual sin descargar todos los dominios de aplicación que lo contienen.</span><span class="sxs-lookup"><span data-stu-id="39d6c-105">There is no way to unload an individual assembly without unloading all of the application domains that contain it.</span></span> <span data-ttu-id="39d6c-106">Aunque el ensamblado esté fuera de ámbito, el archivo de ensamblado actual permanecerá cargado hasta que se descarguen todos los dominios de aplicación que lo contienen.</span><span class="sxs-lookup"><span data-stu-id="39d6c-106">Even if the assembly goes out of scope, the actual assembly file will remain loaded until all application domains that contain it are unloaded.</span></span>  
  
 <span data-ttu-id="39d6c-107">Si desea descargar algunos ensamblados pero no otros, considere la posibilidad de crear un nuevo dominio de aplicación, ejecutar el código en el dominio y, a continuación, descargar ese dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="39d6c-107">If you want to unload some assemblies but not others, consider creating a new application domain, executing the code inside that domain, and then unloading that application domain.</span></span> <span data-ttu-id="39d6c-108">Para obtener más información, vea [Cómo: Descargar un dominio de aplicación](../../../../framework/app-domains/how-to-unload-an-application-domain.md).</span><span class="sxs-lookup"><span data-stu-id="39d6c-108">For more information, see [How to: Unload an Application Domain](../../../../framework/app-domains/how-to-unload-an-application-domain.md).</span></span>  
  
### <a name="to-load-an-assembly-into-an-application-domain"></a><span data-ttu-id="39d6c-109">Para cargar un ensamblado en un dominio de aplicación</span><span class="sxs-lookup"><span data-stu-id="39d6c-109">To load an assembly into an application domain</span></span>  
  
1.  <span data-ttu-id="39d6c-110">Utilice uno de los diversos métodos de carga de las clases <xref:System.AppDomain> y <xref:System.Reflection>.</span><span class="sxs-lookup"><span data-stu-id="39d6c-110">Use one of the several load methods contained in the classes <xref:System.AppDomain> and <xref:System.Reflection>.</span></span> <span data-ttu-id="39d6c-111">Para obtener más información, vea [Cómo: Cargar ensamblados en un dominio de aplicación](../../../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md).</span><span class="sxs-lookup"><span data-stu-id="39d6c-111">For more information, see [How to: Load Assemblies into an Application Domain](../../../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md).</span></span>  
  
### <a name="to-unload-an-application-domain"></a><span data-ttu-id="39d6c-112">Para descargar un dominio de aplicación</span><span class="sxs-lookup"><span data-stu-id="39d6c-112">To unload an application domain</span></span>  
  
1.  <span data-ttu-id="39d6c-113">No existe ninguna forma de descargar un ensamblado individual sin descargar todos los dominios de aplicación que lo contienen.</span><span class="sxs-lookup"><span data-stu-id="39d6c-113">There is no way to unload an individual assembly without unloading all of the application domains that contain it.</span></span> <span data-ttu-id="39d6c-114">Utilice el método `Unload` de <xref:System.AppDomain> para descargar los dominios de aplicación.</span><span class="sxs-lookup"><span data-stu-id="39d6c-114">Use the `Unload` method from <xref:System.AppDomain> to unload the application domains.</span></span> <span data-ttu-id="39d6c-115">Para obtener más información, vea [Cómo: Descargar un dominio de aplicación](../../../../framework/app-domains/how-to-unload-an-application-domain.md).</span><span class="sxs-lookup"><span data-stu-id="39d6c-115">For more information, see [How to: Unload an Application Domain](../../../../framework/app-domains/how-to-unload-an-application-domain.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39d6c-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="39d6c-116">See Also</span></span>  
 <span data-ttu-id="39d6c-117">[Guía de programación de C#](../../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="39d6c-117">[C# Programming Guide](../../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="39d6c-118">[Ensamblados y caché global de ensamblados (C#)](../../../../csharp/programming-guide/concepts/assemblies-gac/index.md) </span><span class="sxs-lookup"><span data-stu-id="39d6c-118">[Assemblies and the Global Assembly Cache (C#)](../../../../csharp/programming-guide/concepts/assemblies-gac/index.md) </span></span>  
 [<span data-ttu-id="39d6c-119">Cómo: Cargar ensamblados en un dominio de aplicación</span><span class="sxs-lookup"><span data-stu-id="39d6c-119">How to: Load Assemblies into an Application Domain</span></span>](../../../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md)

