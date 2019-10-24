---
title: Procedimiento para determinar las actualizaciones de seguridad y revisiones de .NET Framework que están instaladas
description: Aprenda a determinar qué actualizaciones de seguridad y revisiones de .NET Framework están instaladas en un equipo.
ms.date: 11/27/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- updates, determining for .NET Framework
- .NET Framework, determining updates
ms.assetid: 53c7b5f7-d47a-402a-b194-7244a696a88b
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1c69d4bb370087dddafbfed41cbfb1fef229677c
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2019
ms.locfileid: "72318974"
---
# <a name="how-to-determine-which-net-framework-security-updates-and-hotfixes-are-installed"></a><span data-ttu-id="4f574-103">Procedimiento para determinar las actualizaciones de seguridad y revisiones de .NET Framework que están instaladas</span><span class="sxs-lookup"><span data-stu-id="4f574-103">How to: Determine which .NET Framework security updates and hotfixes are installed</span></span>

<span data-ttu-id="4f574-104">En este artículo se muestra cómo determinar qué actualizaciones de seguridad y revisiones de .NET Framework están instaladas en un equipo.</span><span class="sxs-lookup"><span data-stu-id="4f574-104">This article shows you how to find out which .NET Framework security updates and hotfixes are installed on a computer.</span></span>

> [!NOTE]
> <span data-ttu-id="4f574-105">Todas las técnicas que se muestran en este artículo requieren una cuenta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="4f574-105">All the techniques shown in this article require an account with administrative privileges.</span></span>

## <a name="to-find-installed-updates-using-the-registry"></a><span data-ttu-id="4f574-106">Búsqueda de las actualizaciones instaladas mediante el Registro</span><span class="sxs-lookup"><span data-stu-id="4f574-106">To find installed updates using the registry</span></span>

<span data-ttu-id="4f574-107">Las actualizaciones de seguridad y las revisiones instaladas para cada versión de .NET Framework instalada en un equipo se enumeran en el Registro de Windows.</span><span class="sxs-lookup"><span data-stu-id="4f574-107">The installed security updates and hotfixes for each version of the .NET Framework installed on a computer are listed in the Windows registry.</span></span> <span data-ttu-id="4f574-108">Puede utilizar el Editor del Registro (*regedit.exe*) para ver esta información.</span><span class="sxs-lookup"><span data-stu-id="4f574-108">You can use the Registry Editor (*regedit.exe*) program to view this information.</span></span>

1. <span data-ttu-id="4f574-109">Abra el programa **regedit.exe**.</span><span class="sxs-lookup"><span data-stu-id="4f574-109">Open the program **regedit.exe**.</span></span> <span data-ttu-id="4f574-110">En Windows 8 y versiones posteriores, haga clic con el botón derecho en **Inicio** ![Captura de pantalla de la tecla del logotipo de Windows](./media/how-to-determine-which-net-framework-updates-are-installed/windows-keyboard-logo.png "Windowskeyboardlogo") y seleccione **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="4f574-110">In Windows 8 and later versions, right-click **Start** ![Screenshot of the Windows key logo.](./media/how-to-determine-which-net-framework-updates-are-installed/windows-keyboard-logo.png "Windowskeyboardlogo"), then select **Run**.</span></span> <span data-ttu-id="4f574-111">En el cuadro **Abrir**, escriba **regedit.exe** y seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4f574-111">In the **Open** box, enter **regedit** and select **OK**.</span></span>

2. <span data-ttu-id="4f574-112">En el Editor del Registro, abra la subclave siguiente:</span><span class="sxs-lookup"><span data-stu-id="4f574-112">In the Registry Editor, open the following subkey:</span></span>

     `HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Updates`

     <span data-ttu-id="4f574-113">Las actualizaciones instaladas se muestran bajo subclaves que identifican la versión de .NET Framework a la que se aplican.</span><span class="sxs-lookup"><span data-stu-id="4f574-113">The installed updates are listed under subkeys that identify the .NET Framework version they apply to.</span></span> <span data-ttu-id="4f574-114">Cada actualización se identifica mediante un número de la Knowledge Base (KB).</span><span class="sxs-lookup"><span data-stu-id="4f574-114">Each update is identified by a Knowledge Base (KB) number.</span></span>

