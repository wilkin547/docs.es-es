---
title: "Cómo: Determinar qué actualizaciones de .NET Framework están instaladas"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- updates, determining for .NET Framework
- .NET Framework, determining updates
ms.assetid: 53c7b5f7-d47a-402a-b194-7244a696a88b
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ba734dd3a9585b52b96cb2d27743da6190961126
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-determine-which-net-framework-updates-are-installed"></a><span data-ttu-id="51cb8-102">Cómo: Determinar qué actualizaciones de .NET Framework están instaladas</span><span class="sxs-lookup"><span data-stu-id="51cb8-102">How to: Determine Which .NET Framework Updates Are Installed</span></span>
<span data-ttu-id="51cb8-103">Las actualizaciones instaladas para cada versión de .NET Framework instalada en un equipo se enumeran en el Registro de Windows.</span><span class="sxs-lookup"><span data-stu-id="51cb8-103">The installed updates for each version of the .NET Framework installed on a computer are listed in the Windows registry.</span></span> <span data-ttu-id="51cb8-104">Puede utilizar el Editor del Registro (regedit.exe) para ver esta información.</span><span class="sxs-lookup"><span data-stu-id="51cb8-104">You can use the Registry Editor (regedit.exe) to view this information.</span></span>  
  
 <span data-ttu-id="51cb8-105">En el Editor del Registro, las versiones de .NET Framework y las actualizaciones instaladas para cada versión se almacenan en diferentes subclaves.</span><span class="sxs-lookup"><span data-stu-id="51cb8-105">In the Registry Editor, the .NET Framework versions and installed updates for each version are stored in different subkeys.</span></span> <span data-ttu-id="51cb8-106">Para obtener información sobre cómo detectar los números de la versión instalada, consulte [Cómo: Determinar qué versiones de .NET Framework están instaladas](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md).</span><span class="sxs-lookup"><span data-stu-id="51cb8-106">For information about detecting the installed version numbers, see [How to: Determine Which .NET Framework Versions Are Installed](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md).</span></span> <span data-ttu-id="51cb8-107">Para obtener información sobre cómo instalar .NET Framework, consulte [Install the .NET Framework for developers](../../../docs/framework/install/guide-for-developers.md) (Instalar .NET Framework para desarrolladores).</span><span class="sxs-lookup"><span data-stu-id="51cb8-107">For information about installing the .NET Framework, see [Install the .NET Framework for developers](../../../docs/framework/install/guide-for-developers.md).</span></span>  
  
### <a name="to-find-installed-updates"></a><span data-ttu-id="51cb8-108">Para buscar las actualizaciones instaladas</span><span class="sxs-lookup"><span data-stu-id="51cb8-108">To find installed updates</span></span>  
  
1.  <span data-ttu-id="51cb8-109">Abra el programa **regedit.exe**.</span><span class="sxs-lookup"><span data-stu-id="51cb8-109">Open the program **regedit.exe**.</span></span> <span data-ttu-id="51cb8-110">En Windows 8 y versiones posteriores, abra la pantalla Inicio y escriba el nombre.</span><span class="sxs-lookup"><span data-stu-id="51cb8-110">In Windows 8 and higher open the Start screen and type the name.</span></span> <span data-ttu-id="51cb8-111">En versiones anteriores de Windows, en el menú **Iniciar**, elija **Ejecutar** y, después, en el cuadro **Abrir**, escriba **regedit.exe**.</span><span class="sxs-lookup"><span data-stu-id="51cb8-111">In earlier versions of Windows, on the **Start** menu, choose **Run** and then, in the **Open** box, enter **regedit.exe**.</span></span>  
  
     <span data-ttu-id="51cb8-112">Debe tener credenciales de administrador para ejecutar regedit.exe.</span><span class="sxs-lookup"><span data-stu-id="51cb8-112">You must have administrative credentials to run regedit.exe.</span></span>  
  
2.  <span data-ttu-id="51cb8-113">En el Editor del Registro, abra la subclave siguiente:</span><span class="sxs-lookup"><span data-stu-id="51cb8-113">In the Registry Editor, open the following subkey:</span></span>  
  
     <span data-ttu-id="51cb8-114">HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Updates</span><span class="sxs-lookup"><span data-stu-id="51cb8-114">HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Updates</span></span>  
  
     <span data-ttu-id="51cb8-115">Las actualizaciones instaladas se muestran bajo subclaves que identifican la versión de .NET Framework a la que se aplican.</span><span class="sxs-lookup"><span data-stu-id="51cb8-115">The installed updates are listed under subkeys that identify the .NET Framework version they apply to.</span></span> <span data-ttu-id="51cb8-116">Cada actualización se identifica mediante un número de la Knowledge Base (KB).</span><span class="sxs-lookup"><span data-stu-id="51cb8-116">Each update is identified by a Knowledge Base (KB) number.</span></span>  
  
