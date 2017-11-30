---
title: "Cómo: determinar qué revisiones y actualizaciones de seguridad de .NET Framework están instaladas"
description: "Obtenga información acerca de cómo determinar qué actualizaciones de seguridad de .NET Framework y las revisiones se instalan en un equipo."
ms.date: 11/21/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- updates, determining for .NET Framework
- .NET Framework, determining updates
ms.assetid: 53c7b5f7-d47a-402a-b194-7244a696a88b
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c35705470a8e1b553eca2ca0c68d3b8b9b3f6fa6
ms.sourcegitcommit: a3ba258f7a8cab5c6d19a3743dd95e904ecebc44
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/27/2017
---
# <a name="how-to-determine-which-net-framework-security-updates-and-hotfixes-are-installed"></a><span data-ttu-id="73fba-103">Cómo: determinar qué revisiones y actualizaciones de seguridad de .NET Framework están instaladas</span><span class="sxs-lookup"><span data-stu-id="73fba-103">How to: Determine which .NET Framework security updates and hotfixes are installed</span></span>

<span data-ttu-id="73fba-104">Este artículo muestra cómo averiguar qué seguridad de .NET Framework de actualizaciones y revisiones se instalan en un equipo.</span><span class="sxs-lookup"><span data-stu-id="73fba-104">This article shows you how to find out which .NET Framework security updates and hotfixes are installed on a computer.</span></span>

> [!NOTE]
> <span data-ttu-id="73fba-105">Todas las técnicas que se muestra en este artículo requieren una cuenta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="73fba-105">All the techniques shown in this article require an account with administrative privileges.</span></span>

## <a name="to-find-installed-updates-using-the-registry"></a><span data-ttu-id="73fba-106">Para buscar las actualizaciones instaladas mediante el registro</span><span class="sxs-lookup"><span data-stu-id="73fba-106">To find installed updates using the registry</span></span>

<span data-ttu-id="73fba-107">Las actualizaciones de seguridad instaladas y revisiones para cada versión de .NET Framework instalada en un equipo se muestran en el registro de Windows.</span><span class="sxs-lookup"><span data-stu-id="73fba-107">The installed security updates and hotfixes for each version of the .NET Framework installed on a computer are listed in the Windows registry.</span></span> <span data-ttu-id="73fba-108">Puede usar el Editor del registro (*regedit.exe*) programa para ver esta información.</span><span class="sxs-lookup"><span data-stu-id="73fba-108">You can use the Registry Editor (*regedit.exe*) program to view this information.</span></span>

1. <span data-ttu-id="73fba-109">Abra el programa **regedit.exe**.</span><span class="sxs-lookup"><span data-stu-id="73fba-109">Open the program **regedit.exe**.</span></span> <span data-ttu-id="73fba-110">En Windows 8 y versiones posteriores, haga clic en **iniciar** ![logotipo de Windows](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo"), a continuación, seleccione **ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="73fba-110">In Windows 8 and later versions, right-click **Start** ![Windows logo](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo"), then select **Run**.</span></span> <span data-ttu-id="73fba-111">En el **abiertos** cuadro, escriba **regedit** y seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="73fba-111">In the **Open** box, enter **regedit** and select **OK**.</span></span>

2. <span data-ttu-id="73fba-112">En el Editor del Registro, abra la subclave siguiente:</span><span class="sxs-lookup"><span data-stu-id="73fba-112">In the Registry Editor, open the following subkey:</span></span>

     `HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Updates`

     <span data-ttu-id="73fba-113">Las actualizaciones instaladas se muestran bajo subclaves que identifican la versión de .NET Framework a la que se aplican.</span><span class="sxs-lookup"><span data-stu-id="73fba-113">The installed updates are listed under subkeys that identify the .NET Framework version they apply to.</span></span> <span data-ttu-id="73fba-114">Cada actualización se identifica mediante un número de la Knowledge Base (KB).</span><span class="sxs-lookup"><span data-stu-id="73fba-114">Each update is identified by a Knowledge Base (KB) number.</span></span>

<span data-ttu-id="73fba-115">En el Editor del Registro, las versiones de .NET Framework y las actualizaciones instaladas para cada versión se almacenan en diferentes subclaves.</span><span class="sxs-lookup"><span data-stu-id="73fba-115">In the Registry Editor, the .NET Framework versions and installed updates for each version are stored in different subkeys.</span></span> <span data-ttu-id="73fba-116">Para obtener información sobre cómo detectar los números de versión instalada, consulte [Cómo: determinar qué versiones de .NET Framework están instaladas](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md).</span><span class="sxs-lookup"><span data-stu-id="73fba-116">For information about detecting the installed version numbers, see [How to: Determine which .NET Framework versions are installed](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md).</span></span>