<span data-ttu-id="4f574-115">En el Editor del Registro, las versiones de .NET Framework y las actualizaciones instaladas para cada versión se almacenan en diferentes subclaves.</span><span class="sxs-lookup"><span data-stu-id="4f574-115">In the Registry Editor, the .NET Framework versions and installed updates for each version are stored in different subkeys.</span></span> <span data-ttu-id="4f574-116">Para obtener información sobre cómo detectar los números de versión instalados, vea [Procedimiento para determinar qué versiones de .NET Framework están instaladas](how-to-determine-which-versions-are-installed.md).</span><span class="sxs-lookup"><span data-stu-id="4f574-116">For information about detecting the installed version numbers, see [How to: Determine which .NET Framework versions are installed](how-to-determine-which-versions-are-installed.md).</span></span>

## <a name="to-find-installed-updates-by-querying-the-registry-in-code"></a><span data-ttu-id="4f574-117">Búsqueda de las actualizaciones instaladas mediante la consulta al Registro en código</span><span class="sxs-lookup"><span data-stu-id="4f574-117">To find installed updates by querying the registry in code</span></span>

<span data-ttu-id="4f574-118">El ejemplo siguiente determina mediante programación las actualizaciones de seguridad y las revisiones de .NET Framework instaladas en un equipo:</span><span class="sxs-lookup"><span data-stu-id="4f574-118">The following example programmatically determines the .NET Framework security updates and hotfixes that are installed on a computer:</span></span>

[!code-csharp[ListUpdates](../../../samples/snippets/csharp/VS_Snippets_CLR/listupdates/cs/program.cs)]
[!code-vb[ListUpdates](../../../samples/snippets/visualbasic/VS_Snippets_CLR/listupdates/vb/program.vb)]

<span data-ttu-id="4f574-119">El ejemplo genera un resultado similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="4f574-119">The example produces an output that's similar to the following one:</span></span>

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

## <a name="to-find-installed-updates-by-querying-the-registry-in-powershell"></a><span data-ttu-id="4f574-120">Búsqueda de las actualizaciones instaladas mediante la consulta al Registro en PowerShell</span><span class="sxs-lookup"><span data-stu-id="4f574-120">To find installed updates by querying the registry in PowerShell</span></span>

<span data-ttu-id="4f574-121">El ejemplo siguiente muestra cómo determinar las actualizaciones de seguridad y las revisiones de .NET Framework instaladas en un equipo mediante PowerShell:</span><span class="sxs-lookup"><span data-stu-id="4f574-121">The following example shows how to determine the .NET Framework security updates and hotfixes that are installed on a computer using PowerShell:</span></span>

```powershell
$DotNetVersions = Get-ChildItem HKLM:\SOFTWARE\WOW6432Node\Microsoft\Updates | Where-Object {$_.name -like
 "*.NET Framework*"}

ForEach($Version in $DotNetVersions){
    
   $Updates = Get-ChildItem $Version.PSPath
    $Version.PSChildName
    ForEach ($Update in $Updates){
       $Update.PSChildName
       }
}
```

<span data-ttu-id="4f574-122">El ejemplo genera un resultado similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="4f574-122">The example produces an output that's similar to the following one:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="4f574-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="4f574-123">See also</span></span>

- [<span data-ttu-id="4f574-124">Cómo: Determinar qué versiones de .NET Framework están instaladas</span><span class="sxs-lookup"><span data-stu-id="4f574-124">How to: Determine which .NET Framework versions are installed</span></span>](how-to-determine-which-versions-are-installed.md)
- [<span data-ttu-id="4f574-125">Instalación de .NET Framework para desarrolladores</span><span class="sxs-lookup"><span data-stu-id="4f574-125">Install the .NET Framework for developers</span></span>](../install/guide-for-developers.md)
- [<span data-ttu-id="4f574-126">Versiones y dependencias</span><span class="sxs-lookup"><span data-stu-id="4f574-126">Versions and dependencies</span></span>](versions-and-dependencies.md)