## <a name="example"></a><span data-ttu-id="51cb8-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="51cb8-117">Example</span></span>  
 <span data-ttu-id="51cb8-118">El código siguiente determina mediante programación las actualizaciones de .NET Framework instaladas en un equipo.</span><span class="sxs-lookup"><span data-stu-id="51cb8-118">The following code programmatically determines the .NET Framework updates that are installed on a computer.</span></span> <span data-ttu-id="51cb8-119">Debe tener credenciales administrativas para ejecutar este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="51cb8-119">You must have administrative credentials to run this example.</span></span>  
  
 [!code-csharp[ListUpdates#1](../../../samples/snippets/csharp/VS_Snippets_CLR/listupdates/cs/program.cs#1)]
 [!code-vb[ListUpdates#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/listupdates/vb/program.vb#1)]  
  
 <span data-ttu-id="51cb8-120">El ejemplo genera un resultado similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="51cb8-120">The example produces output that's similar to the following:</span></span>  
  
```  
Microsoft .NET Framework 3.5 SP1  
  KB953595  Hotfix for Microsoft .NET Framework 3.5 SP1 (KB953595)  
  SP1  
    KB2657424  Security Update for Microsoft .NET Framework 3.5 SP1 (KB2657424)  
    KB958484  Hotfix for Microsoft .NET Framework 3.5 SP1 (KB958484)  
    KB963707  Update for Microsoft .NET Framework 3.5 SP1 (KB963707)  
Microsoft .NET Framework 4 Client Profile  
  KB2160841  Security Update for Microsoft .NET Framework 4 Client Profile (KB2160841)  
  KB2446708  Security Update for Microsoft .NET Framework 4 Client Profile (KB2446708)  
  KB2468871  Update for Microsoft .NET Framework 4 Client Profile (KB2468871)  
  KB2478663  Security Update for Microsoft .NET Framework 4 Client Profile (KB2478663)  
  KB2518870  Security Update for Microsoft .NET Framework 4 Client Profile (KB2518870)  
  KB2533523  Update for Microsoft .NET Framework 4 Client Profile (KB2533523)  
  KB2539636  Security Update for Microsoft .NET Framework 4 Client Profile (KB2539636)  
  KB2572078  Security Update for Microsoft .NET Framework 4 Client Profile (KB2572078)  
  KB2633870  Security Update for Microsoft .NET Framework 4 Client Profile (KB2633870)  
  KB2656351  Security Update for Microsoft .NET Framework 4 Client Profile (KB2656351)  
Microsoft .NET Framework 4 Extended  
  KB2416472  Security Update for Microsoft .NET Framework 4 Extended (KB2416472)  
  KB2468871  Update for Microsoft .NET Framework 4 Extended (KB2468871)  
  KB2487367  Security Update for Microsoft .NET Framework 4 Extended (KB2487367)  
  KB2533523  Update for Microsoft .NET Framework 4 Extended (KB2533523)  
  KB2656351  Security Update for Microsoft .NET Framework 4 Extended (KB2656351)  
```  
  
## <a name="see-also"></a><span data-ttu-id="51cb8-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="51cb8-121">See also</span></span>

<span data-ttu-id="51cb8-122">[Cómo: Determinar qué versiones de .NET Framework están instaladas](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md) </span><span class="sxs-lookup"><span data-stu-id="51cb8-122">[How to: Determine Which .NET Framework Versions Are Installed](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md) </span></span>  
<span data-ttu-id="51cb8-123">[Instalar .NET Framework](../../../docs/framework/install/guide-for-developers.md) </span><span class="sxs-lookup"><span data-stu-id="51cb8-123">[Installing the .NET Framework](../../../docs/framework/install/guide-for-developers.md) </span></span>  
[<span data-ttu-id="51cb8-124">Versiones y dependencias</span><span class="sxs-lookup"><span data-stu-id="51cb8-124">Versions and Dependencies</span></span>](../../../docs/framework/migration-guide/versions-and-dependencies.md)