## <a name="to-find-installed-updates-by-querying-the-registry-in-code"></a><span data-ttu-id="73fba-117">Para buscar actualizaciones instaladas consultando el registro en el código</span><span class="sxs-lookup"><span data-stu-id="73fba-117">To find installed updates by querying the registry in code</span></span>

<span data-ttu-id="73fba-118">En el ejemplo siguiente se determina mediante programación las actualizaciones de seguridad de .NET Framework y revisiones que se instalan en un equipo:</span><span class="sxs-lookup"><span data-stu-id="73fba-118">The following example programmatically determines the .NET Framework security updates and hotfixes that are installed on a computer:</span></span>

[!code-csharp[ListUpdates](../../../samples/snippets/csharp/VS_Snippets_CLR/listupdates/cs/program.cs)]
[!code-vb[ListUpdates](../../../samples/snippets/visualbasic/VS_Snippets_CLR/listupdates/vb/program.vb)]

<span data-ttu-id="73fba-119">El ejemplo genera una salida similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="73fba-119">The example produces an output that's similar to the following one:</span></span>

```console
Microsoft .NET Framework 4 Client Profile
  KB2468871
  KB2468871v2
  KB2478063
  KB2533523
  KB2544514
  KB2600211
  KB2600217
Microsoft .NET Framework 4 Extended
  KB2468871
  KB2468871v2
  KB2478063
  KB2533523
  KB2544514
  KB2600211
  KB2600217
```

## <a name="to-find-installed-updates-by-querying-the-registry-in-powershell"></a><span data-ttu-id="73fba-120">Para buscar actualizaciones instaladas consultando el registro en PowerShell</span><span class="sxs-lookup"><span data-stu-id="73fba-120">To find installed updates by querying the registry in PowerShell</span></span>

<span data-ttu-id="73fba-121">En el ejemplo siguiente se muestra cómo determinar las actualizaciones de seguridad de .NET Framework y revisiones que se instalan en un equipo con PowerShell:</span><span class="sxs-lookup"><span data-stu-id="73fba-121">The following example shows how to determine the .NET Framework security updates and hotfixes that are installed on a computer using PowerShell:</span></span>

```powershell
 Get-ChildItem "HKLM:SOFTWARE\Wow6432Node\Microsoft\Updates\*" -Recurse | Where-Object {$_.name -like
 "*.NET Framework*"}
```

<span data-ttu-id="73fba-122">El ejemplo genera una salida similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="73fba-122">The example produces an output that's similar to the following one:</span></span>

```console
    Hive: HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Updates\Microsoft .NET Framework 4 Client Profile


Name                           Property
----                           --------
KB2468871                      ThisVersionInstalled : Y
KB2468871v2                    ThisVersionInstalled : Y
KB2478063                      ThisVersionInstalled : Y
KB2533523                      ThisVersionInstalled : Y
KB2544514                      ThisVersionInstalled : Y
KB2600211                      ThisVersionInstalled : Y
KB2600217                      ThisVersionInstalled : Y


    Hive: HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Updates\Microsoft .NET Framework 4 Extended


Name                           Property
----                           --------
KB2468871                      ThisVersionInstalled : Y
KB2468871v2                    ThisVersionInstalled : Y
KB2478063                      ThisVersionInstalled : Y
KB2533523                      ThisVersionInstalled : Y
KB2544514                      ThisVersionInstalled : Y
KB2600211                      ThisVersionInstalled : Y
KB2600217                      ThisVersionInstalled : Y
```

## <a name="see-also"></a><span data-ttu-id="73fba-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="73fba-123">See also</span></span>

[<span data-ttu-id="73fba-124">Cómo: determinar qué versiones de .NET Framework están instaladas</span><span class="sxs-lookup"><span data-stu-id="73fba-124">How to: Determine which .NET Framework versions are installed</span></span>](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md)  
[<span data-ttu-id="73fba-125">Instalar .NET Framework para desarrolladores</span><span class="sxs-lookup"><span data-stu-id="73fba-125">Install the .NET Framework for developers</span></span>](../../../docs/framework/install/guide-for-developers.md)  
[<span data-ttu-id="73fba-126">Versiones y dependencias</span><span class="sxs-lookup"><span data-stu-id="73fba-126">Versions and dependencies</span></span>](../../../docs/framework/migration-guide/versions-and-dependencies.md)
